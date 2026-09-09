---
name: examples
type: page
about: Good and bad PR title examples with explanations.
---

# Examples

## Valid

| Title | Why |
|-------|-----|
| `[ENG-1042] feat(auth): add multi-factor authentication` | Ticketed, scoped, imperative |
| `fix(gateway): resolve memory leak` | Ticketless, scoped, clear |
| `chore!: deprecate node 18 support` | Breaking change flag |
| `refactor(billing): extract payment logic` | Refactor with scope |

## Invalid

| Title | Fail | Fix |
|-------|------|-----|
| `[api-4029] feat: update endpoints` | Ticket ID lowercase | `[API-4029]` |
| `feat: Add user avatar upload` | Description starts uppercase | `add user avatar upload` |
| `fix(ui) resolve alignment issues` | Missing `: ` | `fix(ui): resolve` |
| `WIP: refactor database` | WIP not allowed | Remove WIP |
| `fix: update button color and fix text typo` | Two things | Split into two PRs |

## Breaking Changes

Append `!` before the colon:

```
feat(api)!: remove support for legacy v1 endpoints
```
