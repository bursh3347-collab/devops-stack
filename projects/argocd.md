# Argo CD

> Declarative GitOps continuous delivery tool for Kubernetes.

| Metric | Data |
|--------|------|
| GitHub | [argoproj/argo-cd](https://github.com/argoproj/argo-cd) |
| Stars | ~19,000 |
| Forks | ~5,500 |
| License | Apache-2.0 |
| Language | Go |
| CNCF | Graduated |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 88 | GitOps model, auto-sync, multi-cluster, RBAC, SSO, health checks |
| E Ecosystem | 82 | CNCF graduated, 19k stars, Argo Workflows/Events/Rollouts ecosystem |
| M Market | 70 | GitOps adoption growing, but requires Kubernetes (not universal) |
| C Combo | 30 | Requires Kubernetes which is overkill for天子's Vercel-based workflow |
| **Overall** | **64** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Argo CD implements GitOps: your Git repository IS your deployment source of truth. Any drift from desired state is automatically corrected.

## Architecture Highlights
- **GitOps**: Git repo = single source of truth
- **Auto-sync**: Detect and reconcile drift
- **Multi-cluster**: Manage deployments across clusters
- **Web UI**: Visual application topology
- **ApplicationSet**: Template-based multi-app management

## Why It Might NOT Be Worth It
- Requires Kubernetes (overkill for solo dev)
- GitOps adds complexity for simple deployments
- Vercel's git-based deployment IS already GitOps
- Only makes sense at scale (10+ services)

## 天子点评
GitOps 理念很棒，但绑定 K8s 就不适合一人公司了。Vercel 的 git-push 部署本质上就是简化版 GitOps。
