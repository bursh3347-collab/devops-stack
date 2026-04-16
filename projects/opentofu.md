# OpenTofu

> Open-source Terraform fork, maintained by the Linux Foundation

| Metric | Data |
|--------|------|
| GitHub | [opentofu/opentofu](https://github.com/opentofu/opentofu) |
| Stars | 28,388 |
| License | MPL-2.0 |
| Language | Go |
| Last Updated | 2026-04-16 |
| Contributors | 300+ |
| Forks | 1,208 |
| Open Issues | 323 |

## TEMC Score

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T (Tech) | 88 | Go codebase, 100% Terraform-compatible, added state encryption and client-side functions. Production-grade IaC |
| E (Ecosystem) | 82 | 28k stars, Linux Foundation backing, 140+ companies in OpenTofu Manifesto. All Terraform providers compatible |
| M (Market) | 85 | HashiCorp BUSL license change drove massive migration demand. OpenTofu is the community answer |
| C (Combo) | 65 | Powerful but overkill for solo dev Micro SaaS. Relevant if managing multi-cloud or complex infrastructure |
| **Overall** | **76** | T×0.25 + E×0.20 + M×0.25 + C×0.25 |

## Core Value

OpenTofu is the community fork of Terraform after HashiCorp switched to BUSL-1.1. It's 100% compatible with Terraform but adds:
- **State encryption** — encrypt state files at rest (Terraform doesn't have this)
- **Client-side functions** — run functions without sending data to HashiCorp
- **MPL-2.0 license** — truly open source, no BUSL restrictions
- **Linux Foundation governance** — neutral, community-driven

## Architecture Highlights

- **Core**: Go, HCL (HashiCorp Configuration Language) parser
- **Provider ecosystem**: 3,000+ Terraform providers work unmodified
- **State management**: Local, S3, GCS, Azure Blob, Consul, etc.
- **New features**: `tofu encrypt` for state, `removed` block for safe resource deletion
- **Registry**: registry.opentofu.org (mirrors Terraform registry)

## Solo Dev Verdict

**🟡 SKIP FOR NOW** — For a solo dev using Vercel + Supabase, you don't need IaC. Your infrastructure is managed by platforms. OpenTofu becomes relevant when you:
- Manage 5+ cloud resources manually
- Need reproducible multi-environment setups (staging/prod)
- Hit Coolify's limits and need bare-metal orchestration

**When to revisit**: When you have paying customers and need staging + production parity.

## Risks & Counter-Arguments

- **Complexity tax**: IaC adds significant overhead for simple deployments
- **Terraform compatibility risk**: HashiCorp may diverge the API, breaking compatibility
- **vs CDK/Pulumi**: TypeScript developers may prefer Pulumi (write IaC in TS) over HCL
- **Overkill**: For `vercel deploy` or `coolify push`, OpenTofu is a sledgehammer for a nail
