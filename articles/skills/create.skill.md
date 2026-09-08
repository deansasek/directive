---
name: create
type: skill
about: Creates a new article, skill, or page with correct structure and frontmatter.
---

# Create

## Arguments

- `type` — `article`, `skill`, or `page`
- `article-name` — the article to create inside, or the name of the new article
- `item-name` — the new skill or page name (not for articles)
- `about` — summary (required for articles; optional for skills/pages)

## Examples

- `/create article my-article about="What this covers."`
- `/create skill my-article create-timeline about="Creates a timeline."`
- `/create page my-article timeline-format about="Timeline format reference."`

## Notes

- Article/item names: kebab-case
- Path traversal (`..`) is rejected
- If target exists: error "already exists at <path>"
