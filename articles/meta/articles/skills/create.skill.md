---
name: create
type: skill
about: Creates a new article, skill, or page with correct frontmatter and directory structure.
---

# Create

Creates a new file with frontmatter and, for articles, the necessary subdirectories.

**Arguments:**
- `type` — `article`, `skill`, or `page`
- `article-name` — the article to create inside (for skill/page) or the name of the new article (for article)
- `item-name` — the name of the new skill or page (not used when creating an article)
- `about` — the about summary (required for articles; optional but recommended for skills/pages)

**Behavior:**
1. Validates inputs: kebab-case names, no `..` in paths
2. For `article`: creates `articles/<domain>/<article-name>/<article-name>.article.md` plus `skills/`, `pages/`, `reference/` directories
3. For `skill`: creates `articles/<domain>/<article-name>/skills/<item-name>.skill.md`
4. For `page`: creates `articles/<domain>/<article-name>/pages/<item-name>.page.md`
5. If target already exists: error "already exists at <path>"
6. Runs `regenerate` to update manifest

**Frontmatter created:**
```yaml
---
name: <name>
type: <type>
about: <about or empty>
---
```

**Errors:**
- "path traversal not allowed" if `..` in path
- "already exists at <path>" if file exists
