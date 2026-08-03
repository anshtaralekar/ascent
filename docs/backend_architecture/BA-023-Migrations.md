---
title: Migrations
document_id: BA-023
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Migrations

> "Every schema change should be intentional, reversible in planning, and safe in execution."

## Purpose

Defines the database migration strategy for Ascend.

---

## Philosophy

Schema evolution must be version-controlled, automated, repeatable, and validated before reaching production.

---

## Migration Principles

- Version-controlled
- Forward-first
- Reproducible
- Reviewed
- Tested

---

## Migration Lifecycle

1. Design schema change
2. Generate migration
3. Review SQL
4. Validate locally
5. Test in staging
6. Deploy
7. Verify

---

## Migration Types

- Schema migrations
- Data migrations
- Seed updates
- Index migrations

---

## Zero-Downtime

Prefer:

- Expand then contract
- Backward-compatible schema
- Incremental rollouts
- Deferred cleanup

---

## Rollback

Support rollback planning.

Where rollback is unsafe, provide compensating forward migrations.

---

## CI/CD

Every migration should:

- Run automatically
- Be validated
- Block deployment on failure
- Produce migration reports

---

## Validation

Verify:

- Data integrity
- Constraints
- Performance
- Compatibility

---

## Backup

Coordinate production migrations with backup and recovery procedures.

---

## Anti-Patterns

Avoid:

- Manual production edits
- Destructive migrations without planning
- Large blocking schema changes
- Untested migrations

---

## AI Context

AI coding agents should generate migrations through Prisma Migrate, preserve migration history, and prefer backward-compatible schema evolution.

---

# Next Document

**BA-024 — Indexing Strategy**
