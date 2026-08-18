# Smoke & Sanity Testing Standards

## Purpose

Defines fast validation used to determine whether a build or environment is suitable for deeper testing.

## Smoke Testing

Smoke tests answer:

> Is the system sufficiently alive to justify further testing?

Typical checks include:

- Application starts
- Critical endpoint responds
- Authentication infrastructure is reachable
- Database connectivity works
- Essential configuration loads
- Core UI loads

## Sanity Testing

Sanity testing answers:

> Does a targeted change appear to behave correctly before broader validation?

It is narrower than full regression.

## Post-Deployment Smoke

After deployment, verify:

- Service health
- Readiness
- Critical endpoint
- Authentication
- Database connectivity
- Queue/worker health where relevant
- Critical user journey

## Production Smoke

Production smoke tests must be:

- Low risk
- Read-only where possible
- Explicitly production-aware
- Safe for repeated execution

## Test Data

Never create destructive or uncontrolled production data merely to prove deployment health.

## AI Features

Smoke tests for AI functionality should verify infrastructure and deterministic boundaries such as:

- Provider connectivity
- Configuration
- Authentication
- Tool availability
- Output parsing

They should not depend on subjective model quality unless the smoke test is explicitly an AI quality check.

## Failure Handling

A failed critical smoke test should stop or pause promotion where the release process defines it as a blocking gate.

## Speed

Smoke suites should remain intentionally small and fast.

## Sanity vs Regression

Sanity testing is targeted.

Regression testing is broader.

Do not use the terms interchangeably in automation or documentation.

## Anti-Patterns

Avoid:

- Large smoke suites
- Destructive production smoke tests
- Smoke tests that depend on fragile external systems unnecessarily
- Treating smoke success as complete release validation

# Next Document

**11-013 — Test Automation Architecture**
