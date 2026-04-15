# Terraform

> Infrastructure as Code tool — define cloud resources in declarative HCL configuration files.

| Metric | Data |
|--------|------|
| GitHub | [hashicorp/terraform](https://github.com/hashicorp/terraform) |
| Stars | ~45,000 |
| Forks | ~10,000 |
| License | BUSL-1.1 (⚠️ Changed from MPL-2.0 in 2023) |
| Language | Go |
| Contributors | 1,800+ |
| Alternative | OpenTofu (Linux Foundation fork, MPL-2.0) |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 90 | Declarative IaC, state management, plan/apply workflow, 4,000+ providers |
| E Ecosystem | 88 | 45k stars, massive provider ecosystem, Terraform Registry, but BUSL controversy |
| M Market | 75 | Enterprise standard for IaC, but OpenTofu fork + Pulumi/CDK alternatives growing |
| C Combo | 45 | IaC is overkill for Vercel deployment; useful if managing AWS/GCP directly |
| **Overall** | **72** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Terraform lets you define your entire cloud infrastructure (servers, databases, networks, DNS) in version-controlled code files. Plan changes before applying them.

## Architecture Highlights
- **HCL**: HashiCorp Configuration Language
- **Provider System**: 4,000+ providers (AWS, GCP, Azure, Cloudflare...)
- **State Management**: Track real-world resource state
- **Plan/Apply**: Preview changes before execution
- **Modules**: Reusable infrastructure components

## Key Patterns
1. **Module composition**: Reusable infrastructure blocks
2. **Remote state**: Shared state in S3/Terraform Cloud
3. **Workspaces**: Environment isolation (dev/staging/prod)
4. **Data sources**: Reference existing infrastructure

⚠️ **License Warning**: Changed to BUSL-1.1 in Aug 2023. Consider OpenTofu for new projects.

## Why It Might NOT Be Worth It
- BUSL-1.1 license concerns for commercial use
- Overkill for Vercel-deployed Micro SaaS
- State management complexity
- HCL learning curve
- Solo developer doesn't need IaC — click-ops is faster for 1-2 services

## 天子点评
IaC 标杆工具，但 BUSL 协议是大坑。一人公司用 Vercel 根本不需要 IaC。如果未来管 AWS，优先选 OpenTofu。
