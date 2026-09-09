---
name: patterns
type: page
about: Common testing patterns — Arrange-Act-Assert, mocking, and fixtures.
---

# Testing Patterns

## Arrange-Act-Assert

```python
# Arrange
user = create_test_user()

# Act
result = user.authenticate("password")

# Assert
assert result.is_authenticated
```

## Mocking

Mock external dependencies (APIs, databases) to keep tests fast and deterministic.

## Fixtures

Reusable test data setup. Share across tests to avoid duplication.

## Coverage

- Aim for critical paths, not 100% coverage
- Prioritize: edge cases, error paths, business logic
