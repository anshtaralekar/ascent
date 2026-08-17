---
title: Database Migrations
document_id: 07-007
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Migrations

> "A schema change is a deployment event, not a local edit."

## Purpose

Defines how Ascend database schemas evolve safely across development, testing, staging, and production.

## Philosophy

All schema changes must be reproducible, version-controlled, reviewable, and compatible with the application's deployment strategy.

## Migration Lifecycle

1. Define change
2. Assess compatibility
3. Create migration
4. Test against representative data
5. Review
6. Apply to non-production environments
7. Validate
8. Deploy production change
9. Verify
10. Retire transition code when appropriate

## Migration Files

Every migration should have:

- Unique identifier
- Ordered execution
- Clear description
- Deterministic behavior
- Ownership
- Dependency awareness

## Compatibility

Consider compatibility with:

- Current application version
- Previous application version
- Background workers
- Scheduled jobs
- Read replicas
- External integrations

## Expand-and-Contract

Prefer additive transitions for distributed systems:

1. Add compatible structure
2. Deploy code that supports both states
3. Backfill if required
4. Switch reads/writes
5. Remove obsolete structure later

## Data Migrations

Separate schema changes from large data transformations when appropriate.

Data migrations should consider:

- Batch size
- Lock duration
- Runtime
- Restartability
- Progress tracking
- Idempotency

## Destructive Changes

Destructive changes require explicit review.

Examples:

- Dropping columns
- Dropping tables
- Changing incompatible types
- Removing required relationships

Prefer delayed removal after dependent code has been retired.

## Rollback

Every migration must define a recovery strategy.

For complex migrations, a forward-fix strategy may be safer than automatic rollback.

## Production Safety

Monitor:

- Migration duration
- Lock acquisition
- Database load
- Error rate
- Replication lag

Large changes should be staged where possible.

## Testing

Test migrations against:

- Empty database
- Representative dataset
- Production-scale estimates
- Existing application versions

## Governance

Require:

- Code review
- Migration ordering
- Deployment ownership
- Recovery plan
- Audit trail

## Anti-Patterns

Avoid:

- Editing already-applied migrations
- Manual production schema edits
- Long blocking migrations without planning
- Destructive changes bundled with unrelated features

## AI Context

AI coding agents must generate version-controlled migrations rather than modifying production schemas directly and must account for compatibility across application versions.

# Next Document

**07-008 — Data Access Layer**
