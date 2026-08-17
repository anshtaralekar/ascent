---
title: Database Maintenance & Operational Runbooks
document_id: 07-039
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Maintenance & Operational Runbooks

## Purpose

Defines recurring maintenance activities and operational procedures required to keep Ascend databases healthy.

## Philosophy

Routine maintenance should be predictable, automated where safe, observable, and reversible where possible.

## Maintenance Areas

Manage:

- Backups
- Index health
- Statistics
- Storage
- Partition lifecycle
- Replication
- Connections
- Slow queries
- Retention jobs
- Data reconciliation

## Scheduled Work

Every scheduled database job should define:

- Purpose
- Frequency
- Owner
- Runtime limits
- Failure behavior
- Monitoring
- Retry policy

## Index Maintenance

Index maintenance should be driven by database-specific behavior and measured fragmentation or performance signals rather than arbitrary schedules.

## Statistics

Where the database technology uses query statistics or planner metadata, maintain them according to operational requirements.

## Storage Maintenance

Monitor growth and reclaim or archive space according to lifecycle policy.

## Retention Jobs

Retention and deletion jobs must:

- Be scoped
- Be idempotent where possible
- Process data safely
- Record outcomes
- Avoid unexpected load spikes

## Reconciliation Jobs

Reconciliation jobs should compare authoritative and derived state and produce auditable repair results.

## Maintenance Windows

High-impact maintenance should consider:

- Traffic patterns
- Locking
- Replication
- Backup activity
- Deployment activity

## Runbook Structure

Each critical runbook should include:

1. Preconditions
2. Detection
3. Commands/actions
4. Validation
5. Rollback or recovery
6. Escalation

## Automation

Automate repetitive maintenance when:

- The operation is well understood
- Failure behavior is defined
- Observability exists
- Permissions are appropriately restricted

## Emergency Operations

Emergency database access should be:

- Restricted
- Audited
- Time-bounded where possible
- Followed by review

## AI Systems

AI-generated maintenance operations must never execute destructive database actions merely because a model predicts they are safe. High-impact maintenance requires explicit authorization and appropriate tooling.

## Anti-Patterns

Avoid:

- Unowned scheduled jobs
- Unmonitored cleanup
- Destructive maintenance without backups
- Manual recurring procedures that could be safely automated
- Emergency access without auditability

## AI Context

AI coding agents should document new maintenance jobs and provide operational runbooks for database changes that introduce recurring work.

# Next Document

**07-040 — Database Cost & Resource Governance**
