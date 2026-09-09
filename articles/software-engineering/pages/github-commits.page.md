---
name: github-commits
type: page
about: Commit header, body, footer structure, type reference, and examples.
---

# GitHub — Commits

## Format

### Header (required)

```
<type>(<scope>): <summary>
```

Imperative, lowercase, under 72 chars, no period.

### Body (optional)

Explain what and why — not how.

### Footer (optional)

```
Closes PROJ-1234
BREAKING CHANGE: <description>
```

## Types

| Type | Use when |
|------|---------|
| `feat` | New behavior |
| `fix` | Bug fix |
| `refactor` | Code restructure |
| `perf` | Performance |
| `test` | Tests |
| `chore` | Dependencies, tooling |
| `ci` | CI/CD |
| `infra` | Infrastructure |
| `docs` | Documentation |
| `style` | Formatting |

Breaking: `feat(api)!:` or `BREAKING CHANGE:` footer.

## Examples

### Valid

- `fix(auth): prevent session drop on 503`
- `feat(billing): add Stripe webhook`
- `refactor(api): extract validation logic`

### Invalid

| Bad | Good |
|-----|------|
| `Fixed auth bug` | `fix(auth): resolve session drop` |
| `Add login` | `feat(auth): add OAuth2 login` |
| `login button broken on mobile` | `fix(ui): repair mobile login button` |
