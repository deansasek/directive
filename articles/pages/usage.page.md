---
name: usage
type: page
about: How to use the system — discovering, loading, creating, updating, deleting.
---

# Usage

## Discovering Articles

Read `manifest.json` to see all articles. Open an article's `<name>.article.md` to see its skills and pages.

## Loading Skills or Pages

- `read` — frontmatter + content
- `peek` — frontmatter only

## Creating Content

```
/create <type> <article-name> <item-name> about="..."
```

## Updating

`/update <path> patch about="..."` — or `replace` for full overwrite.

## Deleting

```
/delete <type> <article-name> <item-name>
```

Articles require `confirm=yes`. Deleting an article removes everything inside it.

## When to Create a New Article

When a set of skills and pages share a coherent topic but don't fit an existing article.

## Best Practices

- `about` should be 2-3 sentences — enough for an AI to assess relevance without reading the full file
- Skills do one thing; pages document when and in what order
- Reference files stay private to each article — don't share across articles
- Run `regenerate` after creating or deleting articles
