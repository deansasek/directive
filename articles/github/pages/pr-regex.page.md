---
name: pr-regex
type: page
about: PR title validation regex.
---

# Regex

```
^(\[[A-Z0-9]+-[0-9]+\] )?(feat|fix|chore|refactor|perf|test|docs|style|ci|infra)(\([a-z0-9\-]+\))?!?: [a-z0-9].+$
```

Breaking change flag: `!` before the colon.
