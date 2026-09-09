---
name: github-template
type: page
about: Standardized PR body template and how to configure it.
---

# GitHub — PR Template

## Template

```markdown
## Description
<!-- what changed and why -->

## Related Issues
<!-- Fixes PROJ-1234 -->

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Refactor / Performance / Tech Debt

## How Has This Been Tested?
- [ ] Unit tests
- [ ] Integration tests
- [ ] Manual smoke test

## Checklist
- [ ] Style guidelines
- [ ] Self-review
- [ ] Documentation
- [ ] Security implications
```

## Setup

Create `.github/PULL_REQUEST_TEMPLATE.md`. Comments are stripped when the PR opens.

## Enforcement

Use `semantic-pull-requests` GitHub Action to require conventional PR titles.
