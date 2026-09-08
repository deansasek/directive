---
name: delete
type: skill
about: Deletes an article, skill, or page.
---

# Delete

## Arguments

- `type` — `article`, `skill`, or `page`
- `article-name` — the owning article (required for skills/pages)
- `item-name` — the skill or page to delete
- `confirm` — required `yes` to delete an article

## Examples

- `/delete article my-article` (requires `confirm=yes`)
- `/delete skill my-article create-timeline`
- `/delete page my-article timeline-format`

## Notes

- Path traversal (`..`) is rejected
- Deleting last skill/page from an article leaves an empty directory
- Deleting an article removes everything inside it
