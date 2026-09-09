---
name: types
type: page
about: When to use each PR type prefix — feature, fix, refactor, and more.
---

# PR Type Reference

Use the right type prefix for every PR.

## Feature & Bug Resolution

- **feat** — new capability or behavior
- **fix** — bug fix or patch

## Quality

- **refactor** — code health, no behavior change
- **perf** — speed or memory improvement
- **test** — test coverage or test refactoring

## Operations

- **chore** — dependencies, build tools, tooling
- **ci** — CI/CD pipelines, build runners
- **infra** — Terraform, Docker, Kubernetes

## Surface

- **docs** — documentation only
- **style** — formatting, linting

## Choosing

1. **Is it a new behavior?** → `feat`
2. **Is it fixing a bug?** → `fix`
3. **Is it changing behavior?** → `refactor`
4. **Is it infrastructure?** → `ci` or `infra`
5. **Is it documentation only?** → `docs`
