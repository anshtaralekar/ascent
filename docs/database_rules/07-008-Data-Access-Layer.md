---
title: Data Access Layer
document_id: 07-008
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Access Layer

> "The data-access layer translates business intent into controlled persistence."

## Purpose

Defines the architecture separating application business logic from database-specific operations.

## Philosophy

Services should express domain intent while repositories or equivalent data-access components encapsulate persistence mechanics.

## Layering

Use:

1. API or interface layer
2. Application/service layer
3. Repository or data-access layer
4. ORM/query builder or driver
5. Database

## Repository Responsibilities

Repositories may handle:

- Entity retrieval
- Persistence
- Updates
- Deletes
- Queries
- Transaction participation
- Pagination
- Mapping database records to domain structures

## Service Responsibilities

Services remain responsible for:

- Business rules
- Workflow orchestration
- Authorization decisions
- Domain state transitions
- Coordination across repositories and external systems

Do not hide significant business logic inside generic repository methods.

## Query Design

Repositories should provide intentional operations rather than unrestricted arbitrary querying.

Queries must:

- Be parameterized
- Respect authorization scope
- Limit result size
- Select required fields
- Support documented access patterns

## Transactions

Transaction boundaries should be controlled at the service/workflow level when multiple repository operations must succeed together.

Repositories should participate in an existing transaction context rather than creating hidden independent transactions where inappropriate.

## Mapping

Keep database-specific representations separate from domain representations when doing so improves maintainability and boundary clarity.

## Concurrency

Support domain-required mechanisms such as:

- Optimistic locking
- Version checks
- Unique constraints
- Idempotency

## Error Handling

Translate persistence failures into meaningful application-level errors.

Do not leak:

- SQL statements
- Credentials
- Internal schema details
- Raw database exceptions

## Testing

Test repositories with:

- Integration tests against the actual database technology
- Constraint behavior
- Transaction behavior
- Query correctness
- Representative data volumes

Mocks may supplement but should not replace database integration testing.

## Observability

Record safe telemetry for:

- Query latency
- Operation type
- Failure category
- Transaction context
- Slow queries

Avoid logging sensitive query parameters.

## Governance

Data-access interfaces should remain consistent with the approved domain and schema architecture.

## Anti-Patterns

Avoid:

- SQL scattered throughout business code
- Generic repository abstractions that hide useful query semantics
- Repository methods containing unrelated business decisions
- Unbounded data retrieval
- ORM behavior accepted without understanding generated queries

## AI Context

AI coding agents should place persistence logic behind the approved data-access boundary and verify generated queries, transaction behavior, authorization scope, and performance characteristics.

# Next Document

**07-009 — Caching & Persistence Strategy**
