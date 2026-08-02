---
title: Testing
document_id: FA-039
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Testing

> "Quality is engineered before release, not inspected afterward."

## Purpose

Defines the testing strategy for all frontend code in Ascend.

---

## Philosophy

Every feature should be verified through automated testing at the appropriate level while keeping tests reliable, maintainable, and fast.

---

## Testing Pyramid

- Unit Tests
- Integration Tests
- End-to-End Tests

Favor many small tests over a few broad ones.

---

## Test Types

- Unit
- Integration
- Component
- End-to-End
- Accessibility
- Visual Regression
- Performance

---

## Coverage

Test:

- Business logic
- User workflows
- Error handling
- Authentication
- AI interactions
- Critical UI states

---

## Mocking

Mock:

- External APIs
- AI providers
- Browser APIs
- Time-dependent logic

Avoid mocking internal business logic.

---

## Continuous Integration

Run automated tests on:

- Pull requests
- Main branch
- Release candidates

Block deployments on critical failures.

---

## Performance

Keep tests:

- Fast
- Deterministic
- Independent
- Repeatable

---

## Anti-Patterns

Avoid:

- Fragile selectors
- Over-mocking
- Snapshot abuse
- Flaky timing-dependent tests

---

## AI Context

AI coding agents should generate tests alongside production code and follow the established testing pyramid.

---

# Next Document

**FA-040 — Storybook**
