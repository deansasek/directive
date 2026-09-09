---
name: github-pr-naming
type: article
about: Enterprise-standard Pull Request naming — syntax, types, regex, and governance rules.
---

# GitHub PR Naming

A strict syntax for PR titles that keeps Git history clean, readable, and machine-parseable.

## Syntax

```
[TICKET-ID] type(scope): imperative description
```

Examples:
- `[ENG-1042] feat(auth): add multi-factor authentication`
- `fix(gateway): resolve memory leak`
- `chore!: deprecate node 18 support`

## Skills

- **validate** — check a PR title against the standard
- **suggest** — generate a PR title from a description

## Pages

- **types** — when to use each type prefix
- **examples** — good and bad examples

## Types

| Type | Use for |
|------|---------|
| `feat` | New feature or capability |
| `fix` | Bug resolution |
| `refactor` | Code health, no behavior change |
| `perf` | Speed or memory improvements |
| `test` | Test coverage, refactoring tests |
| `chore` | Dependencies, build tools, .gitignore |
| `ci` | CI/CD pipelines, build runners |
| `infra` | Terraform, Docker, Kubernetes |
| `docs` | Documentation only |
| `style` | Formatting, linting |

## Regex

```
^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$
```

Breaking changes: append `!` before the colon.

## Rules

- **Imperative mood**: `resolve`, not `resolved` or `resolves`
- **Ticket ID uppercase**: `[API-4029]`, not `[api-4029]`
- **Ticketless PRs**: one thing only — no "and"
- **Scope encouraged**: `fix(billing):` in large monorepos

## Squash Merge

Require squash-and-merge. The PR title becomes the single commit on main.
