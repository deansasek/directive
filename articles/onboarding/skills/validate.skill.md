---
name: validate
type: skill
about: Checks if all onboarding tools are installed.
---

# Validate

Checks if each required tool is installed.

**Behavior:**
1. Run `which` for each tool: `claude`, `tmux`, `zsh`, `git`
2. Return PASS or FAIL per tool

**Output:**
```
claude: PASS
tmux: PASS
zsh: PASS
git: PASS
```
