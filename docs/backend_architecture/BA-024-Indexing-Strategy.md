---
title: Indexing Strategy
document_id: BA-024
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Indexing Strategy

> "Indexes should accelerate the queries that matter, not every column."

## Purpose

Defines the indexing strategy for PostgreSQL databases used by Ascend.

---

## Philosophy

Indexes should be intentional, measurable, and aligned with application query patterns.

---

## Index Types

- Primary indexes
- Unique indexes
- Secondary indexes
- Composite indexes
- Partial indexes
- Full-text indexes

Choose the simplest index that satisfies the query.

---

## Design Principles

- Index frequently filtered columns
- Support common JOIN paths
- Optimize ORDER BY operations
- Minimize duplicate indexes

---

## Naming

Use consistent descriptive names.

Example:

idx_users_email

---

## Composite Indexes

Order indexed columns according to query selectivity and access patterns.

---

## Maintenance

Regularly:

- Analyze query plans
- Remove unused indexes
- Rebuild fragmented indexes
- Monitor storage usage

---

## Performance

Balance:

- Read performance
- Write overhead
- Storage consumption
- Maintenance cost

---

## Monitoring

Track:

- Index hit ratio
- Sequential scans
- Slow queries
- Unused indexes

---

## Anti-Patterns

Avoid:

- Indexing every column
- Duplicate indexes
- Overly wide composite indexes
- Ignoring query plans

---

## AI Context

AI coding agents should create indexes only when justified by query patterns and verify improvements through query analysis.

---

# Next Document

**BA-025 — Query Optimization**
