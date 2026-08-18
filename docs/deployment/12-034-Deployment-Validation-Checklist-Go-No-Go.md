# Deployment Validation Checklist & Go/No-Go Decision

## Purpose

Defines the final operational checklist used before and during production deployment.

## Pre-Deployment

Verify:

- [ ] Correct source revision
- [ ] Correct artifact
- [ ] Required tests passed
- [ ] Security gates passed
- [ ] Configuration validated
- [ ] Secrets available through approved mechanisms
- [ ] Database migration plan validated
- [ ] Infrastructure changes reviewed
- [ ] Monitoring active
- [ ] Recovery path confirmed
- [ ] Required approvals complete

## Deployment

Verify:

- [ ] Correct environment
- [ ] Correct artifact identity
- [ ] Rollout strategy active
- [ ] Health/readiness checks passing
- [ ] No unexpected errors
- [ ] Traffic exposure within planned scope

## Post-Deployment

Verify:

- [ ] Critical synthetic checks pass
- [ ] Error rate acceptable
- [ ] Latency acceptable
- [ ] Resource usage acceptable
- [ ] Database healthy
- [ ] Queue/workers healthy
- [ ] AI provider behavior healthy where applicable
- [ ] No blocking regression detected

## Go Criteria

Proceed when required blocking conditions are satisfied and observed behavior matches expectations.

## No-Go Criteria

Stop or recover when there is:

- Critical security failure
- Data integrity risk
- Failed readiness
- Severe availability degradation
- Material unexplained regression
- Invalid configuration
- Missing recovery capability

## AI Releases

For material AI changes also verify:

- [ ] Evaluation baseline available
- [ ] Safety evaluation passed
- [ ] Tool-use validation passed
- [ ] RAG validation passed where applicable
- [ ] Cost/latency within limits
- [ ] Deterministic authorization intact

## Decision Record

The deployment decision should identify:

- Release
- Environment
- Decision
- Evidence
- Decision-maker or policy
- Exceptions

## Anti-Patterns

Avoid approving from memory, skipping checks because the release is small, and treating a green CI pipeline as sufficient evidence for every production concern.

# Next Document

**12-035 — Deployment Automation & AI Agent Operating Rules**
