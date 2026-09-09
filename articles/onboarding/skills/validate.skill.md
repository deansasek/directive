---
name: validate
type: skill
about: Checks if all onboarding tools are installed and ~/src/ exists.
---

# Validate

Checks if each required tool is installed and `~/src/` exists.

**Behavior:**
1. Run `which` for each tool: `claude`, `tmux`, `zsh`, `git`
2. Check `~/src/` exists
3. Return PASS or FAIL per item

**Output:**
```
claude: PASS
tmux: PASS
zsh: PASS
git: PASS
~/src/: PASS
```
