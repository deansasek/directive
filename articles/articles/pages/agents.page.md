---
name: agents
type: page
about: The stock agents that come with the directive toolkit.
---

# Agents

Directive ships with two stock agents:

## `@researcher`

Researches codebases and surfaces findings. Use when exploring unfamiliar code, auditing architecture, or identifying patterns. Delegates implementation to `@engineer`.

## `@engineer`

Implements, scaffolds, refactors, and fixes. Takes direction from `@researcher`. Reads article pages for conventions when relevant — no preloading.

## Usage

```
claude --plugin-dir ./directive
@researcher audit the auth module
@engineer scaffold a new article called 'api-design'
```

## Adding Agents

Place `.md` files in `agents/` at the plugin root. See `.claude-plugin/plugin.json` for the plugin name — agents become `/<plugin-name>:<agent-name>`.
