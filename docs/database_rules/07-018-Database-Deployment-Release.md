---
title: Database Deployment & Release
document_id: 07-018
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Deployment & Release

## Purpose

Defines how database changes are safely promoted through environments and coordinated with application releases.

## Philosophy

Database changes must account for application compatibility, migration duration, data volume, rollback limitations, and operational risk.

## Release Lifecycle

1. Design
2. Review
3. Generate migration
4. Test
5. Assess compatibility
6. Deploy to staging
7. Validate
8. Apply production migration
9. Deploy dependent code
10. Monitor

## Compatibility

Consider simultaneous operation of previous and new application versions, workers, jobs, replicas, and integrations.

## Expand-Contract

Prefer:

1. Add compatible schema
2. Deploy compatible application
3. Backfill
4. Switch usage
5. Remove obsolete structure later

## Migration Execution

Large migrations must account for lock duration, batch size, transaction duration, database load, replication lag, and recovery.

## Rollback

Database rollback is not always equivalent to application rollback. Each release must identify whether recovery uses a reversible migration, forward fix, restore, feature disablement, or compatibility layer.

## Monitoring

During deployment monitor migration duration, locks, errors, query latency, connections, replication, and application errors.

## Release Gates

Require migration review, compatibility assessment, test evidence, backup/recovery readiness, rollout plan, and monitoring plan.

## Auditability

Record migration version, deployment time, responsible service or operator, application version, and outcome.

## Anti-Patterns

Avoid manual production edits, destructive changes without analysis, assuming application rollback reverses database changes, and deploying incompatible versions simultaneously.

## AI Context

AI coding agents must treat migrations as release artifacts and explicitly coordinate schema compatibility with application, worker, and deployment versions.

# Next Document

**07-019 — Multi-Tenancy & Data Isolation**
