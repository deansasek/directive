# Directive

An engineering toolkit for Claude Code agents, distributed as a plugin.

## Install

```bash
# As a plugin (full toolkit)
git clone https://github.com/deansasek/directive.git
claude --plugin-dir ./directive

# Or auto-load from skills directory
cp -r directive ~/.claude/skills/directive
```

## Features

### Articles

Manifest-driven knowledge system. See `articles/articles/articles.article.md` for the meta-article.

To install articles globally only:

```bash
cp -r articles ~/.claude/articles
```

Then add to `~/.claude/CLAUDE.md`:

```
See `~/.claude/articles/manifest.json` to discover articles.
```
