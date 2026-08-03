---
title: Prisma ORM
document_id: BA-021
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Prisma ORM

> "The ORM should enforce correctness, not hide complexity."

## Purpose

Defines how Prisma ORM is used as the primary data access layer for Ascend.

---

## Philosophy

Prisma provides a type-safe abstraction over PostgreSQL while preserving explicit control over data modeling, transactions, and performance.

---

## Schema Organization

Organize models by business domain.

Keep schema readable, modular, and aligned with PostgreSQL design standards.

---

## Model Design

Each model should define:

- Primary key
- Relationships
- Constraints
- Defaults
- Indexes
- Audit fields

Avoid duplicating business logic inside schema definitions.

---

## Client Generation

Generate a single shared Prisma Client.

Reuse the client across requests to minimize connection overhead.

---

## Query Principles

- Prefer type-safe queries
- Select only required fields
- Avoid N+1 queries
- Use eager loading intentionally

---

## Transactions

Support:

- Atomic operations
- Interactive transactions
- Rollbacks
- Optimistic concurrency where appropriate

---

## Soft Deletes

Implement soft deletes through shared abstractions.

Prevent deleted records from appearing in standard queries.

---

## Repository Integration

Repositories should encapsulate Prisma operations.

Business services must not access Prisma Client directly.

---

## Performance

- Batch queries where possible
- Reuse connections
- Optimize relation loading
- Monitor slow queries

---

## Anti-Patterns

Avoid:

- Prisma access inside controllers
- Raw SQL without justification
- Global mutable Prisma instances
- Excessive nested queries

---

## AI Context

AI coding agents should generate database access through repository abstractions built on Prisma Client while preserving type safety and architectural boundaries.

---

# Next Document

**BA-022 — Database Transactions**
