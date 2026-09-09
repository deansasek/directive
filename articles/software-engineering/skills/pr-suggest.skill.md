---
name: pr-suggest
type: skill
about: Suggests a PR title given a change description.
---

# PR Suggest

Suggests a PR title in conventional format: `[TICKET] type(scope): imperative description`

**Arguments:**
- `description` — brief description of the change (what changed and why)
- `ticket` — optional ticket ID (e.g., `ENG-123`)
- `type` — optional type override (feat, fix, refactor, etc.)
- `scope` — optional scope (e.g., auth, api, ui)

**Output:** A valid PR title suggestion.
