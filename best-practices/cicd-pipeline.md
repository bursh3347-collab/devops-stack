# CI/CD Pipeline Best Practices

> Patterns extracted from GitHub Actions, GitLab CI, and Jenkins workflows.

## 1. Standard TypeScript CI Pipeline

```yaml
# .github/workflows/ci.yml
name: CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  lint-and-test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: pnpm/action-setup@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'pnpm'
      - run: pnpm install --frozen-lockfile
      - run: pnpm lint
      - run: pnpm type-check
      - run: pnpm test
      - run: pnpm build

  deploy:
    needs: lint-and-test
    if: github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      # Vercel auto-deploys on push, so this is optional
      # Add manual deployment steps if needed
```

## 2. Pipeline Stages

```
┌─────────┐  ┌──────────┐  ┌─────────┐  ┌──────────┐  ┌─────────┐
│  Lint   │→ │  Type    │→ │  Test   │→ │  Build  │→ │ Deploy  │
│         │  │  Check   │  │         │  │         │  │         │
└─────────┘  └──────────┘  └─────────┘  └──────────┘  └─────────┘
```

## 3. Caching Strategy

```yaml
- uses: actions/cache@v4
  with:
    path: |
      ~/.pnpm-store
      node_modules/.cache
    key: $ runner.os -pnpm-$ hashFiles('pnpm-lock.yaml') 
    restore-keys: |
      $ runner.os -pnpm-
```

## 4. Branch Protection Rules

- Require PR reviews before merge
- Require status checks to pass
- Require branches to be up to date
- No force pushes to main

## 5. Secrets Management

- Use GitHub Actions Secrets (Settings → Secrets)
- Use OIDC for cloud provider auth (no long-lived keys)
- Never log secrets in CI output
- Rotate secrets quarterly

## Sources
- GitHub Actions documentation
- Vercel deployment best practices
- pnpm CI/CD guide
