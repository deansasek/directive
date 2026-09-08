---
name: usage
type: page
about: How to work with articles — discovering, loading, creating, updating, deleting.
---

# Usage

## Discovering Articles

Read `manifest.json`, then open the article's `<name>.article.md` to see its skills and pages.

## Loading

- `read` — full file (frontmatter + content)
- `peek` — frontmatter only

## Creating

`/create <type> <article-name> <item-name> about="..."`

## Updating

`/update <path> patch about="..."` — or `replace` for full overwrite.

## Deleting

`/delete <type> <article-name> <item-name>` — articles require `confirm=yes`.

## When to Create a New Article

When a set of skills/pages share a coherent topic but don't fit an existing article.
