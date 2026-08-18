# Zero-Downtime & Availability-Aware Deployment

## Purpose

Defines deployment requirements for maintaining service availability during supported production changes.

## Principle

Availability during deployment is an architectural property, not a promise made by the deployment script.

## Capacity

Before removing or replacing instances, ensure sufficient remaining capacity.

## Connection Draining

Traffic should be drained safely before terminating instances where the infrastructure supports it.

## Long-Running Requests

Deployment must account for:

- Active requests
- Streaming responses
- Background jobs
- WebSocket or persistent connections where applicable

## Backward Compatibility

During rolling transitions, old and new versions may coexist.

APIs, events, and database schemas must therefore remain compatible for the transition window.

## Database Changes

Prefer expand-and-contract migration patterns for changes requiring multiple application versions.

Example:

```text
Expand
→ Deploy Compatible Code
→ Migrate/Backfill
→ Switch Behavior
→ Contract
```

## Queue Workers

Worker version transitions must avoid:

- Duplicate processing
- Incompatible messages
- Lost jobs

## AI Streaming

For AI features using streaming, deployment must handle active streams without unnecessary interruption where availability requirements demand it.

## Maintenance Windows

If zero-downtime is technically or economically inappropriate, an explicit maintenance window may be used.

It must be communicated and authorized.

## Verification

Measure actual availability during representative deployments.

## Anti-Patterns

Avoid schema changes that instantly break the previous version, terminating all instances simultaneously without capacity planning, and claiming zero downtime without testing the transition.

# Next Document

**12-009 — Rollback, Roll-Forward & Recovery Strategy**
