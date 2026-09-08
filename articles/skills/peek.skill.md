---
name: peek
type: skill
about: Returns only the YAML frontmatter of a file, no content.
---

# Peek

## Arguments

- `path` — file path, e.g. `articles/skills/read.skill.md`

## Notes

- Path traversal (`..`) is rejected
- Returns frontmatter as YAML
