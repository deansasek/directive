---
name: types
type: page
about: When to use each conventional commits type.
---

# Types

| Type | Use when |
|------|---------|
| `feat` | New behavior |
| `fix` | Bug fix |
| `refactor` | Code restructure, no behavior change |
| `perf` | Performance improvement |
| `test` | Tests |
| `chore` | Dependencies, build, tooling |
| `ci` | CI/CD config |
| `infra` | Infrastructure (Terraform, Docker) |
| `docs` | Documentation |
| `style` | Formatting |

Breaking changes: append `!` → `feat(api)!:` or use `BREAKING CHANGE:` footer.
