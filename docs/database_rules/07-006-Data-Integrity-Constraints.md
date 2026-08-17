---
title: Data Integrity & Constraints
document_id: 07-006
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Integrity & Constraints

> "Integrity is the database's promise that valid state remains valid."

## Purpose

Defines the mechanisms used to ensure Ascend data remains accurate, consistent, complete, and valid regardless of which application component writes it.

## Philosophy

Critical invariants should be enforced as close to the source of truth as practical. Application validation improves user experience, while database constraints provide durable protection.

## Integrity Layers

Use:

1. Application validation
2. Service-level business rules
3. Database constraints
4. Transaction boundaries
5. Operational reconciliation

## Constraint Types

Support:

- Primary keys
- Foreign keys
- Unique constraints
- NOT NULL constraints
- CHECK constraints
- Domain-specific validation

## Referential Integrity

Foreign-key relationships should prevent invalid references where the domain requires strict ownership.

Deletion behavior must be explicitly selected:

- Restrict
- Cascade
- Set null
- Archive through application workflow

## Uniqueness

Define uniqueness for business identifiers that must not be duplicated.

Consider:

- Tenant scope
- Case sensitivity
- Normalization
- Lifecycle state
- Concurrent creation

## Business Invariants

Important invariants should be documented and enforced consistently.

Examples include:

- One active record per defined scope
- Valid state transitions
- Non-negative quantities
- Valid ownership relationships
- Unique external identifiers

## Validation Boundaries

Validate early at the API and service layers, but do not rely solely on application checks for invariants vulnerable to concurrency.

## Reconciliation

For derived or distributed data, provide periodic reconciliation where appropriate.

Reconciliation should identify:

- Missing records
- Duplicate records
- Broken relationships
- Unexpected state
- Divergence between source and derived stores

## Integrity Failures

Handle constraint failures as expected operational conditions where appropriate.

Do not expose raw database errors directly to users.

## Monitoring

Track:

- Constraint violations
- Reconciliation failures
- Data-quality anomalies
- Duplicate attempts
- Referential integrity issues

## Governance

Critical integrity rules require documentation and review when changed.

## Anti-Patterns

Avoid:

- Application-only uniqueness checks
- Disabling constraints to simplify migrations
- Silent integrity repair
- Treating corrupted data as a normal state

## AI Context

AI coding agents must identify critical invariants before implementing persistent workflows and should enforce them through the strongest appropriate combination of application logic, transactions, and database constraints.

# Next Document

**07-007 — Database Migrations**
