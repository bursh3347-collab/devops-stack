# Caddy

> The web server with automatic HTTPS — zero-config TLS certificates for every site.

| Metric | Data |
|--------|------|
| GitHub | [caddyserver/caddy](https://github.com/caddyserver/caddy) |
| Stars | 60,000+ |
| License | Apache-2.0 ✅ |
| Language | Go |
| Last Updated | Active (weekly commits) |
| Contributors | 400+ |
| Backed By | Ardan Labs + community |

## TEMC Scoring

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T Technology (×0.25) | 82 | Automatic HTTPS via Let's Encrypt/ZeroSSL (zero config). Single binary, no dependencies. Caddyfile (simple) or JSON config (powerful). HTTP/3 support. Reverse proxy, file server, load balancer in one. Go = memory-safe, fast |
| E Ecosystem (×0.20) | 78 | 400+ contributors, growing plugin ecosystem. Active community forum. Smaller than Nginx/Apache ecosystem but higher quality per-plugin. Official Docker image. Caddy modules registry |
| M Market (×0.30) | 75 | Simplicity trend is strong — developers want zero-config TLS. Growing adoption as Nginx alternative. Cloud-native friendly. But: Nginx still dominates (67% market share), enterprise adoption slower |
| C Combinability (×0.25) | 80 | ⭐ Perfect for solo dev self-hosting. Automatic HTTPS eliminates certbot/renewal headaches. Simple reverse proxy for multiple services. Pairs with Coolify, Docker Compose. Single Caddyfile = entire routing config |
| **Composite** | **79** | T×0.25 + E×0.20 + M×0.30 + C×0.25 = 20.5 + 15.6 + 22.5 + 20.0 |

## Architecture Highlights

```
┌──────────────────────────────────────┐
│            Caddy Server              │
│  ┌────────────┐  ┌───────────────┐   │
│  │ TLS Auto   │  │ Reverse Proxy │   │
│  │ (ACME/     │  │ (load balance │   │
│  │  ZeroSSL)  │  │  + headers)   │   │
│  └────────────┘  └───────────────┘   │
│  ┌────────────┐  ┌───────────────┐   │
│  │ File Server│  │ Plugin System │   │
│  │ (static)   │  │ (modules)     │   │
│  └────────────┘  └───────────────┘   │
└──────────────────────────────────────┘
         │ automatic HTTPS
         ▼
    Let's Encrypt / ZeroSSL
```

**Key Design Decisions:**
- **HTTPS by default**: Every site gets automatic TLS — no certbot, no cron jobs, no renewal scripts
- **Caddyfile simplicity**: 
  ```
  myapp.com {
      reverse_proxy localhost:3000
  }
  ```
  That's it. Automatic HTTPS, HTTP/2, HTTP/3.
- **Single binary**: Download, run, done. No package managers, no dependencies
- **Hot reload**: Change config without dropping connections (`caddy reload`)

## Extractable Patterns

1. **Reverse proxy config** → code-base/deploy/caddy/ (multi-service routing with auto-TLS)
2. **Docker Compose + Caddy** → Production-ready setup for self-hosted SaaS
3. **Wildcard TLS** → Automatic wildcard certs for multi-tenant SaaS (`*.myapp.com`)
4. **Security headers** → Pre-configured security headers template (HSTS, CSP, X-Frame-Options)

## Competitive Landscape

| | Caddy | Nginx | Traefik | Apache | HAProxy |
|--|-------|-------|---------|--------|---------|
| Auto HTTPS | ✅ Built-in | ❌ Manual | ✅ Built-in | ❌ Manual | ❌ Manual |
| Config | Caddyfile | nginx.conf | YAML/Labels | httpd.conf | haproxy.cfg |
| Language | Go | C | Go | C | C |
| Stars | 60K+ | N/A (not on GH) | 52K+ | N/A | N/A |
| License | Apache-2.0 ✅ | BSD-2 ✅ | MIT ✅ | Apache-2.0 ✅ | GPL-2.0 ⚠️ |
| Learning Curve | Very Low | Medium | Medium | High | High |
| Best For | Simple hosting | High performance | Kubernetes/Docker | Legacy | TCP/UDP LB |
| HTTP/3 | ✅ | ✅ (experimental) | ✅ | ❌ | ❌ |

## Solo Dev Verdict

**⭐ Best choice for self-hosted deployments.** If you're running anything on a VPS (Hetzner, DigitalOcean), Caddy eliminates all TLS complexity. Three lines of config = production-ready reverse proxy with automatic HTTPS.

**The killer combo for solo devs:**
```yaml
# docker-compose.yml
services:
  caddy:
    image: caddy:latest
    ports: ["80:80", "443:443"]
    volumes:
      - ./Caddyfile:/etc/caddy/Caddyfile
  app:
    image: your-nextjs-app
```

**When to use:** Self-hosted SaaS, VPS deployments, staging environments, multi-service routing. Caddy vs Traefik: pick Caddy for simplicity, Traefik for Kubernetes-native service mesh.

**Skip if:** You're on Vercel/Railway/Fly.io — they handle TLS for you.
