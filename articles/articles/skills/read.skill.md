---
name: read
type: skill
about: Reads a file by path, returning both the YAML frontmatter and the Markdown body.
---

# Read

Returns the complete file: frontmatter block followed by Markdown body.

**Behavior:**
1. Reads the target file
2. Returns the full file as-is

**Arguments:**
- `path` — path to the file relative to the repo root, e.g. `articles/github/skills/pr-validate.skill.md`

**Error:** "path traversal not allowed" if path contains `..`
