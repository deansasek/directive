---
name: suggest
type: skill
about: Suggests a PR title given a description of the change.
---

# Suggest

Generates a PR title from a change description.

**Arguments:**
- `description` — what the PR does
- `ticket` — ticket ID if available (e.g., `ENG-1042`)
- `type` — type hint if known (e.g., `feat`, `fix`)
- `scope` — component or service if applicable (e.g., `auth`, `billing`)

**Behavior:**
1. Infer type from description if not provided
2. Apply imperative mood to description
3. Format as `[TICKET] type(scope): description`
4. Return the suggested title

**Examples:**
- `suggest "add oauth2 to auth service" ticket=ENG-1042 type=feat scope=auth` → `[ENG-1042] feat(auth): add OAuth2 provider`
- `suggest "fix memory leak in gateway"` → `fix(gateway): resolve memory leak`
