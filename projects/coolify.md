# Coolify

> Open-source, self-hostable PaaS alternative to Vercel, Heroku & Netlify

| Metric | Data |
|--------|------|
| GitHub | [coollabsio/coolify](https://github.com/coollabsio/coolify) |
| Stars | 53,476 |
| License | Apache-2.0 |
| Language | PHP (Laravel) |
| Last Updated | 2026-04-16 |
| Contributors | 400+ |
| Forks | 4,129 |
| Open Issues | 724 |

## TEMC Score

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T (Tech) | 82 | Laravel + Svelte 5 frontend, Docker-native, supports 280+ one-click services. Solid but PHP limits TypeScript ecosystem fit |
| E (Ecosystem) | 88 | 53k+ stars, very active community, frequent releases on v4.x branch, 400+ contributors |
| M (Market) | 90 | Self-hosting boom post-Heroku sunset, massive demand for PaaS alternatives. Vercel/Railway pricing pushes devs to self-host |
| C (Combo) | 85 | Directly usable for deploying Micro SaaS apps. One-click Supabase/Postgres/Redis. Perfect for solo dev infrastructure |
| **Overall** | **82** | T×0.25 + E×0.20 + M×0.25 + C×0.25 |

## Core Value

Coolify is the most complete open-source PaaS for self-hosting. It turns any VPS ($5-20/month) into a full deployment platform with:
- **Git push deploy** — connect GitHub/GitLab, auto-deploy on push
- **280+ one-click services** — databases, monitoring, analytics, CMS
- **SSL/domains** — automatic Let's Encrypt certificates
- **Docker-native** — everything runs in containers
- **Team features** — multi-user with RBAC

## Architecture Highlights

- **Frontend**: Svelte 5 + Inertia.js (SPA-like feel with server rendering)
- **Backend**: Laravel 11 (PHP 8.3+)
- **Infra**: Docker Compose orchestration, SSH-based remote server management
- **Database**: PostgreSQL for app data, Redis for queues
- **Key Pattern**: Agent-based architecture — Coolify agent runs on each managed server

## Key Modules

| Module | Description | Extractable? |
|--------|-------------|-------------|
| Docker Compose Generator | Generates compose files from UI config | ⚠️ PHP-specific |
| Git Webhook Handler | Processes push events for auto-deploy | ✅ Pattern reusable |
| SSL/Domain Manager | Let's Encrypt automation | ✅ Useful pattern |
| One-Click Templates | 280+ service definitions | ✅ YAML/JSON configs |
| Server Agent | Remote server management via SSH | ⚠️ Complex |

## Solo Dev Verdict

**🟢 USE IT** — If you have a VPS ($5-20/month Hetzner/DigitalOcean), Coolify replaces Vercel + Railway + database hosting. Saves $50-200/month at scale. 30-minute setup. The PHP backend doesn't matter — you're using it as a platform, not extending it.

**ROI**: $5 VPS + Coolify vs $20+ Vercel Pro + $25+ Railway = **saves $40+/month from day 1**.

## Risks & Counter-Arguments

- **PHP backend**: If you need to customize deeply, PHP is outside your TypeScript stack
- **Single point of failure**: Self-hosted = you manage uptime. Coolify v4 adds multi-server, but still your responsibility
- **Learning curve**: Docker knowledge required for debugging
- **vs Vercel**: Vercel's edge network and DX are hard to beat for frontend-heavy apps
