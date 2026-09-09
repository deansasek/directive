---
name: patterns
type: page
about: Agent patterns — background, delegation, and color conventions.
---

# Agent Patterns

## Background Agents

Set `background: true` for fire-and-forget workers:

```yaml
---
name: query
background: true
---
```

Workers run in the background, notify when done.

## Orchestration

Parent agents delegate to specialized agents:

```
@project-manager → @researcher (explore)
              → @engineer (build)
              → @linter (format)
```

## Color Convention

| Color | Agent |
|-------|-------|
| `blue` | Researcher |
| `green` | Engineer |
| `orange` | Project Manager |
| `cyan` | Query / Data |
| `yellow` | Linter |
