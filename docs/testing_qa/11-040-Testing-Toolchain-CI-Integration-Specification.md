# Testing Toolchain & CI Integration Specification

## Purpose

Defines the expected relationship between the testing architecture and the software delivery pipeline.

## Principle

Testing must be integrated into delivery as a set of reliable, attributable quality controls.

## Tooling

Use the repository's approved tools for:

- Formatting
- Linting
- Static analysis
- Unit testing
- Integration testing
- E2E testing
- Security scanning
- Accessibility checks
- Performance testing
- AI evaluation

Do not introduce overlapping tooling without justification.

## Pipeline Stages

A representative flow is:

```text
Source
  ↓
Static Validation
  ↓
Unit / Component
  ↓
Integration / Contract
  ↓
Security
  ↓
Build
  ↓
E2E
  ↓
Performance / Specialized
  ↓
Release Gates
```

Exact sequencing follows repository and deployment constraints.

## Test Selection

CI may use multiple tiers:

- Fast checks on every change
- Broader validation on pull requests
- Full regression on release candidates
- Scheduled performance/security/recovery suites

## Failure Handling

CI must distinguish:

- Test failure
- Infrastructure failure
- Provider failure
- Configuration failure
- Flakiness

Do not silently classify infrastructure failures as successful test runs.

## Artifacts

Retain useful reports, logs, traces, screenshots, coverage, and evaluation results according to retention policy.

## Secrets

CI tests use isolated credentials and approved secret mechanisms.

## Production Protection

CI jobs must technically prevent accidental production mutation unless the workflow explicitly belongs to controlled production deployment.

## AI Evaluation

AI CI should record:

- Dataset version
- Model/provider
- Configuration
- Results
- Cost/usage where relevant

Material regressions should block release when policy defines them as blocking.

## Parallelism

Parallel execution should improve feedback time without creating shared-state races.

## Reproducibility

A failed CI run should provide enough metadata to reproduce the relevant validation locally or in an equivalent environment.

## Governance

Every blocking CI check requires an owner and documented purpose.

## Anti-Patterns

Avoid giant opaque pipelines, silent failures, unbounded retries, production credentials in test jobs, and quality gates nobody owns.

# Volume 11 Progress

**11-001 through 11-040 complete.**

# Next Document

**11-041 — Final Testing Architecture Specification**
