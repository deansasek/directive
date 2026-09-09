---
name: delete
type: skill
about: Deletes an article, skill, or page. Deleting a skill or page requires the owning article name.
---

# Delete

Removes a file or directory from the repo.

**Arguments:**
- `type` — `article`, `skill`, or `page`
- `article-name` — the owning article (required for skill/page); for article deletion, the article to delete
- `item-name` — the skill or page name to delete (not used for article deletion)
- `confirm` — required `yes` when deleting an article

**Behavior:**
1. Validates path: no `..` allowed
2. For `article`: deletes `articles/<article-name>/` directory and everything inside
3. For `skill`: deletes `articles/<article-name>/skills/<item-name>.skill.md`
4. For `page`: deletes `articles/<article-name>/pages/<item-name>.page.md`
5. Runs `regenerate` to update manifest

**Errors:**
- "path traversal not allowed" if `..` in path
- "article-name is required for skill/page deletion" if missing
- "confirm=yes required to delete an article" if not provided
- "file not found at <path>" if target doesn't exist
