# Jenkins

> Classic open-source CI/CD automation server — the grandfather of all CI/CD tools.

| Metric | Data |
|--------|------|
| GitHub | [jenkinsci/jenkins](https://github.com/jenkinsci/jenkins) |
| Stars | ~23,000 |
| Forks | ~8,800 |
| License | MIT |
| Language | Java |
| Contributors | 700+ |
| Plugin Ecosystem | 1,800+ plugins |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 72 | Mature, extensible via plugins, but Java-heavy and aging architecture |
| E Ecosystem | 75 | 1,800+ plugins, huge enterprise adoption, but community declining |
| M Market | 55 | Legacy enterprise tool, new projects choose GitHub Actions/GitLab CI |
| C Combo | 25 | Java server, self-hosted, massive overhead for solo developer |
| **Overall** | **55** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Jenkins pioneered CI/CD automation. 1,800+ plugins mean it can integrate with virtually anything. Still the backbone of many enterprise CI/CD pipelines.

## Why It Might NOT Be Worth It
- Self-hosted Java server (maintenance overhead)
- Groovy Jenkinsfile is painful
- Security vulnerabilities are common
- GitHub Actions/GitLab CI are better for new projects
- Declining community momentum
