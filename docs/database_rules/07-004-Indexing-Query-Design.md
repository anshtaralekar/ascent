---
title: Indexing & Query Design
document_id: 07-004
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Indexing & Query Design

> "An index is a performance decision with a storage and write cost."

## Purpose

Defines how Ascend designs database indexes and queries for predictable performance without creating unnecessary storage or write overhead.

## Philosophy

Indexes should be driven by real access patterns, measured workload characteristics, and query plans rather than added speculatively.

## Query-First Design

For important entities, identify:

- Common filters
- Sort operations
- Joins
- Pagination patterns
- Aggregations
- Lookup frequency
- Expected cardinality

Schema and index decisions should support these known access patterns.

## Index Selection

Consider indexes for:

- Primary keys
- Foreign keys where beneficial
- Frequently filtered columns
- Common sort keys
- Unique business identifiers
- Composite query patterns

## Composite Indexes

Design composite indexes according to actual query predicates and ordering.

Column order matters and must be justified by the dominant access pattern.

## Selectivity

High-selectivity columns are generally stronger index candidates than low-selectivity columns, but workload and query structure remain the deciding factors.

## Query Design

Queries should:

- Select only required data
- Use parameterized values
- Apply appropriate filters
- Avoid unnecessary joins
- Avoid accidental full-table scans
- Respect pagination limits

## Pagination

Prefer stable pagination strategies for large or changing datasets.

Cursor-based pagination should be considered for high-volume ordered datasets where offset pagination becomes inefficient or unstable.

## N+1 Prevention

Data-access code should detect and prevent repetitive queries caused by fetching related records one item at a time.

Use:

- Joins
- Batch retrieval
- Explicit prefetching
- Data-loader patterns where appropriate

## Query Safety

Never construct queries through unsafe string concatenation with untrusted input.

Use parameterized queries or safe ORM/query-builder mechanisms.

## Query Plans

Important queries should be examined using database query-plan tooling.

Monitor for:

- Full scans
- Inefficient joins
- Excessive sorting
- Poor cardinality estimates
- Index misuse

## Index Lifecycle

Indexes should be:

- Named consistently
- Version-controlled
- Created through migrations
- Monitored for usefulness
- Removed when demonstrably unnecessary

## Trade-offs

Every index adds potential:

- Storage cost
- Write amplification
- Maintenance cost
- Migration time

Optimize the complete workload rather than read performance alone.

## Monitoring

Track:

- Query latency
- Slow-query frequency
- Index usage
- Lock waits
- Scan frequency
- Database CPU and I/O

## Governance

Performance-sensitive query changes should include:

- Before/after measurements
- Query-plan evidence where appropriate
- Expected workload impact

## Anti-Patterns

Avoid:

- Indexing every column
- Blindly copying indexes between tables
- Unbounded queries
- Offset pagination at massive scale without justification
- Ignoring query plans

## AI Context

AI coding agents should infer indexes from documented access patterns and validate important queries against realistic data volumes before declaring database performance acceptable.

# Next Document

**07-005 — Transactions & Data Consistency**
