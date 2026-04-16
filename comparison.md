# DevOps Tools Comparison

> Horizontal comparison of all DevOps tools analyzed in this repository.
> Last updated: 2026-04-16

## CI/CD Platform Comparison

| Feature | GitHub Actions | GitLab CI | Jenkins | Act (local) |
|---------|---------------|-----------|--------|-------------|
| **Stars/Adoption** | ~33% market | ~20% market | ~23k stars | 70k stars |
| **License** | Proprietary | MIT (CE) | MIT | MIT |
| **Hosting** | SaaS + self-hosted | SaaS + self-hosted | Self-hosted only | Local only |
| **Config** | YAML | YAML | Groovy/YAML | Same as GH Actions |
| **Free Tier** | 2,000 min/month | 400 min/month | Free (self-hosted) | Free (local) |
| **Best For** | GitHub users | GitLab users | Enterprise legacy | Local testing |

### Recommendation for Solo Developer
**GitHub Actions + Act** — write workflows in GitHub Actions, test locally with Act, push when green.

## Deployment Tools Comparison

| Feature | Coolify | Kamal | Vercel |
|---------|---------|-------|--------|
| **Stars** | 53k | 14k | N/A |
| **License** | Apache-2.0 | MIT | Proprietary |
| **Type** | Self-hosted PaaS | CLI deploy tool | Managed PaaS |
| **Language** | PHP (Laravel) | Ruby | N/A |
| **One-click services** | 280+ | No | Limited |
| **Zero-downtime** | ✅ | ✅ | ✅ |
| **Custom domains** | ✅ | ✅ | ✅ (paid) |
| **Cost** | $5-20/mo VPS | $5-20/mo VPS | $20+/mo |
| **Setup time** | 30 min | 15 min | 5 min |
| **Learning curve** | Low | Medium (Ruby) | Very Low |

### Recommendation for Micro SaaS
- **Start**: Vercel (zero DevOps, fastest to market)
- **Scale**: Coolify on Hetzner (save money at $50+/month spend)
- **Learn**: Kamal's Docker+SSH pattern (transferable knowledge)

## Infrastructure Tools Comparison

| Feature | Docker | Kubernetes | OpenTofu | Terraform | Traefik |
|---------|--------|------------|----------|-----------|--------|
| **Stars** | ~73k | ~115k | 28k | ~45k | 63k |
| **License** | Apache-2.0 | Apache-2.0 | MPL-2.0 | BUSL-1.1 ⚠️ | MIT |
| **Category** | Containers | Orchestration | IaC | IaC | Reverse Proxy |
| **Complexity** | Low-Med | Very High | High | High | Medium |
| **Solo Dev Need** | Yes | No | No | No | Indirect |
| **Cost** | Free | $70+/mo managed | Free | Free | Free |

### Recommendation for Micro SaaS
- **Use**: Docker (local dev), Traefik (embedded in Coolify/Kamal)
- **Skip**: Kubernetes, OpenTofu/Terraform (overkill for 1 person)
- **Platform**: Vercel (frontend) + Supabase (database) = zero DevOps

## TEMC Score Ranking (All 12 Projects)

| Rank | Project | Overall | T | E | M | C | Solo Dev |
|------|---------|---------|---|---|---|---|----------|
| 1 | **GitHub Actions** | **91** | 85 | 95 | 90 | 95 | 🟢 Must |
| 2 | **Docker** | **85** | 90 | 95 | 85 | 75 | 🟢 Must |
| 3 | **Act** | **84** | 85 | 90 | 88 | 90 | 🟢 Must |
| 4 | **Coolify** | **82** | 82 | 88 | 90 | 85 | 🟢 Use |
| 5 | **OpenTofu** | **76** | 88 | 82 | 85 | 65 | 🟡 Later |
| 6 | **Traefik** | **76** | 90 | 88 | 82 | 60 | 🟡 Indirect |
| 7 | **Kubernetes** | **73** | 95 | 98 | 80 | 35 | 🔴 Skip |
| 8 | **Terraform** | **72** | 90 | 88 | 75 | 45 | 🔴 Skip |
| 9 | **Kamal** | **71** | 80 | 72 | 78 | 70 | 🟡 Learn |
| 10 | **GitLab CI** | **66** | 85 | 78 | 70 | 40 | 🔴 Skip |
| 11 | **Vitess** | **65** | 88 | 80 | 65 | 45 | 🔴 Skip |
| 12 | **Argo CD** | **64** | 88 | 82 | 70 | 30 | 🔴 Skip |
| 13 | **Jenkins** | **55** | 72 | 75 | 55 | 25 | 🔴 Skip |

## Solo Dev Priority Stack

```
Tier 1 (Install today):
  GitHub Actions + Act + Docker

Tier 2 (When spending $50+/month on hosting):
  Coolify on Hetzner VPS

Tier 3 (When managing 5+ services):
  Traefik (learn labels), Kamal (learn pattern)

Tier 4 (When enterprise):
  OpenTofu, Kubernetes, Argo CD
```
