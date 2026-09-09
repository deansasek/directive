---
name: pr-examples
type: page
about: Good and bad PR title examples.
---

# PR Examples

## Valid

- `[ENG-1] feat(auth): add OAuth2 provider`
- `fix(gateway): resolve memory leak`
- `chore!: deprecate node 18 support`

## Invalid

| Bad | Fix |
|-----|-----|
| `[api-1] feat: add login` | `[API-1]` |
| `feat: Add login` | `feat: add login` |
| `fix(ui) resolve` | `fix(ui): resolve` |
| `WIP: add login` | Remove WIP |
