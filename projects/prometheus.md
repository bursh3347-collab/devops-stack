# Prometheus

> Open-source monitoring and alerting toolkit — the de facto standard for cloud-native metrics collection.

| Metric | Data |
|--------|------|
| GitHub | [prometheus/prometheus](https://github.com/prometheus/prometheus) |
| Stars | 56,000+ |
| License | Apache-2.0 ✅ |
| Language | Go |
| Last Updated | Active (daily commits) |
| Contributors | 1,100+ |
| Backed By | CNCF (Graduated) |

## TEMC Scoring

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T Technology (×0.25) | 85 | Pull-based metric collection, PromQL query language (powerful but learning curve), built-in time-series DB (TSDB), multi-dimensional data model with labels. Service discovery for dynamic targets. Single binary, no external dependencies |
| E Ecosystem (×0.20) | 90 | CNCF graduated project. 1,000+ exporters for every service imaginable. Grafana integration is industry standard. OpenMetrics standard. Thanos/Cortex/Mimir for long-term storage. AlertManager for routing |
| M Market (×0.30) | 80 | De facto standard for Kubernetes monitoring. Every major cloud offers managed Prometheus (AWS AMP, GCP Managed Prometheus, Azure). Required knowledge for any production system. Growing into AI/ML observability |
| C Combinability (×0.25) | 70 | Essential for any SaaS going to production. Prometheus + Grafana = complete observability stack. Node exporter + custom metrics = full visibility. But: overkill for pre-PMF solo dev, Vercel Analytics is simpler |
| **Composite** | **81** | T×0.25 + E×0.20 + M×0.30 + C×0.25 = 21.25 + 18.0 + 24.0 + 17.5 |

## Architecture Highlights

```
┌─────────────────────────────────────┐
│           Prometheus Server          │
│  ┌───────────┐  ┌────────────────┐  │
│  │ Retrieval  │  │   TSDB         │  │
│  │ (pull)     │──│ (local storage)│  │
│  └─────┬─────┘  └────────────────┘  │
│        │         ┌────────────────┐  │
│        │         │   PromQL       │  │
│        │         │   Engine       │  │
│        │         └────────────────┘  │
└────────┼────────────────────────────┘
         │ scrape /metrics
    ┌────┼────┬──────────┐
    ▼    ▼    ▼          ▼
  App  Node  Redis    Custom
  Exp  Exp   Exp     Exporter
```

**Key Design Decisions:**
- **Pull-based**: Prometheus scrapes targets (vs push). Simplifies service discovery, natural health checking
- **Multi-dimensional labels**: `http_requests_total{method="GET", status="200"}` — flexible slicing
- **Local TSDB**: No external database dependency. 1-2 week retention by default
- **PromQL**: Powerful but unique query language. `rate(http_requests_total[5m])` for request rate

## Extractable Patterns

1. **Metrics instrumentation** → code-base/monitoring/prometheus-metrics/ (custom metrics in Node.js/Python)
2. **Alert rules** → Standard SLO-based alerting patterns (latency p99, error rate, saturation)
3. **Service discovery** → Dynamic target discovery patterns for cloud-native apps
4. **Recording rules** → Pre-compute expensive queries for dashboard performance

## Competitive Landscape

| | Prometheus | Datadog | New Relic | InfluxDB | VictoriaMetrics |
|--|-----------|---------|-----------|----------|-----------------|
| Type | OSS | SaaS | SaaS | OSS/Cloud | OSS |
| Cost | Free | $15/host/mo+ | $0.30/GB+ | Free/Cloud | Free |
| Stars | 56K+ | N/A | N/A | 29K | 13K |
| Query | PromQL | Custom | NRQL | InfluxQL | MetricsQL |
| Best For | K8s/Cloud-native | Full-stack APM | Full-stack APM | IoT/Time-series | High-cardinality |
| Retention | 15d default | Unlimited | Unlimited | Unlimited | Unlimited |

## Solo Dev Verdict

**Learn now, deploy when you have paying users.** Pre-PMF, use Vercel Analytics + Sentry for free. Post-PMF (10+ customers), Prometheus + Grafana gives you production-grade monitoring at zero cost. The PromQL knowledge transfers to every cloud platform's managed offering.

**When it IS essential:** Running your own infrastructure, SaaS with SLA requirements, debugging performance issues at scale, preparing for SOC 2 compliance (audit trail of metrics).
