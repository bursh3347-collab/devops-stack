# Act

> Run your GitHub Actions locally 🚀

| Metric | Data |
|--------|------|
| GitHub | [nektos/act](https://github.com/nektos/act) |
| Stars | 69,884 |
| License | MIT |
| Language | Go |
| Last Updated | 2026-04-16 |
| Contributors | 300+ |
| Forks | 1,911 |
| Open Issues | 319 |

## TEMC Score

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| T (Tech) | 85 | Go binary, parses GitHub Actions YAML, runs workflows in Docker containers locally. Fast iteration |
| E (Ecosystem) | 90 | 70k stars — one of the most popular DevOps tools on GitHub. Massive community adoption |
| M (Market) | 88 | Every developer using GitHub Actions needs local testing. CI minutes are expensive ($0.008/min) |
| C (Combo) | 90 | Directly useful for solo dev. Test CI pipelines before pushing. Save GitHub Actions minutes. Debug locally |
| **Overall** | **84** | T×0.25 + E×0.20 + M×0.25 + C×0.25 |

## Core Value

Act runs GitHub Actions workflows on your local machine using Docker. This means:
- **Fast feedback** — test CI changes in seconds, not minutes
- **Save money** — don't burn GitHub Actions minutes on broken workflows
- **Offline development** — test CI/CD without internet
- **Debug locally** — step through workflow failures with local Docker

## How It Works

```bash
# Run the default event (push)
act

# Run a specific job
act -j test

# Run a specific event
act pull_request

# List available workflows
act -l

# Use a specific runner image
act -P ubuntu-latest=catthehacker/ubuntu:act-latest
```

## Architecture Highlights

- **Parser**: Reads `.github/workflows/*.yml` and builds a DAG of jobs/steps
- **Runner**: Executes each step in a Docker container matching the `runs-on` spec
- **Expressions**: Evaluates GitHub Actions expressions (`$ github.event `, etc.)
- **Secrets**: Pass secrets via `.secrets` file or `-s` flag
- **Artifacts**: Supports upload/download artifact actions
- **Runner images**: Uses community Docker images (smaller than GitHub's full runners)

## Key Modules

| Module | Description | Extractable? |
|--------|-------------|-------------|
| YAML Workflow Parser | Parses GH Actions syntax into execution DAG | ✅ Go library |
| Docker Runner | Executes steps in containers | ✅ Pattern |
| Expression Evaluator | Handles `$ ` expressions | ✅ Go library |
| Event Simulator | Simulates push/PR/schedule events | ✅ Pattern |

## Solo Dev Verdict

**🟢 MUST HAVE** — Install it now: `brew install act`. Every time you touch `.github/workflows/`, use `act` first. Saves 5-10 minutes per CI iteration and prevents embarrassing broken-pipeline commits.

**Setup time**: 2 minutes. **ROI**: Immediate.

```bash
brew install act  # macOS
choco install act-cli  # Windows
curl -s https://raw.githubusercontent.com/nektos/act/master/install.sh | sudo bash  # Linux
```

## Risks & Counter-Arguments

- **Docker required**: Must have Docker Desktop or compatible runtime
- **Not 100% compatible**: Some GitHub-hosted runner features don't work locally (cached tools, service containers)
- **Large images**: Full runner images are 12GB+. Use micro images for speed
- **Secrets management**: Be careful not to commit `.secrets` files
