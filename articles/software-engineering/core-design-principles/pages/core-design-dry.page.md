---
name: core-design-dry
type: page
about: Don't Repeat Yourself — every piece of knowledge should have a single, authoritative representation.
---

# Core Design — DRY

Every piece of knowledge should have a single, authoritative representation in the system.

Duplication causes bugs when updates are missed — fix one place, forget another.

## When to Apply

Extract repeated logic into functions, modules, or shared utilities.

## When NOT to Apply

Don't force DRY on things that happen to look similar but have different reasons to change. Duplication is cheaper than the wrong abstraction.
