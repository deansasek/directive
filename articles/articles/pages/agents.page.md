---
name: agents
type: page
about: The stock agents that come with the directive toolkit.
---

# Agents

Directive ships with four stock agents:

## `@project-manager`

Orchestrates tasks. Breaks work into research → implementation phases, delegates to researcher and engineer.

## `@researcher`

Researches codebases and surfaces findings. Use for audits, exploring unfamiliar code, identifying patterns.

## `@engineer`

Implements, scaffolds, refactors, and fixes. Reads article pages for conventions when relevant — no preloading.

## `@query`

Handles SQL queries and data access. Uses the cheapest model for cost efficiency.

## Usage

```
claude --plugin-dir ./directive
@project-manager plan the auth refactor
@researcher audit the billing module
@engineer scaffold a new article called 'api-design'
@query show me active users from last week
```

## Adding Agents

Place `.md` files in `agents/` at the plugin root. See `.claude-plugin/plugin.json` for the plugin name — agents become `/<plugin-name>:<agent-name>`.
