# 🔧 devops-stack

> ⭐ Maturity: **L1 Growing** — 7 projects analyzed, comparison complete, best practices started.

Extracted best practices, architecture patterns, and deep analysis from 7 high-star DevOps projects on GitHub.

## 📈 本分类飙升榜（最近更新：2026-04-15）

| 排名 | 项目 | 总Stars | 周增 | 趋势 |
|------|------|---------|------|------|
| 1 | Kubernetes | 115k | +300 | → |
| 2 | Docker | 73k | +150 | → |
| 3 | Terraform | 45k | +100 | → |
| 4 | GitLab CI | 24k | +50 | → |
| 5 | Jenkins | 23k | +30 | ↓ |
| 6 | Argo CD | 19k | +80 | ↑ |
| 7 | GitHub Actions | N/A | N/A | 🚀 |

> 🌟 GitHub Actions 无开源仓库但市场份额第一（33%+）。Argo CD 在 GitOps 领域稳步增长。

## 📋 What's Inside

### Projects Analyzed (7)
| Project | Stars | TEMC | Language | Category |
|---------|-------|------|----------|----------|
| [GitHub Actions](projects/github-actions.md) | N/A | **91** | YAML | CI/CD |
| [Docker](projects/docker.md) | ~73k | **85** | Go | Containers |
| [Kubernetes](projects/kubernetes.md) | ~115k | **73** | Go | Orchestration |
| [Terraform](projects/terraform.md) | ~45k | **72** | Go | IaC |
| [GitLab CI](projects/gitlab-ci.md) | ~24k | **66** | Ruby | CI/CD |
| [Argo CD](projects/argocd.md) | ~19k | **64** | Go | GitOps |
| [Jenkins](projects/jenkins.md) | ~23k | **55** | Java | CI/CD |

### Comparison & Best Practices
- [📊 DevOps Tools Comparison](comparison.md) — Side-by-side feature matrix
- [🔄 CI/CD Pipeline](best-practices/cicd-pipeline.md) — Standard pipeline patterns
- [📦 Containerization](best-practices/containerization.md) — Docker best practices
- [🏗️ Infrastructure as Code](best-practices/infrastructure-as-code.md) — When and how to use IaC
- [🗺️ Technology Roadmap](roadmap.md) — Trends & predictions for DevOps

## 🎯 Quick Recommendation for Micro SaaS Solo Developer

| Need | Tool | Why |
|------|------|-----|
| CI/CD | **GitHub Actions** | Already where your code is, free tier generous |
| Local Dev | **Docker Compose** | Postgres + Redis in one command |
| Deployment | **Vercel** | Zero-config, git-push deploy |
| Database | **Supabase** or **Neon** | Managed Postgres, no ops |

**Skip**: Kubernetes, Terraform, Argo CD, Jenkins — overkill for 1 person.

## 🏗️ Repository Structure
```
devops-stack/
├── README.md              ← You are here
├── projects/              ← Individual project analyses (TEMC scored)
├── best-practices/        ← Cross-project patterns
├── code/                  ← Extractable code (coming soon)
├── comparison.md          ← Horizontal comparison tables
├── roadmap.md             ← Technology trends & predictions
├── CONTRIBUTING.md        ← How to contribute
└── SOURCES.md             ← All source links + licenses
```

## License
This repository contains analysis and extracted patterns. See [SOURCES.md](SOURCES.md).
