# Database Migration Deployment Strategy

## Purpose

Defines how database schema and data migrations are coordinated with application deployment.

## Authority

Volume 07 governs database architecture. Volume 11 governs migration testing. Volume 12 governs deployment sequencing.

## Principle

Database changes must be deployed in a way that preserves application compatibility and recoverability.

## Migration Classes

Consider separately:

- Additive schema changes
- Data backfills
- Constraint changes
- Index changes
- Renames
- Destructive changes

## Expand-and-Contract

Prefer staged changes where old and new application versions may coexist:

```text
Expand
→ Deploy Compatible Application
→ Backfill / Migrate
→ Switch Behavior
→ Verify
→ Contract
```

## Compatibility

During rolling deployment:

- New code must tolerate the transitional schema.
- Old code must not fail because of the expanded schema.
- Shared data formats must remain compatible.

## Backfills

Large backfills should be:

- Bounded
- Observable
- Resumable where possible
- Resource-aware

Do not allow a migration to unexpectedly exhaust production resources.

## Indexes

Large indexes should be created using the safest supported operational strategy.

Measure lock and performance impact.

## Destructive Changes

Dropping or transforming data requires explicit review and recovery planning.

Do not combine irreversible destructive changes with an uncertain deployment.

## Ordering

Where appropriate:

```text
Database Expand
→ Application Deploy
→ Data Migration
→ Behavior Switch
→ Verification
→ Database Contract
```

## Rollback

Application rollback must be evaluated against the current database state.

A migration may make application rollback unsafe.

## Recovery

For irreversible changes, define forward recovery rather than assuming rollback.

## AI-Generated Migrations

AI-generated SQL or migration code requires human review and full migration testing.

Syntactic correctness is not operational safety.

## Verification

After migration verify:

- Schema
- Constraints
- Data integrity
- Query behavior
- Performance
- Application compatibility

## Anti-Patterns

Avoid destructive migrations during uncertain releases, untested production-scale backfills, and assuming database rollback is equivalent to application rollback.

# Next Document

**12-014 — Infrastructure Deployment & Change Management**
