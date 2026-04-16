![Stars](https://img.shields.io/github/stars/bursh3347-collab/devops-stack?style=flat-square)
![License](https://img.shields.io/github/license/bursh3347-collab/devops-stack?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/bursh3347-collab/devops-stack?style=flat-square)

[English](README.md) | [中文](README_CN.md)

# 🛠️ devops-stack

> ⭐ Maturity: **L2 Growing** — 12+ projects analyzed, comparison & best practices complete, observability stack added.

DevOps, CI/CD, monitoring, and infrastructure tools curated for solo developers. Deep analysis, comparison, and **TEMC scoring** (Technology · Ecosystem · Market Timing · Combinability) of 12+ high-star projects — with practical best practices you can actually use.

Part of the [Open Source Knowledge Restructuring Project](https://github.com/bursh3347-collab).

## 📈 Trending This Week (Updated: 2026-04-16)

| Rank | Project | Stars | Weekly Δ | Trend |
|------|---------|-------|----------|-------|
| 1 | [Kubernetes](https://github.com/kubernetes/kubernetes) | 115k | +300 | → |
| 2 | [Docker](https://github.com/moby/moby) | 73k | +150 | → |
| 3 | [Grafana](https://github.com/grafana/grafana) | 66k | +200 | ↑ |
| 4 | [Ansible](https://github.com/ansible/ansible) | 63k | +100 | → |
| 5 | [Caddy](https://github.com/caddyserver/caddy) | 60k | +180 | ↑ |
| 6 | [Prometheus](https://github.com/prometheus/prometheus) | 56k | +160 | ↑ |
| 7 | [Traefik](https://github.com/traefik/traefik) | 52k | +120 | → |
| 8 | [Terraform](https://github.com/hashicorp/terraform) | 45k | +100 | → |
| 9 | [Pulumi](https://github.com/pulumi/pulumi) | 22k | +90 | ↑ |
| 10 | GitHub Actions | N/A | N/A | 🚀 |

> 🌟 Grafana, Caddy, Prometheus seeing steady growth. Pulumi gaining momentum as TypeScript IaC.

## 📊 Project Rankings (by TEMC Score)

| Rank | Project | Stars | TEMC | Language | Category |
|------|---------|-------|------|----------|----------|
| 1 | [GitHub Actions](projects/github-actions.md) | N/A | **91** | YAML | CI/CD |
| 2 | [Docker](projects/docker.md) | ~73k | **85** | Go | Containers |
| 3 | [Act](projects/act.md) | ~70k | **84** | Go | Local CI |
| 4 | [Coolify](projects/coolify.md) | ~53k | **82** | PHP/TS | Self-hosted PaaS |
| 5 | [Prometheus](projects/prometheus.md) | ~56k | **81** | Go | Monitoring |
| 6 | [Grafana](projects/grafana.md) | ~66k | **81** | Go/TS | Visualization |
| 7 | [Caddy](projects/caddy.md) | ~60k | **79** | Go | Web Server |
| 8 | [Pulumi](projects/pulumi.md) | ~22k | **78** | Go/TS | IaC |
| 9 | [OpenTofu](projects/opentofu.md) | ~28k | **76** | Go | IaC |
| 10 | [Traefik](projects/traefik.md) | ~53k | **76** | Go | Reverse Proxy |
| 11 | [Ansible](projects/ansible.md) | ~63k | **75** | Python | Config Management |
| 12 | [Kubernetes](projects/kubernetes.md) | ~115k | **73** | Go | Orchestration |
| 13 | [Terraform](projects/terraform.md) | ~45k | **72** | Go | IaC |
| 14 | [Kamal](projects/kamal.md) | ~14k | **71** | Ruby | Deploy CLI |
| 15 | [GitLab CI](projects/gitlab-ci.md) | ~24k | **66** | Ruby | CI/CD |
| 16 | [Argo CD](projects/argocd.md) | ~19k | **64** | Go | GitOps |
| 17 | [Jenkins](projects/jenkins.md) | ~23k | **55** | Java | CI/CD |

> **TEMC** = Technology (25%) + Ecosystem (20%) + Market Timing (30%) + Combinability (25%)

## 📋 What's Inside

- [📊 DevOps Tools Comparison](comparison.md) — Side-by-side feature matrix
- [🔄 CI/CD Pipeline Patterns](best-practices/cicd-pipeline.md) — Standard pipeline architectures
- [📦 Containerization Best Practices](best-practices/containerization.md) — Docker done right
- [🏗️ Infrastructure as Code](best-practices/infrastructure-as-code.md) — When and how to use IaC
- [🗺️ Technology Roadmap](roadmap.md) — Trends & predictions for DevOps

## 🆕 L2 Additions (April 2026)

| Project | TEMC | Why Added |
|---------|------|-----------|
| [Prometheus](projects/prometheus.md) | **81** | De facto standard for cloud-native monitoring. CNCF graduated |
| [Grafana](projects/grafana.md) | **81** | Industry-standard visualization. Pairs with Prometheus |
| [Caddy](projects/caddy.md) | **79** | Automatic HTTPS, zero-config TLS. Perfect for solo devs |
| [Pulumi](projects/pulumi.md) | **78** | TypeScript IaC — same language as your app code |
| [Ansible](projects/ansible.md) | **75** | Agentless automation, 63K+ stars, massive ecosystem |

## 🏆 Solo Dev Verdict

| Need | Pick | Why |
|------|------|-----|
| CI/CD | **GitHub Actions** | Already where your code lives, generous free tier |
| Local Dev | **Docker Compose** | Postgres + Redis in one command |
| Deployment | **Vercel** | Zero-config, git-push deploy |
| Self-hosted Deploy | **Caddy** + Docker Compose | Automatic HTTPS, simple config |
| Monitoring | **Prometheus + Grafana** | Free, production-grade (post-PMF) |
| IaC (if needed) | **Pulumi** (TypeScript) | Same language as your app |
| Database | **Supabase** or **Neon** | Managed Postgres, zero ops |

**Skip for solo work**: Kubernetes, Terraform, Argo CD, Jenkins, Ansible — overkill for a one-person team.

## 📂 Structure

```
devops-stack/
├── projects/              ← 17 individual project deep-dives (TEMC scored)
├── best-practices/        ← Cross-project patterns
├── code/                  ← Extractable code (coming soon)
├── comparison.md          ← Horizontal comparison tables
├── roadmap.md             ← Technology trends & predictions
├── CONTRIBUTING.md
├── SOURCES.md
└── README.md
```

## 📝 How to Use

1. **Compare** — Start with [comparison.md](comparison.md) for the full landscape
2. **Deep-dive** — Read the analysis for your chosen tool in `projects/`
3. **Apply** — Use patterns from `best-practices/` in your workflow
4. **Stay current** — Check [roadmap.md](roadmap.md) for where DevOps is heading

## License

Analysis content: MIT. Each referenced project has its own license — see [SOURCES.md](SOURCES.md).
