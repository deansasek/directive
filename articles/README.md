# Articles

A knowledge organization system for AI agents — manifest-driven, token-efficient, composable.

## What It Is

- **manifest.json** — index of all articles
- **skills/** — tooling: list, read, peek, create, update, delete, regenerate
- **pages/** — guidance: overview, anatomy, usage
- **articles/** — article content entry points

## Install (Global)

```bash
cp -r articles ~/.claude/articles
```

Then add to `~/.claude/CLAUDE.md`:

```
See `~/.claude/articles/manifest.json` to discover articles.
```
