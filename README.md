![Stars](https://img.shields.io/github/stars/bursh3347-collab/devops-stack?style=flat-square)
![License](https://img.shields.io/github/license/bursh3347-collab/devops-stack?style=flat-square)
![Last Commit](https://img.shields.io/github/last-commit/bursh3347-collab/devops-stack?style=flat-square)

[English](README.md) | [中文](README_CN.md)

# 🛠️ devops-stack

> ⭐ Maturity: **L1 Growing** — 7 projects analyzed, comparison complete, best practices started.

DevOps and CI/CD tools curated for solo developers. Deep analysis, comparison, and **TEMC scoring** (Technology · Ecosystem · Market Timing · Combinability) of 7 high-star projects — with practical best practices you can actually use.

Part of the [Open Source Knowledge Restructuring Project](https://github.com/bursh3347-collab).

## 📈 Trending This Week (Updated: 2026-04-15)

| Rank | Project | Stars | Weekly Δ | Trend |
|------|---------|-------|----------|-------|
| 1 | [Kubernetes](https://github.com/kubernetes/kubernetes) | 115k | +300 | → |
| 2 | [Docker](https://github.com/moby/moby) | 73k | +150 | → |
| 3 | [Terraform](https://github.com/hashicorp/terraform) | 45k | +100 | → |
| 4 | [GitLab CI](https://github.com/gitlabhq/gitlabhq) | 24k | +50 | → |
| 5 | [Jenkins](https://github.com/jenkinsci/jenkins) | 23k | +30 | ↓ |
| 6 | [Argo CD](https://github.com/argoproj/argo-cd) | 19k | +80 | ↑ |
| 7 | GitHub Actions | N/A | N/A | 🚀 |

> 🌟 GitHub Actions has no open-source repo but holds #1 market share (33%+). Argo CD steadily growing in the GitOps space.

## 📊 Project Rankings (by TEMC Score)

| Rank | Project | Stars | TEMC | Language | Category |
|------|---------|-------|------|----------|----------|
| 1 | [GitHub Actions](projects/github-actions.md) | N/A | **91** | YAML | CI/CD |
| 2 | [Docker](projects/docker.md) | ~73k | **85** | Go | Containers |
| 3 | [Kubernetes](projects/kubernetes.md) | ~115k | **73** | Go | Orchestration |
| 4 | [Terraform](projects/terraform.md) | ~45k | **72** | Go | IaC |
| 5 | [GitLab CI](projects/gitlab-ci.md) | ~24k | **66** | Ruby | CI/CD |
| 6 | [Argo CD](projects/argocd.md) | ~19k | **64** | Go | GitOps |
| 7 | [Jenkins](projects/jenkins.md) | ~23k | **55** | Java | CI/CD |

> **TEMC** = Technology (25%) + Ecosystem (20%) + Market Timing (30%) + Combinability (25%)

## 📋 What's Inside

- [📊 DevOps Tools Comparison](comparison.md) — Side-by-side feature matrix
- [🔄 CI/CD Pipeline Patterns](best-practices/cicd-pipeline.md) — Standard pipeline architectures
- [📦 Containerization Best Practices](best-practices/containerization.md) — Docker done right
- [🏗️ Infrastructure as Code](best-practices/infrastructure-as-code.md) — When and how to use IaC
- [🗺️ Technology Roadmap](roadmap.md) — Trends & predictions for DevOps

## 🏆 Solo Dev Verdict

| Need | Pick | Why |
|------|------|-----|
| CI/CD | **GitHub Actions** | Already where your code lives, generous free tier |
| Local Dev | **Docker Compose** | Postgres + Redis in one command |
| Deployment | **Vercel** | Zero-config, git-push deploy |
| Database | **Supabase** or **Neon** | Managed Postgres, zero ops |

**Skip for solo work**: Kubernetes, Terraform, Argo CD, Jenkins — overkill for a one-person team.

## 📂 Structure

```
devops-stack/
├── projects/              ← Individual project deep-dives (TEMC scored)
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
