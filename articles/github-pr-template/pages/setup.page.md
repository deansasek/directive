---
name: setup
type: page
about: How to configure a PR template.
---

# Setup

Create `.github/PULL_REQUEST_TEMPLATE.md`:

```bash
mkdir -p .github
```

Add the template. Comments (`<!-- -->`) are stripped when the PR opens.

## Enforcement

Use GitHub Actions with `semantic-pull-requests` to require conventional PR titles.
