# Deployment Strategies & Rollout Patterns

## Purpose

Defines approved deployment patterns for controlling production blast radius and managing release risk.

## Principle

Choose the simplest rollout strategy that provides sufficient safety for the change.

## Rolling Deployment

Replace instances progressively while maintaining service availability.

Validate:

- Capacity during transition
- Version compatibility
- Health checks
- Connection draining
- Recovery behavior

## Blue/Green Deployment

Maintain two independently deployable environments and shift traffic between them.

Use when:

- Rapid traffic reversal is valuable
- Environment duplication is practical
- Strong release isolation is required

## Canary Deployment

Expose a limited portion of traffic to the new release before broader rollout.

Monitor:

- Error rate
- Latency
- Resource usage
- Critical workflows
- Business signals
- AI quality where relevant

## Feature-Flagged Deployment

Deploy code while keeping functionality disabled until validation is complete.

Flags require:

- Owner
- Scope
- Default state
- Auditability where needed
- Removal plan

## Recreate Deployment

Terminate the previous version before starting the new one.

Use only where downtime is explicitly acceptable.

## Rollout Stages

A progressive rollout may follow:

```text
Deploy
→ Health Check
→ Small Exposure
→ Observe
→ Expand
→ Observe
→ Complete
```

## Rollout Abort

Define objective conditions that stop expansion.

Examples:

- Elevated error rate
- Critical workflow failure
- Security failure
- Resource saturation
- Significant latency regression

## AI Releases

AI model or prompt changes may use limited exposure and comparative evaluation before full rollout.

## Database Compatibility

Rollout strategy must account for schema compatibility between old and new application versions.

## Recovery

Every rollout pattern must have a documented recovery mechanism.

## Anti-Patterns

Avoid selecting rollout patterns solely because they are fashionable, expanding traffic without health evidence, and relying on manual intuition for abort decisions.

# Next Document

**12-007 — Health Checks, Readiness & Deployment Verification**
