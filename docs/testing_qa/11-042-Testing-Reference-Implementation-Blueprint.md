# Testing Reference Implementation Blueprint

## Purpose

Defines how the testing architecture should translate into repository-level implementation.

## Implementation Principle

The repository should make the correct testing behavior easy to discover, execute, and maintain.

## Recommended Organization

Use a structure appropriate to the existing repository, with clear separation for:

- Unit tests
- Component tests
- Integration tests
- Contract tests
- E2E tests
- Security tests
- Performance tests
- AI evaluations
- Test fixtures
- Shared test utilities

Do not create duplicate test hierarchies merely to follow this conceptual structure.

## Test Naming

Names should communicate:

- Feature/component
- Scenario
- Expected behavior

## Test Utilities

Shared utilities should reduce duplication without hiding important test intent.

## Fixtures

Fixtures and factories should be deterministic and easy to reset.

## Environment Configuration

Testing configuration must identify the intended environment explicitly.

## Database

Integration tests must use controlled databases and predictable migration/seed behavior.

## APIs

Contract and integration tests should derive expectations from the authoritative API definitions.

## E2E

Critical journeys should have stable setup, isolated identities, deterministic data, and useful failure artifacts.

## AI Evaluation

AI evaluation code should record:

- Dataset version
- Model/provider
- Configuration
- Evaluation result
- Relevant usage/cost metadata

## CI

Tests should expose machine-readable results and clear failure states.

## Performance

Performance tooling should record workload, environment, artifact, and baseline comparison.

## Security

Security checks should run with isolated test credentials and must not require production access.

## Production Verification

Synthetic checks require dedicated accounts and safe test data.

## AI Coding Rule

An AI coding agent must inspect the existing repository before introducing test directories, frameworks, fixtures, or runners.

It must reuse established conventions where compatible.

## Anti-Patterns

Avoid duplicate frameworks, hidden environment dependencies, shared mutable fixtures, and giant test utility layers that obscure behavior.

# Next Document

**11-043 — Testing Implementation & Acceptance Handoff**
