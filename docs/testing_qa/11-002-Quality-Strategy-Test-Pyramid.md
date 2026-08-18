# Quality Strategy & Test Pyramid

## Purpose
Defines the distribution and sequencing of tests across Ascend.

## Pyramid
```text
          E2E / Journey
             /\
        Integration
          /      \
     Component / Contract
        /          \
             Unit
```

## Unit
Use for business rules, pure transformations, validation, and deterministic calculations.

## Component
Validate meaningful module behavior while avoiding unnecessary external dependencies.

## Integration
Validate real interactions with databases, queues, caches, storage, authentication, and provider adapters where those interactions are the risk.

## Contract
Verify that independently developed consumers and providers agree on requests, responses, errors, and compatibility.

## E2E
Validate critical user journeys selectively. E2E tests should not become the default mechanism for testing simple logic.

## Specialized Testing
Add security, performance, accessibility, recovery, compatibility, migration, and AI evaluation according to risk.

## CI Ordering
Formatting/lint → static/type checks → unit → component → integration/contract → security → build → E2E → release validation.

## Flakiness
Flaky tests are defects in the quality system. Do not permanently hide failures to make CI green.

## Coverage
Coverage is a diagnostic metric, not the definition of quality.

## AI Tests
AI-generated tests must validate behavior rather than merely mirror implementation details.

# Next Document
**11-003 — Test Levels & Validation Boundaries**
