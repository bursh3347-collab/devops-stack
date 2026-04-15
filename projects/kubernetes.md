# Kubernetes

> Container orchestration platform — the operating system of the cloud.

| Metric | Data |
|--------|------|
| GitHub | [kubernetes/kubernetes](https://github.com/kubernetes/kubernetes) |
| Stars | ~115,000 |
| Forks | ~40,000 |
| License | Apache-2.0 |
| Language | Go |
| Contributors | 3,800+ |
| CNCF | Graduated |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 95 | Industry standard, declarative, self-healing, auto-scaling, massive extensibility |
| E Ecosystem | 98 | 115k stars, CNCF graduated, every cloud has managed K8s (EKS/GKE/AKS) |
| M Market | 80 | Enterprise standard, but massive complexity; alternatives exist for small teams |
| C Combo | 35 | Overkill for Micro SaaS one-person company, Vercel is the right abstraction layer |
| **Overall** | **73** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Kubernetes is the universal API for deploying, scaling, and managing containerized applications. It's the "Linux of the cloud" — the platform everything else runs on.

## Architecture Highlights
- **Control Plane**: API server, scheduler, controller manager, etcd
- **Worker Nodes**: kubelet, kube-proxy, container runtime
- **Declarative**: Desired state in YAML, K8s reconciles
- **Self-healing**: Automatic restart, rescheduling, scaling
- **Extensible**: CRDs, operators, service mesh integration

## Key Concepts
1. **Pod**: Smallest deployable unit
2. **Deployment**: Managed ReplicaSet with rolling updates
3. **Service**: Network abstraction (ClusterIP/LoadBalancer)
4. **Ingress**: HTTP routing
5. **ConfigMap/Secret**: Configuration management

## Why It Might NOT Be Worth It
- **Massively overkill** for solo developer / Micro SaaS
- Steep learning curve (months to master)
- Operational overhead (even managed K8s)
- Cost: minimum ~$70/month for managed cluster
- Vercel/Railway/Fly.io solve the same problems with zero K8s knowledge

## 天子点评
云计算操作系统，技术上无可挑剔。但一人公司绝对不要碰——Vercel 就是你的 K8s。了解概念即可，不要实操。
