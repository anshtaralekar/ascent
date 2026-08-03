---
title: Query Optimization
document_id: BA-025
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Query Optimization

> "Fast queries are designed, measured, and continuously refined."

## Purpose

Defines the query optimization strategy for all database operations in Ascend.

---

## Philosophy

Every query should retrieve only the required data with minimal latency while preserving correctness and maintainability.

---

## Query Principles

- Select only required columns
- Filter early
- Limit result sets
- Prefer indexed access
- Keep queries predictable

---

## JOIN Optimization

Use joins intentionally.

Avoid unnecessary joins and excessive table chaining.

Optimize join order using query plans.

---

## Pagination

Support:

- Cursor-based pagination
- Offset pagination where appropriate
- Stable ordering
- Configurable page sizes

---

## N+1 Prevention

Prevent N+1 queries through:

- Eager loading
- Batch fetching
- Data loaders
- Optimized relation queries

---

## Connection Management

- Reuse pooled connections
- Minimize idle connections
- Configure pool sizes appropriately
- Monitor connection usage

---

## Performance Monitoring

Analyze:

- EXPLAIN plans
- Slow query logs
- Query execution time
- Index utilization

---

## Caching

Cache:

- Frequently accessed reference data
- Expensive read queries
- AI metadata where appropriate

Always define cache invalidation rules.

---

## Anti-Patterns

Avoid:

- SELECT *
- Unbounded result sets
- Repeated identical queries
- Missing WHERE clauses on large tables

---

## AI Context

AI coding agents should optimize queries using Prisma best practices, validate execution plans, and prevent N+1 query patterns before implementation.

---

# Next Document

**BA-026 — AI Gateway**
