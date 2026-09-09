---
name: peek
type: skill
about: Returns only the YAML frontmatter of a file, stopping at the closing --- delimiter.
---

# Peek

Returns only the YAML frontmatter block of a file — nothing from the Markdown body.

**Behavior:**
1. Reads the target file
2. Extracts content between the opening `---` and closing `---` of the YAML frontmatter block
3. Returns only the frontmatter, stripped of the `---` delimiters
4. Returns an empty response if the file has no frontmatter

**Arguments:**
- `path` — path to the file, e.g. `skills/read.skill.md` or `articles/articles.article.md`

**Error:** "path traversal not allowed" if path contains `..`
