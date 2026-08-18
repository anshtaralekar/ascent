# Test Governance & Quality Ownership

## Purpose

Defines accountability for test suites, quality signals, failures, and validation infrastructure.

## Ownership Principle

Every critical test suite and quality gate must have an owner.

Ownership includes:

- Maintenance
- Failure triage
- Relevance
- Performance
- Flakiness
- Documentation

## Test Ownership

Assign ownership for:

- Unit/component suites
- Integration suites
- E2E journeys
- Security tests
- Performance tests
- AI evaluations
- Accessibility checks
- Infrastructure tests

## Quality Gate Ownership

Every blocking gate must have an accountable owner capable of resolving failures.

## Test Review

Tests should be reviewed when:

- Architecture changes
- Product behavior changes
- Dependencies change
- A recurring failure appears
- A protected behavior is removed

## Flakiness Governance

Track flaky tests with:

- Owner
- Cause
- Status
- Quarantine date
- Remediation plan

## Test Debt

Test debt should be tracked similarly to technical debt.

Examples:

- Missing regression coverage
- Outdated fixtures
- Slow suites
- Weak assertions
- Unvalidated critical journeys

## AI Evaluation Governance

AI evaluation datasets, rubrics, and baselines require ownership.

Changes to evaluation criteria should be documented because changing the test can change the apparent product quality.

## Evidence Governance

Important validation evidence must be attributable to:

- Artifact
- Environment
- Test version
- Timestamp
- Configuration

## Compliance

Where regulatory or contractual requirements apply, preserve appropriate testing evidence and review history.

## Human Judgment

Automation provides evidence. Responsible engineers remain accountable for interpreting high-risk results.

## Anti-Patterns

Avoid orphaned suites, gates with no owner, permanent quarantines, undocumented evaluation changes, and shared responsibility with no accountability.

# Next Document

**11-039 — Test Maintenance & Lifecycle Management**
