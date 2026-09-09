---
name: commit-examples
type: page
about: Good and bad commit message examples.
---

# Examples

## Valid

- `fix(auth): prevent session drop on 503`
- `feat(billing): add Stripe webhook`
- `refactor(api): extract validation logic`

## Invalid

| Bad | Good |
|-----|------|
| `Fixed auth bug` | `fix(auth): resolve session drop` |
| `Add login` | `feat(auth): add OAuth2 login` |
| `login button broken on mobile` | `fix(ui): repair mobile login button` |
