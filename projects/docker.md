# Docker

> Container runtime and toolchain — the universal standard for application packaging and deployment.

| Metric | Data |
|--------|------|
| GitHub | [moby/moby](https://github.com/moby/moby) |
| Stars | ~73,000 |
| Forks | ~26,000 |
| License | Apache-2.0 |
| Language | Go |
| Contributors | 2,000+ |

## TEMC Score

| Dimension | Score | Reasoning |
|-----------|-------|-----------|
| T Tech | 90 | Container standard, BuildKit, multi-stage builds, Docker Compose for local dev |
| E Ecosystem | 95 | Universal adoption, Docker Hub (8M+ images), every cloud supports Docker |
| M Market | 85 | Mature and stable, essential infrastructure, but serverless reducing direct usage |
| C Combo | 75 | Useful for local dev (Supabase/Postgres), but Vercel deployment doesn't require Docker |
| **Overall** | **85** | T×0.25 + E×0.20 + M×0.30 + C×0.25 |

## Core Value
Docker packages applications into portable containers that run identically everywhere. "It works on my machine" → "It works everywhere."

## Architecture Highlights
- **Docker Engine**: Container runtime (containerd + runc)
- **Dockerfile**: Declarative image build specification
- **Docker Compose**: Multi-container local development
- **BuildKit**: Next-gen build engine (parallel, cached)
- **Docker Hub**: Container image registry

## Key Patterns
1. **Multi-stage build**: Minimize image size
2. **Docker Compose for dev**: Postgres + Redis + App in one command
3. **.dockerignore**: Exclude unnecessary files
4. **Layer caching**: Order Dockerfile for optimal cache hits
5. **Non-root user**: Security best practice

## Extractable Components
- Multi-stage Dockerfile templates → code-base/deploy/docker/
- Docker Compose dev stacks → code-base/deploy/docker-compose/

⭐ Universal Code Candidate: Dockerfile templates, Docker Compose dev stacks

## Why It Might NOT Be Worth It
- Serverless platforms (Vercel) abstract away containers
- Docker Desktop licensing ($5/user/month for business)
- Resource overhead for solo developer
- Complexity for simple deployments
