# Containerization Best Practices

> Patterns extracted from Docker documentation and high-star projects.

## 1. Multi-Stage Dockerfile for Next.js

```dockerfile
# Stage 1: Dependencies
FROM node:20-alpine AS deps
WORKDIR /app
COPY package.json pnpm-lock.yaml ./
RUN corepack enable pnpm && pnpm install --frozen-lockfile

# Stage 2: Build
FROM node:20-alpine AS builder
WORKDIR /app
COPY --from=deps /app/node_modules ./node_modules
COPY . .
RUN corepack enable pnpm && pnpm build

# Stage 3: Production
FROM node:20-alpine AS runner
WORKDIR /app
ENV NODE_ENV=production
RUN addgroup --system --gid 1001 nodejs
RUN adduser --system --uid 1001 nextjs
COPY --from=builder /app/public ./public
COPY --from=builder --chown=nextjs:nodejs /app/.next/standalone ./
COPY --from=builder --chown=nextjs:nodejs /app/.next/static ./.next/static
USER nextjs
EXPOSE 3000
CMD ["node", "server.js"]
```

## 2. Docker Compose for Local Dev

```yaml
# docker-compose.yml
version: '3.8'
services:
  db:
    image: postgres:16-alpine
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: myapp
    ports:
      - '5432:5432'
    volumes:
      - pgdata:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    ports:
      - '6379:6379'

volumes:
  pgdata:
```

## 3. .dockerignore

```
node_modules
.next
.git
*.md
.env.local
```

## 4. Image Size Optimization

| Approach | Size Reduction |
|----------|---------------|
| Alpine base | ~5x smaller |
| Multi-stage build | ~10x smaller |
| .dockerignore | Variable |
| Next.js standalone | ~80% smaller |

## Sources
- Docker official best practices
- Next.js Docker example
- Node.js Docker best practices guide
