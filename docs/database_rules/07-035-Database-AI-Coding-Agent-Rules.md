---
title: Database AI Coding-Agent Rules
document_id: 07-035
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database AI Coding-Agent Rules

> "An AI coding agent should make database changes as though every schema decision will still exist years after the prompt is forgotten."

## Purpose

Defines mandatory behavior for AI coding agents working on Ascend database code.

## Rule 1: Inspect Before Changing

Before modifying persistence, inspect:

- Existing schema
- Migrations
- Models
- Repositories
- Services
- Tests
- ADRs
- Configuration
- Tenant architecture

Do not generate a new pattern when an approved pattern already exists.

## Rule 2: Identify Ownership

Every new entity must have:

- Owning domain
- Source of truth
- Lifecycle
- Security classification
- Tenant scope where applicable

## Rule 3: Preserve Integrity

Use appropriate:

- Primary keys
- Foreign keys
- Unique constraints
- Check constraints
- Transactions

Do not move critical invariants entirely into application code when concurrent writes can violate them.

## Rule 4: Migrations Are Mandatory

Schema changes must use version-controlled migrations.

Never instruct an application to modify production schema directly at runtime unless the architecture explicitly defines such a mechanism.

## Rule 5: Queries Must Be Safe

Use parameterized queries or safe ORM/query-builder APIs.

Never concatenate untrusted input into SQL.

## Rule 6: Respect Tenant Boundaries

Tenant scope must come from trusted authenticated context.

Never trust a client-provided tenant identifier as authorization.

## Rule 7: Define Consistency

For every state-changing workflow, identify:

- Transaction boundary
- Consistency requirement
- Retry behavior
- Idempotency
- External side effects

## Rule 8: Consider Performance

Before introducing queries, consider:

- Cardinality
- Indexes
- Pagination
- N+1 behavior
- Connection usage
- Query frequency
- Large result sets

## Rule 9: Protect Sensitive Data

Never place database secrets or sensitive values in:

- Source code
- Prompts
- Logs
- Error messages
- Public telemetry

## Rule 10: AI Data Requires Provenance

For embeddings, memory, summaries, or vector records preserve:

- Source reference
- Version
- Tenant scope
- Lifecycle
- Rebuild strategy

## Rule 11: Derived Data Is Not Automatically Truth

Search indexes, caches, vectors, and materialized views should be treated as derived unless explicitly designated otherwise.

## Rule 12: Test Real Behavior

Use actual database integration tests for:

- Constraints
- Queries
- Transactions
- Migrations
- Concurrency
- Isolation

Mocks alone are insufficient for database correctness.

## Rule 13: Plan Failure

Every important database workflow should have a defined response to:

- Timeout
- Connection failure
- Deadlock
- Duplicate execution
- Migration failure
- Partial asynchronous processing

## Rule 14: Preserve Observability

New database workflows should expose safe telemetry for:

- Latency
- Errors
- Operation identity
- Query performance
- Background processing

## Rule 15: Do Not Invent Infrastructure

Do not introduce a new database, vector store, cache, ORM, or persistence technology without architectural justification.

## Required Self-Review

Before submitting a database change, the agent must verify:

- [ ] Domain ownership is clear
- [ ] Source of truth is clear
- [ ] Tenant scope is enforced
- [ ] Constraints are defined
- [ ] Migration exists
- [ ] Queries are parameterized
- [ ] Indexes match access patterns
- [ ] Transactions are intentional
- [ ] Retry behavior is safe
- [ ] Tests cover real persistence behavior
- [ ] Sensitive data is protected
- [ ] Observability exists
- [ ] Recovery implications are understood
- [ ] Documentation/ADR is updated when required

## Forbidden Patterns

The agent must not:

- Create production tables manually
- Embed database credentials
- Bypass authorization
- Trust client tenant scope
- Generate unrestricted SQL
- Store secrets in logs
- Add unbounded queries
- Add indexes without justification
- Treat vectors as authoritative by default
- Skip migrations
- Skip required integration tests
- Introduce new persistence technologies casually

## Completion Rule

The agent may declare a database task complete only when the implementation, migration, testing, security, performance, observability, and documentation requirements appropriate to the change are satisfied.

## Volume 13 Bridge

These rules are intended to become normative implementation rules in:

**Volume 13 → Chapter 7: Database Rules**

and related chapters covering security, performance, testing, deployment, naming, and AI integration.

# Volume 07 Status

**Database architecture is now mapped from foundational design through implementation and AI-agent execution rules.**
