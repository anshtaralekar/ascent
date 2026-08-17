---
title: Volume 07 → Volume 13 Handoff Specification
document_id: 07-045
volume: 07
version: 1.0.0
status: Draft
owner: Architecture Team
---

# Volume 07 → Volume 13 Handoff Specification

## Purpose

Defines the database rules and decisions that must be carried forward into Volume 13, `AI_CONTEXT.md`, so AI coding agents implement persistence consistently with the approved architecture.

## Authoritative Database Rules

Volume 13 must preserve the following:

1. Use the approved primary persistence technology.
2. Treat the transactional database as the source of truth for transactional business state.
3. Use the approved data-access layer.
4. Use version-controlled migrations.
5. Enforce critical invariants with database constraints where appropriate.
6. Use parameterized queries.
7. Enforce tenant isolation server-side.
8. Never expose database credentials to clients or ordinary AI model context.
9. Define transaction boundaries explicitly.
10. Make retryable writes idempotent where required.
11. Design indexes from actual access patterns.
12. Bound connection pools and concurrency.
13. Define lifecycle and retention for persistent data.
14. Preserve provenance for AI-derived data.
15. Treat vector/search/cache stores as derived unless explicitly designated otherwise.
16. Monitor important database operations.
17. Provide backup and recovery for critical data.
18. Test migrations and real database behavior.
19. Record material architecture decisions in ADRs.
20. Do not introduce new persistence technologies without architectural justification.

## Volume 13 Mapping

### Chapter 3 — Tech Stack

Must identify the approved database technology and supporting persistence technologies.

### Chapter 4 — Repository Structure

Must define locations for:

- Schemas/models
- Migrations
- Repositories
- Database configuration
- Integration tests
- Seed/test data
- Database utilities

### Chapter 7 — Database Rules

Must incorporate:

- Schema rules
- Migration rules
- Query rules
- Transaction rules
- Integrity rules
- Tenant isolation
- Lifecycle
- AI persistence

### Chapter 8 — API Rules

Must prevent raw database structures from leaking through API contracts.

### Chapter 9 — AI Integration Rules

Must enforce provenance, authorization, lifecycle, and controlled access for AI persistence.

### Chapter 10 — Coding Standards

Must apply database naming, repository, query, transaction, and error-handling conventions.

### Chapter 11 — Naming Standards

Must reference the database naming conventions from Volume 07.

### Chapter 14 — Performance Rules

Must include:

- Query optimization
- Index discipline
- Connection management
- Pagination
- Batching
- Concurrency limits

### Chapter 15 — Security Rules

Must include:

- Least privilege
- Secret handling
- SQL injection prevention
- Tenant isolation
- Sensitive-data protection

### Chapter 17 — Testing Rules

Must require:

- Database integration tests
- Migration tests
- Constraint tests
- Transaction tests
- Concurrency tests where applicable

### Chapter 18 — Deployment Rules

Must define:

- Migration deployment
- Compatibility
- Rollout ordering
- Recovery/forward-fix strategy

### Chapter 19 — Definition of Done

Database work is complete only when architecture, migration, tests, security, performance, observability, and recovery requirements are satisfied.

### Chapter 20 — Forbidden Patterns

Must include:

- Direct production schema editing
- Credentials in source code
- Unparameterized queries
- Client-controlled tenant authorization
- Unbounded queries
- Unversioned migrations
- Unjustified database technologies

### Chapter 21 — Decision Tree

Database decisions should ask:

**Does this require persistence? → What owns the data? → What is the source of truth? → What consistency is required? → What access pattern exists? → What constraints/indexes are required? → How is it migrated/tested/deployed/recovered?**

### Chapter 23 — Self Review Checklist

The database checklist from Volume 07 should be incorporated into the agent's final review.

### Chapter 24 — Repository Map

The actual repository locations should be populated from the implemented project structure.

### Chapter 25 — AI Operating Manual

The agent should inspect existing database architecture before creating persistence and should never invent a competing persistence pattern without justification.

## Handoff Contract

Volume 13 should treat Volume 07 as an upstream architecture authority.

Where a later implementation decision conflicts with Volume 07:

1. Identify the conflict.
2. Do not silently override the architecture.
3. Record the decision.
4. Update the relevant ADR/specification.
5. Propagate the approved change into `AI_CONTEXT.md`.

## Final Rule

**The AI coding agent is an implementation executor, not an unauthorized database architect.**

It may propose alternatives, but architectural deviations require explicit approval.

# Volume 07 Status

**Complete — Database architecture and implementation handoff defined through AI build rules.**
