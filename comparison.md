# DevOps Tools Comparison

> Horizontal comparison of all DevOps tools analyzed in this repository.
> Last updated: 2026-04-15

## CI/CD Platform Comparison

| Feature | GitHub Actions | GitLab CI | Jenkins |
|---------|---------------|-----------|--------|
| **Stars/Adoption** | ~33% market | ~20% market | ~23k stars |
| **License** | Proprietary | MIT (CE) | MIT |
| **Hosting** | SaaS + self-hosted | SaaS + self-hosted | Self-hosted only |
| **Config** | YAML | YAML | Groovy/YAML |
| **Free Tier** | 2,000 min/month | 400 min/month | Free (self-hosted) |
| **Marketplace** | 20,000+ actions | Templates | 1,800+ plugins |
| **Security Scanning** | Via actions | Built-in SAST/DAST | Via plugins |
| **Learning Curve** | Low | Medium | High |
| **Best For** | GitHub users | GitLab users | Enterprise legacy |

### Recommendation for Solo Developer
**GitHub Actions** — already where your code lives, generous free tier, largest marketplace.

## Infrastructure Tools Comparison

| Feature | Docker | Kubernetes | Terraform | Argo CD |
|---------|--------|------------|-----------|--------|
| **Stars** | ~73k | ~115k | ~45k | ~19k |
| **License** | Apache-2.0 | Apache-2.0 | BUSL-1.1 ⚠️ | Apache-2.0 |
| **Category** | Containerization | Orchestration | IaC | GitOps CD |
| **Complexity** | Low-Medium | Very High | High | High |
| **Learning Curve** | 1-2 weeks | 2-6 months | 1-2 months | 1 month |
| **Solo Dev Need** | Yes (local dev) | No | No | No |
| **Cost** | Free (OSS) | $70+/month (managed) | Free (OSS) | Free (OSS) |

### Recommendation for Micro SaaS
- **Use**: Docker (local dev), GitHub Actions (CI/CD)
- **Skip**: Kubernetes, Terraform, Argo CD (overkill for 1 person)
- **Platform**: Vercel (frontend) + Supabase/Neon (database) = zero DevOps

## TEMC Score Ranking

| Rank | Project | Overall | T | E | M | C |
|------|---------|---------|---|---|---|---|
| 1 | **GitHub Actions** | **91** | 85 | 95 | 90 | 95 |
| 2 | **Docker** | **85** | 90 | 95 | 85 | 75 |
| 3 | **Kubernetes** | **73** | 95 | 98 | 80 | 35 |
| 4 | **Terraform** | **72** | 90 | 88 | 75 | 45 |
| 5 | **GitLab CI** | **66** | 85 | 78 | 70 | 40 |
| 6 | **Vitess** | **65** | 88 | 80 | 65 | 45 |
| 7 | **Argo CD** | **64** | 88 | 82 | 70 | 30 |
| 8 | **Jenkins** | **55** | 72 | 75 | 55 | 25 |
