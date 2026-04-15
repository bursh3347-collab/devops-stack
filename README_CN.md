[English](README.md) | [中文](README_CN.md)

# 🛠️ devops-stack

> ⭐ 成熟度: **L1 成长期** — 已分析 7 个项目，对比表完成，最佳实践进行中。

为独立开发者策展的 DevOps 与 CI/CD 工具集。对 7 个高星项目的深度分析、横向对比与 **TEMC 评分**（技术 · 生态 · 时机 · 组合），附带你能直接用的实战最佳实践。

属于 [GitHub 开源知识重组工程](https://github.com/bursh3347-collab) 的一部分。

## 📈 本分类飙升榜（最近更新：2026-04-15）

| 排名 | 项目 | 总Stars | 周增 | 趋势 |
|------|------|---------|------|------|
| 1 | [Kubernetes](https://github.com/kubernetes/kubernetes) | 115k | +300 | → |
| 2 | [Docker](https://github.com/moby/moby) | 73k | +150 | → |
| 3 | [Terraform](https://github.com/hashicorp/terraform) | 45k | +100 | → |
| 4 | [GitLab CI](https://github.com/gitlabhq/gitlabhq) | 24k | +50 | → |
| 5 | [Jenkins](https://github.com/jenkinsci/jenkins) | 23k | +30 | ↓ |
| 6 | [Argo CD](https://github.com/argoproj/argo-cd) | 19k | +80 | ↑ |
| 7 | GitHub Actions | N/A | N/A | 🚀 |

> 🌟 GitHub Actions 无开源仓库但市场份额第一（33%+）。Argo CD 在 GitOps 领域稳步增长。

## 📊 项目排名（按 TEMC 评分）

| 排名 | 项目 | Stars | TEMC | 语言 | 分类 |
|------|------|-------|------|------|------|
| 1 | [GitHub Actions](projects/github-actions.md) | N/A | **91** | YAML | CI/CD |
| 2 | [Docker](projects/docker.md) | ~73k | **85** | Go | 容器化 |
| 3 | [Kubernetes](projects/kubernetes.md) | ~115k | **73** | Go | 编排 |
| 4 | [Terraform](projects/terraform.md) | ~45k | **72** | Go | 基础设施即代码 |
| 5 | [GitLab CI](projects/gitlab-ci.md) | ~24k | **66** | Ruby | CI/CD |
| 6 | [Argo CD](projects/argocd.md) | ~19k | **64** | Go | GitOps |
| 7 | [Jenkins](projects/jenkins.md) | ~23k | **55** | Java | CI/CD |

> **TEMC** = 技术分(25%) + 生态分(20%) + 时机分(30%) + 组合分(25%)

## 📋 仓库内容

- [📊 DevOps 工具横向对比](comparison.md) — 功能矩阵一览
- [🔄 CI/CD 流水线模式](best-practices/cicd-pipeline.md) — 标准流水线架构
- [📦 容器化最佳实践](best-practices/containerization.md) — Docker 正确用法
- [🏗️ 基础设施即代码](best-practices/infrastructure-as-code.md) — 何时使用、如何使用 IaC
- [🗺️ 技术路线图](roadmap.md) — DevOps 趋势与预测

## 🏆 天子点评（一人公司推荐）

| 需求 | 推荐 | 理由 |
|------|------|------|
| CI/CD | **GitHub Actions** | 代码就在这里，免费额度充足 |
| 本地开发 | **Docker Compose** | 一条命令启动 Postgres + Redis |
| 部署 | **Vercel** | 零配置，git push 即部署 |
| 数据库 | **Supabase** 或 **Neon** | 托管 Postgres，零运维 |

**一人公司可跳过**：Kubernetes、Terraform、Argo CD、Jenkins — 对个人开发者来说过度复杂。

## 📂 仓库结构

```
devops-stack/
├── projects/              ← 单个项目深度分析（含 TEMC 评分）
├── best-practices/        ← 跨项目最佳实践
├── code/                  ← 可提取代码（即将上线）
├── comparison.md          ← 横向对比表
├── roadmap.md             ← 技术趋势与预测
├── CONTRIBUTING.md
├── SOURCES.md
└── README.md
```

## 📝 使用指南

1. **对比** — 从 [comparison.md](comparison.md) 开始了解全景
2. **深入** — 阅读 `projects/` 中你选择的工具分析
3. **实践** — 将 `best-practices/` 中的模式应用到你的工作流
4. **跟进** — 查看 [roadmap.md](roadmap.md) 了解 DevOps 发展方向

## License

分析内容采用 MIT 协议。各项目保留其原始开源协议 — 详见 [SOURCES.md](SOURCES.md)。
