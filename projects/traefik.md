# Traefik

> The Cloud Native Application Proxy — automatic service discovery and routing

| Metric | Data |
|--------|------|
| GitHub | [traefik/traefik](https://github.com/traefik/traefik) |
| Stars | 62,718 |
| License | MIT |
| Language | Go |
| Last Updated | 2026-04-16 |
| Contributors | 800+ |
| Forks | 5,918 |
| Open Issues | 787 |

## TEMC Score

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T (Tech) | 90 | Go, production-grade, automatic Let's Encrypt, Docker/K8s/Consul provider auto-discovery. Battle-tested at scale |
| E (Ecosystem) | 88 | 63k stars, 800+ contributors, CNCF project, Traefik Labs commercial backing ($100M+ raised) |
| M (Market) | 82 | Cloud-native reverse proxy is essential infrastructure. Competes with Nginx, Caddy, HAProxy |
| C (Combo) | 60 | Overkill as standalone for simple SaaS. But it's built into Coolify and Kamal — you'll use it indirectly |
| **Overall** | **76** | T×0.25 + E×0.20 + M×0.25 + C×0.25 |

## Core Value

Traefik is an edge router that automatically discovers services and routes traffic to them. Its killer feature is **zero-config service discovery**:
- **Docker labels** → Traefik auto-configures routing
- **Automatic HTTPS** via Let's Encrypt
- **Load balancing** with health checks
- **Middleware** — rate limiting, auth, headers, compression
- **Dashboard** — real-time traffic visualization

## Architecture Highlights

- **Providers**: Docker, Kubernetes, Consul, ECS, file-based — Traefik watches for changes
- **Entrypoints**: HTTP (:80), HTTPS (:443), TCP, UDP
- **Routers**: Match rules (Host, Path, Headers) → route to services
- **Middlewares**: Chain of transformations (auth, rate-limit, retry, circuit-breaker)
- **Services**: Backend servers with load balancing
- **Traefik Hub**: Commercial API gateway built on top

## Key Modules

| Module | Description | Extractable? |
|--------|-------------|-------------|
| ACME/Let's Encrypt | Automatic SSL certificate management | ✅ Pattern |
| Docker Provider | Auto-discover containers via Docker socket | ✅ Pattern |
| Middleware Chain | Rate limiting, auth, headers pipeline | ✅ Pattern |
| Health Check | Backend service health monitoring | ✅ Pattern |

## Solo Dev Verdict

**🟡 USE INDIRECTLY** — You won't install Traefik directly. It's already embedded in Coolify and Kamal as the reverse proxy layer. Understanding Traefik's Docker label configuration is useful for debugging deployment issues.

**Key takeaway**: Learn Docker labels for Traefik routing — this knowledge applies anywhere containers are deployed.

## Risks & Counter-Arguments

- **Complexity**: Configuration can be bewildering for beginners (entrypoints, routers, services, middlewares)
- **vs Caddy**: Caddy is simpler for basic reverse proxy with auto-HTTPS
- **vs Nginx**: Nginx has a larger knowledge base and is simpler for static config
- **Memory**: Traefik uses more memory than Nginx for equivalent load
