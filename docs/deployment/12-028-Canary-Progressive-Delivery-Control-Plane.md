# Canary & Progressive Delivery Control Plane

## Purpose

Defines the controls required to progressively expose a release while continuously evaluating its health.

## Principle

Traffic exposure should increase only when evidence supports increasing confidence.

## Stages

A rollout may use:

```text
0%
→ Internal / Synthetic
→ Small Canary
→ Expanded Canary
→ Majority
→ 100%
```

Exact percentages are environment-specific.

## Entry Criteria

Before canary exposure:

- Artifact verified
- Required tests passed
- Security gates passed
- Configuration validated
- Recovery path confirmed
- Monitoring active

## Canary Signals

Monitor:

- Error rate
- Latency
- Saturation
- Critical workflow success
- Dependency failures
- Business signals
- AI quality/cost signals where relevant

## Comparison

Compare canary behavior against an appropriate stable baseline.

## Abort Conditions

Define objective conditions for:

- Pause
- Abort
- Rollback
- Escalation

## Promotion

Promotion must be deliberate and traceable.

Automated promotion is acceptable only when policy and signals are sufficiently deterministic.

## AI Canary

For material AI changes, compare relevant:

- Quality evaluations
- Safety evaluations
- Tool-use behavior
- Latency
- Cost
- Provider errors

## Traffic Integrity

Traffic routing must not accidentally expose users outside the intended cohort.

## Cohort Design

Where applicable, use stable cohort assignment so users do not unpredictably switch between versions.

## Control Plane Failure

The rollout system itself must fail safely.

Loss of rollout-control connectivity must not automatically mean unrestricted promotion.

## Anti-Patterns

Avoid canaries without comparison baselines, subjective promotion decisions, unstable cohorts, and rollout controllers that fail open.

# Next Document

**12-029 — Feature Flags & Deployment Decoupling**
