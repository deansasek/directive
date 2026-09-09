---
name: pr-suggest
type: skill
about: Suggests a PR title from a description.
---

# PR Suggest

**Args:** `description`, `ticket`, `type`, `scope`

**Output:** `[TICKET] type(scope): description`

**Examples:**
- `pr-suggest "add oauth2 to auth" ticket=ENG-1 type=feat scope=auth` → `[ENG-1] feat(auth): add OAuth2 provider`
- `pr-suggest "fix memory leak in gateway"` → `fix(gateway): resolve memory leak`
