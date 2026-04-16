# Kamal

> Deploy web apps anywhere with zero-downtime deploys, from Basecamp (DHH)

| Metric | Data |
|--------|------|
| GitHub | [basecamp/kamal](https://github.com/basecamp/kamal) |
| Stars | 14,056 |
| License | MIT |
| Language | Ruby |
| Last Updated | 2026-04-16 |
| Contributors | 100+ |
| Forks | 699 |
| Open Issues | 126 |

## TEMC Score

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T (Tech) | 80 | Clean Ruby codebase, Docker + SSH based, zero-downtime via rolling deploy. Simple but effective |
| E (Ecosystem) | 72 | 14k stars, backed by DHH/37signals. Strong Ruby community, growing adoption outside Rails |
| M (Market) | 78 | "Leave the cloud" movement growing. Kamal 2 simplified multi-server deploys significantly |
| C (Combo) | 70 | Ruby tooling — not directly in TypeScript stack. But the deployment pattern (Docker + SSH + Traefik) is universal |
| **Overall** | **71** | T×0.25 + E×0.20 + M×0.25 + C×0.25 |

## Core Value

Kamal deploys Docker containers to any server (VPS, bare metal, cloud) with zero downtime. Created by DHH as the tool behind HEY and Basecamp's "cloud exit" saving $7M/year.

- **Zero-downtime deploys** via Traefik load balancer
- **Multi-server** — deploy to multiple hosts simultaneously
- **No Kubernetes needed** — just Docker + SSH
- **Rolling deploys** with health checks
- **Accessories** — manage databases, Redis alongside app

## Architecture Highlights

- **Core**: Ruby gem wrapping Docker + SSH commands
- **Proxy**: Traefik (previously nginx) handles routing and SSL
- **Deploy flow**: Build → Push to registry → Pull on servers → Health check → Switch traffic
- **Config**: Single `config/deploy.yml` file
- **Kamal 2**: Simplified proxy management, boot-level integration

## Solo Dev Verdict

**🟡 LEARN THE PATTERN** — Kamal's Docker + SSH + Traefik pattern is gold, but the Ruby tooling adds friction for a TypeScript developer. Better to understand the deployment model and use Coolify (which does the same thing with a UI) or replicate the pattern with shell scripts.

**Key takeaway**: The deploy.yml → Docker build → SSH deploy → Traefik routing pipeline is a production-proven pattern worth studying.

## Risks & Counter-Arguments

- **Ruby dependency**: Requires Ruby runtime for the CLI tool
- **DHH-centric**: Heavily opinionated toward Rails conventions
- **vs Coolify**: Coolify offers the same Docker-on-VPS pattern with a web UI
- **vs Vercel**: For Next.js apps, Vercel's integration is vastly simpler
