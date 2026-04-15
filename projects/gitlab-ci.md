# GitLab CI/CD

> Integrated CI/CD platform within GitLab — one platform for source code, CI/CD, and DevOps.

| Metric | Data |
|--------|------|
| GitHub | [gitlabhq/gitlabhq](https://github.com/gitlabhq/gitlabhq) |
| Stars | ~24,000 |
| License | MIT (CE) / Proprietary (EE) |
| Language | Ruby |
| Market Share | ~20% CI/CD market |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 85 | Integrated platform, Auto DevOps, DAST/SAST built-in, container registry |
| E Ecosystem | 78 | Strong enterprise adoption, self-hosted option, but smaller than GitHub ecosystem |
| M Market | 70 | Strong #2 to GitHub, popular in enterprise/self-hosted, less common in indie |
| C Combo | 40 | 天子 uses GitHub, switching cost high; GitLab CI only useful on GitLab repos |
| **Overall** | **66** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
GitLab CI is the most integrated DevOps platform — source code, CI/CD, container registry, SAST/DAST, monitoring all in one tool.

## Architecture Highlights
- **.gitlab-ci.yml**: Pipeline definition
- **Stages**: Sequential pipeline phases
- **Jobs**: Parallel execution within stages
- **Auto DevOps**: Zero-config CI/CD
- **Built-in Security**: SAST, DAST, dependency scanning

## Why It Might NOT Be Worth It
- Requires GitLab (天子 uses GitHub)
- Competing ecosystem, not composable with GitHub Actions
- Self-hosted GitLab is resource-heavy
- Free tier limitations increasing

## 天子点评
好产品但用不上——天子在 GitHub 生态。功能比 GitHub Actions 更全面，但切换成本太高。了解即可。
