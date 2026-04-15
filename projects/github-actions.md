# GitHub Actions

> CI/CD platform built into GitHub — the most adopted CI/CD solution (33%+ market share).

| Metric | Data |
|--------|------|
| Platform | [github.com/features/actions](https://github.com/features/actions) |
| Market Share | ~33% (largest CI/CD platform) |
| License | Proprietary (free tier: 2,000 min/month) |
| Language | YAML workflows |
| Marketplace | 20,000+ community actions |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 85 | Matrix builds, reusable workflows, composite actions, OIDC federation |
| E Ecosystem | 95 | 20k+ marketplace actions, native GitHub integration, de facto standard |
| M Market | 90 | 33% market share, free for public repos, most new projects default to it |
| C Combo | 95 | Already used by天子(bursh3347-collab), native to GitHub workflow |
| **Overall** | **91** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Zero-config CI/CD that lives where your code already is. No separate service to manage. Trigger on any GitHub event (push, PR, issue, schedule, dispatch).

## Architecture Highlights
- **Event-driven**: Triggered by 40+ GitHub events
- **Workflow YAML**: Declarative pipeline definition
- **Runners**: GitHub-hosted (Ubuntu/macOS/Windows) or self-hosted
- **Marketplace**: 20k+ reusable actions
- **Matrix Strategy**: Parallel testing across versions/OS
- **OIDC**: Keyless auth to cloud providers (AWS/GCP/Azure)

## Key Patterns
1. **CI Pipeline**: lint → test → build → deploy
2. **Matrix Testing**: Test across Node 18/20/22 × OS
3. **Reusable Workflows**: DRY pipeline definitions
4. **Environment Protection**: Manual approvals for production
5. **Caching**: npm/pnpm cache for faster builds

## Extractable Components
- Standard CI/CD workflow templates → code-base/deploy/ci-cd/
- OIDC federation patterns → code-base/deploy/auth/
- Caching strategies → code-base/deploy/caching/

⭐ Universal Code Candidate: CI/CD workflow templates for TypeScript projects

## Why It Might NOT Be Worth It
- Vendor lock-in to GitHub
- YAML debugging is painful
- Minutes-based pricing can spike
- Complex workflows become unwieldy
- Self-hosted runners require infrastructure

## 天子点评
一人公司 CI/CD 唯一选择，不需要考虑其他。代码在 GitHub，CI/CD 也在 GitHub，零摩擦。免费额度完全够用。
