# Infrastructure as Code Best Practices

> When you outgrow Vercel, these patterns will help.

## 1. When Do You Need IaC?

| Stage | Infrastructure | IaC Needed? |
|-------|---------------|-------------|
| MVP / Solo | Vercel + Supabase | ❌ No |
| Growing (10-100 users) | + Custom domain + CDN | ❌ No (platform handles it) |
| Scaling (100-1000) | + Redis + Queue + Workers | ⚠️ Maybe (Docker Compose) |
| Enterprise (1000+) | + Multi-region + Custom VPC | ✅ Yes (Terraform/Pulumi) |

**For Micro SaaS solo developer: You probably never need IaC.**

## 2. If You Do Need IaC

### Choose Your Tool
- **Terraform**: Industry standard, HCL language, BUSL-1.1 license ⚠️
- **OpenTofu**: Terraform fork, MPL-2.0 (truly open source)
- **Pulumi**: Write IaC in TypeScript/Python/Go (天子 would prefer this)
- **SST (Serverless Stack)**: TypeScript IaC specifically for serverless apps

### Recommendation
If天子 needs IaC: **SST or Pulumi** (TypeScript-native, matches基准栈)

## 3. Key Principles

1. **Everything in code**: No manual cloud console changes
2. **State is sacred**: Never manually edit state files
3. **Environments as code**: dev/staging/prod as separate configs
4. **Secrets separate**: Use environment variables or secret managers
5. **Plan before apply**: Always review changes before executing

## Sources
- Terraform best practices guide
- Pulumi TypeScript examples
- SST documentation
