---
title: AI Build Instructions for Database Layer
document_id: 07-025
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# AI Build Instructions for Database Layer

> "The database layer should be generated from architecture, not improvised from a feature request."

## Purpose

Translates Volume 07 database architecture into explicit instructions for AI coding agents implementing Ascend persistence.

## Primary Rule

Before creating or modifying persistent data, the agent must determine:

1. Domain entity
2. Source of truth
3. Ownership
4. Tenant scope
5. Lifecycle
6. Access patterns
7. Integrity requirements
8. Security classification
9. Migration strategy
10. Recovery requirements

## Required Workflow

### Step 1: Inspect

Inspect:

- Existing schema
- Data models
- Migrations
- Repositories
- Services
- Tests
- Database configuration
- Existing ADRs

Do not assume the repository is empty or that a new table is automatically appropriate.

### Step 2: Model

Define:

- Entity
- Relationships
- State
- Ownership
- Constraints
- Lifecycle

Resolve ambiguity before introducing persistent structure.

### Step 3: Design

Determine:

- Table/schema changes
- Indexes
- Transaction boundaries
- Query patterns
- Tenant isolation
- Retention
- Audit requirements

### Step 4: Implement

Implement through the approved data-access architecture.

Do not:

- Modify production databases manually
- Embed credentials
- Bypass repositories without justification
- Introduce an unrelated persistence technology

### Step 5: Migrate

Create a versioned migration.

Assess:

- Compatibility
- Existing data
- Locking
- Backfill
- Rollback or forward-fix
- Deployment ordering

### Step 6: Test

Run relevant:

- Schema tests
- Integration tests
- Constraint tests
- Transaction tests
- Migration tests
- Performance tests
- Security/isolation tests

### Step 7: Observe

Add appropriate:

- Query metrics
- Error telemetry
- Traces
- Slow-query monitoring
- Operational alerts

### Step 8: Review

Before completion verify:

- Source of truth
- Data integrity
- Tenant isolation
- Security
- Performance
- Recovery
- Documentation

## Mandatory Rules

The agent must:

- Use parameterized queries
- Respect tenant scope
- Use approved migrations
- Preserve database constraints
- Avoid sensitive data in logs
- Use least-privilege access
- Define transaction boundaries
- Consider idempotency for retryable writes

## AI/Vector Rules

When implementing AI persistence:

- Preserve source provenance
- Store model/version metadata
- Enforce source authorization
- Define re-index behavior
- Define deletion propagation
- Never treat vectors as automatically authoritative

## New Database Technology

If a feature appears to require a new persistence technology:

1. Check existing architecture
2. Check the decision matrix
3. Identify alternatives
4. Document trade-offs
5. Create/update an ADR
6. Obtain required approval
7. Implement only after the architectural decision is accepted

## Completion Gate

The agent must not declare a database task complete if any required item remains unresolved in:

- Schema
- Migration
- Data access
- Testing
- Security
- Observability
- Recovery
- Documentation

## Forbidden Patterns

Never:

- Put database credentials in code
- Trust client-provided tenant scope
- Log sensitive database values
- Create unversioned schema changes
- Use unrestricted queries
- Delete data without lifecycle rules
- Bypass authorization for AI retrieval
- Introduce a new database without architectural justification

## Final Self-Review

Before reporting completion, answer:

- What is the source of truth?
- What invariants are enforced?
- How is the change migrated?
- What happens under concurrent writes?
- What happens when the database is unavailable?
- How is the data recovered?
- How is tenant isolation enforced?
- How is sensitive data protected?
- How is performance monitored?
- How can the change be safely rolled back or repaired?

## AI Context

This document is the bridge between Volume 07 and Volume 13. Volume 13 should incorporate these rules into the final `AI_CONTEXT.md` so database implementation behavior is enforced consistently across the repository.

# Volume 07 Integration Status

**Database architecture, implementation, operations, and AI build guidance defined.**
