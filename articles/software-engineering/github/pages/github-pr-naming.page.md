---
name: github-pr-naming
type: page
about: PR title format, type prefixes, validation regex, and examples.
---

# GitHub — PR Naming

Format: `[TICKET] type(scope): imperative description`

## Type Prefixes

| Type | Use for |
|------|---------|
| `feat` | New feature |
| `fix` | Bug fix |
| `refactor` | Code restructure |
| `perf` | Performance |
| `test` | Tests |
| `chore` | Dependencies, tooling |
| `ci` | CI/CD |
| `infra` | Infrastructure |
| `docs` | Documentation |
| `style` | Formatting |

Breaking changes: append `!` → `feat(api)!:`

## Validation Regex

```
^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$
```

Breaking change flag: `!` before the colon.

## Examples

### Valid

- `[ENG-1] feat(auth): add OAuth2 provider`
- `fix(gateway): resolve memory leak`
- `chore!: deprecate node 18 support`

### Invalid

| Bad | Fix |
|-----|-----|
| `[api-1] feat: add login` | `[API-1]` |
| `feat: Add login` | `feat: add login` |
| `fix(ui) resolve` | `fix(ui): resolve` |
| `WIP: add login` | Remove WIP |
