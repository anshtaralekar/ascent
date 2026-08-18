# Release Acceptance & Quality Gate Architecture

## Purpose

Defines how test evidence is converted into an explicit release decision.

## Principle

A release is accepted when required risk controls and validation evidence satisfy the defined release policy.

## Gate Categories

Gates may include:

- Static validation
- Unit/component tests
- Integration/contract tests
- Security validation
- Build/artifact validation
- E2E journeys
- Performance
- Accessibility
- AI evaluation
- Infrastructure/policy checks

## Blocking Gates

A blocking gate must pass before normal promotion.

Blocking conditions should be defined by risk, not convenience.

## Risk-Based Gates

Not every change requires every expensive test.

Change impact determines the applicable gate set.

## Artifact Traceability

Every release decision must identify the artifact and source revision that produced the evidence.

## Evidence Freshness

Tests used for release decisions should correspond to the release candidate or a demonstrably equivalent artifact/configuration.

## Exceptions

Exceptions require:

- Explicit reason
- Scope
- Risk assessment
- Owner
- Expiration or review point
- Compensating controls where applicable

## Emergency Releases

Emergency releases may use an expedited gate path defined by operational policy.

Required security and recovery controls must not be silently discarded.

## AI Changes

Material AI changes may require:

- Evaluation dataset execution
- Safety regression
- Tool-use validation
- Latency/cost comparison
- Human review

## Release Decision

A release decision should be attributable and reproducible.

## Anti-Patterns

Avoid manually declaring a release safe without evidence, using stale test results, bypassing gates without recording exceptions, or treating coverage as the only acceptance metric.

# Next Document

**11-038 — Test Governance & Quality Ownership**
