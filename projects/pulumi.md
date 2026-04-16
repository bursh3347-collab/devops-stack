# Pulumi

> Infrastructure as Code using real programming languages — TypeScript, Python, Go, C#. No DSL, just code.

| Metric | Data |
|--------|------|
| GitHub | [pulumi/pulumi](https://github.com/pulumi/pulumi) |
| Stars | 22,000+ |
| License | Apache-2.0 ✅ |
| Language | Go (engine) + TypeScript/Python/Go/C# (SDKs) |
| Last Updated | Active (daily commits) |
| Contributors | 500+ |
| Backed By | Pulumi Corp ($112M+ funding) |

## TEMC Scoring

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T Technology (×0.25) | 80 | Real programming languages (loops, conditionals, abstractions) instead of HCL/YAML. Multi-cloud (AWS, GCP, Azure, K8s). State management via Pulumi Cloud or self-hosted backends (S3, local). Pulumi AI for natural language IaC |
| E Ecosystem (×0.20) | 72 | Growing but smaller than Terraform. 150+ providers, Pulumi Registry. Active Discord community. But: fewer Stack Overflow answers, fewer blog posts, smaller talent pool |
| M Market (×0.30) | 78 | Developer-first IaC is trending hard. Terraform's BUSL license change pushed users to explore alternatives. TypeScript IaC = natural for full-stack devs. Pulumi AI = next-gen IaC authoring |
| C Combinability (×0.25) | 82 | ⭐ **Perfect for user's stack.** TypeScript SDK means same language for app + infrastructure. Vercel provider exists. Supabase can be managed via Pulumi. No new language to learn — just `npm install @pulumi/aws` |
| **Composite** | **78** | T×0.25 + E×0.20 + M×0.30 + C×0.25 = 20.0 + 14.4 + 23.4 + 20.5 |

## Architecture Highlights

```
┌───────────────────────────────────────┐
│         Your TypeScript Code          │
│  import * as aws from "@pulumi/aws"   │
│  const bucket = new aws.s3.Bucket()   │
└───────────────┬───────────────────────┘
                │ gRPC
┌───────────────▼───────────────────────┐
│         Pulumi Engine (Go)            │
│  ┌─────────┐  ┌────────────────────┐  │
│  │ Differ   │  │ Resource Providers │  │
│  │ (state   │  │ (AWS, GCP, K8s,   │  │
│  │  mgmt)   │  │  Vercel, 150+)    │  │
│  └─────────┘  └────────────────────┘  │
└───────────────┬───────────────────────┘
                │ API calls
        ┌───────┼───────┐
        ▼       ▼       ▼
       AWS     GCP   Vercel
```

**Key Design Decisions:**
- **Real languages**: TypeScript/Python/Go/C# — use IDE autocomplete, type checking, abstractions, testing
- **Component model**: Build reusable infrastructure components like npm packages
- **Pulumi Cloud**: Managed state + secrets + RBAC + deployment history (free for individuals)
- **Import existing**: `pulumi import` can adopt existing cloud resources into Pulumi management

## Extractable Patterns

1. **TypeScript IaC templates** → code-base/deploy/pulumi/ (Vercel + Supabase + AWS S3 setup)
2. **Component abstractions** → Reusable infra components ("SaaS Stack" = DB + Auth + CDN + Monitoring)
3. **Testing IaC** → Unit tests for infrastructure using standard test frameworks (Jest/Vitest)
4. **GitOps with Pulumi** → Pulumi Deployments for git-push infrastructure changes

## Competitive Landscape

| | Pulumi | Terraform | OpenTofu | AWS CDK | SST |
|--|--------|-----------|----------|---------|-----|
| Language | TS/Py/Go/C# | HCL | HCL | TS/Py/Java | TypeScript |
| License | Apache-2.0 ✅ | BUSL-1.1 ⚠️ | MPL-2.0 ✅ | Apache-2.0 ✅ | MIT ✅ |
| Stars | 22K+ | 45K+ | 28K+ | 11K+ | 22K+ |
| Providers | 150+ | 4,000+ | 4,000+ | AWS only | AWS only |
| Multi-cloud | ✅ Yes | ✅ Yes | ✅ Yes | ❌ AWS only | ❌ AWS only |
| Learning Curve | Low (if you know TS) | Medium (HCL) | Medium (HCL) | Medium | Low |
| Best For | Full-stack devs | Enterprise multi-cloud | Terraform refugees | AWS shops | Serverless |

## Solo Dev Verdict

**⭐ Best IaC choice for TypeScript developers.** If you already write TypeScript (which the user does), Pulumi eliminates the need to learn HCL. Same language, same IDE, same testing tools. The free Pulumi Cloud tier handles state management.

**Recommended stack for solo dev:**
```typescript
import * as vercel from "@pulumi/vercel";
import * as supabase from "@pulumi/supabase";

// Your entire infrastructure in 20 lines of TypeScript
```

**When to use:** When you outgrow Vercel's UI-based config, need reproducible multi-environment setups (dev/staging/prod), or want infrastructure version-controlled alongside app code.

**Skip if:** You only deploy to Vercel with git-push — the platform handles infra for you.
