# Grafana

> The open-source visualization and observability platform — dashboards for everything, from Prometheus to Postgres.

| Metric | Data |
|--------|------|
| GitHub | [grafana/grafana](https://github.com/grafana/grafana) |
| Stars | 66,000+ |
| License | AGPL-3.0 ⚠️ |
| Language | Go + TypeScript |
| Last Updated | Active (daily commits) |
| Contributors | 4,000+ |
| Backed By | Grafana Labs ($240M+ funding) |

## TEMC Scoring

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T Technology (×0.25) | 82 | Rich visualization engine (30+ panel types), plugin architecture, unified alerting, Go backend + React frontend. Grafana Loki (logs) + Tempo (traces) + Mimir (metrics) = full LGTM stack. Dashboard-as-code via JSON/Terraform |
| E Ecosystem (×0.20) | 88 | 4,000+ contributors, 150+ official data source plugins, 1,000+ community dashboards. Grafana Cloud free tier (10K metrics, 50GB logs). Industry standard pairing with Prometheus |
| M Market (×0.30) | 82 | Observability market exploding ($25B+ by 2028). Grafana is the default visualization layer — even competitors use it. Growing into AI-powered observability (Grafana Assistant, ML-based anomaly detection) |
| C Combinability (×0.25) | 75 | Pairs perfectly with Prometheus for monitoring SaaS. Dashboard embedding possible. But AGPL-3.0 license means you cannot embed Grafana into a proprietary product without open-sourcing. Use as a tool, not a component |
| **Composite** | **81** | T×0.25 + E×0.20 + M×0.30 + C×0.25 = 20.5 + 17.6 + 24.6 + 18.75 |

## Architecture Highlights

```
┌─────────────────────────────────────────┐
│              Grafana Server              │
│  ┌────────────┐  ┌──────────────────┐   │
│  │ Dashboard   │  │ Alerting Engine  │   │
│  │ Engine      │  │ (Unified Alerts) │   │
│  └──────┬─────┘  └──────────────────┘   │
│         │         ┌──────────────────┐   │
│         │         │ Plugin System    │   │
│         │         │ (150+ sources)   │   │
│         │         └──────────────────┘   │
└─────────┼───────────────────────────────┘
          │ query
   ┌──────┼──────┬──────────┬──────────┐
   ▼      ▼      ▼          ▼          ▼
Prome-  Loki   Postgres  Elastic   Cloud-
theus   (logs)  (SQL)    search    Watch
```

**Key Design Decisions:**
- **Data source agnostic**: Query anything — Prometheus, Postgres, Elasticsearch, CloudWatch, 150+ sources
- **Dashboard-as-code**: Export/import JSON, Terraform provider, Git-based workflow
- **Unified alerting**: One alerting system across all data sources (replaced legacy per-source alerting)
- **Plugin architecture**: Panels, data sources, apps — extensible without forking

## Extractable Patterns

1. **Dashboard templates** → code-base/monitoring/grafana-dashboards/ (SaaS metrics, Node.js app, Postgres)
2. **Alert rule templates** → SLO-based alerts (error budget, latency, availability)
3. **Dashboard-as-code** → Terraform + JSON provisioning for reproducible observability
4. **Embedded analytics pattern** → Grafana panel embedding for customer-facing dashboards

## Competitive Landscape

| | Grafana | Datadog | Kibana | Metabase | Apache Superset |
|--|---------|---------|--------|----------|-----------------|
| Focus | Observability | Full APM | Log analytics | BI/Analytics | BI/Analytics |
| Cost | Free/Cloud | $15/host+ | Free/Cloud | Free/Cloud | Free |
| Stars | 66K+ | N/A | 20K | 39K | 63K |
| Data Sources | 150+ | Built-in | Elasticsearch | SQL databases | SQL databases |
| License | AGPL-3.0 ⚠️ | Proprietary | SSPL ⚠️ | AGPL-3.0 ⚠️ | Apache-2.0 ✅ |
| Best For | Metrics viz | Enterprise ops | Log deep-dive | Business BI | Data exploration |

## Solo Dev Verdict

**Must-have knowledge, deploy with Prometheus post-PMF.** The Prometheus + Grafana combo is the gold standard for self-hosted monitoring at zero cost. Pre-PMF, Grafana Cloud free tier gives you dashboards without running infrastructure.

⚠️ **AGPL-3.0 License Warning**: You can USE Grafana freely for internal dashboards, but you CANNOT embed Grafana panels into a proprietary SaaS product you sell — that triggers AGPL copyleft. For customer-facing analytics, use Metabase (AGPL but with embedding license) or Apache Superset (Apache-2.0).

**When it IS essential:** Production SaaS monitoring, customer-facing status pages, internal analytics dashboards, SOC 2 compliance evidence.
