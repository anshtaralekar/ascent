# Regression Testing Strategy

## Purpose

Defines how Ascend prevents previously working behavior from breaking as the system evolves.

## Principle

Regression testing should protect important behavior without turning every historical defect into an expensive end-to-end test.

## Regression Sources

Regression coverage should come from:

- Critical product workflows
- Previous defects
- Security findings
- Data integrity incidents
- API compatibility requirements
- Infrastructure failures
- AI evaluation failures

## Test Placement

When a defect is fixed, add the regression test at the lowest appropriate test layer.

Prefer:

```text
Unit > Component > Integration > Contract > E2E
```

unless the defect specifically requires a higher-level test.

## Critical Regression Suite

Maintain a focused suite covering the highest-risk behaviors.

It should be fast enough to run frequently.

## Full Regression

A broader suite may run:

- Before major releases
- After high-risk architectural changes
- On scheduled validation cycles
- Before major migrations

## Change-Aware Regression

Where practical, identify affected areas from changed code, dependencies, contracts, and infrastructure.

Do not rely exclusively on change detection because indirect effects can exist.

## Security Regression

Security fixes require regression coverage proving that the vulnerability remains closed.

## Database Regression

Schema and migration changes should include tests for affected queries, constraints, compatibility, and data integrity.

## API Regression

Contract tests should protect existing consumers from unintended breaking changes.

## AI Regression

AI evaluation suites should retain representative historical failures.

When model/provider behavior changes, compare results against established evaluation datasets.

## Flaky Regression Tests

Do not remove a regression test simply because it is inconvenient.

Investigate whether the underlying test or system is unstable.

## Test Retirement

Retire obsolete regression tests only when the protected behavior no longer exists or the architecture has intentionally changed.

Document important reasoning for removal.

## Anti-Patterns

Avoid:

- Running only a giant regression suite
- Adding every regression as E2E
- Removing tests because a bug is old
- Ignoring historical AI failures
- Treating green regression results as proof of complete correctness

# Next Document

**11-012 — Smoke & Sanity Testing Standards**
