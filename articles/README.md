# Articles

A knowledge organization system for AI agents — manifest-driven, token-efficient, composable.

## What It Is

- **manifest.json** — index of all articles
- **articles/articles/** — the "articles" meta-article with core skills and pages
- **articles/<name>/** — individual article content with their own skills and pages

## Install (Global)

```bash
cp -r articles ~/.claude/articles
```

Then add to `~/.claude/CLAUDE.md`:

```
See `~/.claude/articles/manifest.json` to discover articles.
```
