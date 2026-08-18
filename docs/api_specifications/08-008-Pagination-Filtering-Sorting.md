---
title: Pagination, Filtering & Sorting
document_id: 08-008
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# Pagination, Filtering & Sorting

## Purpose

Defines predictable and scalable collection-query behavior for Ascend APIs.

## Philosophy

Collection APIs must remain bounded and performant regardless of dataset growth.

## Pagination

Every potentially large collection must define pagination.

Possible strategies include:

- Cursor-based pagination
- Offset-based pagination
- Page-number pagination

Use the strategy that matches the workload and consistency requirements.

## Cursor Pagination

Prefer cursor pagination for large or frequently changing datasets where stable traversal is important.

Cursors should be opaque to clients unless there is a deliberate reason otherwise.

## Offset Pagination

Offset pagination may be acceptable for smaller datasets or administrative interfaces where its performance characteristics are understood.

## Page Size

Every collection endpoint must define:

- Default page size
- Maximum page size
- Behavior for invalid values

Clients must not be able to request unbounded result sets.

## Filtering

Filters should be explicitly supported and validated.

Examples include:

- Status
- Date range
- Owner
- Search term
- Resource type

## Tenant Scope

Filtering must never override authorization or tenant boundaries.

## Sorting

Supported sort fields and directions should be allowlisted.

Stable sorting should be used when pagination requires deterministic traversal.

## Date Filters

Date-range queries should define:

- Time zone semantics
- Inclusive/exclusive boundaries
- Maximum range where necessary

## Search

Search parameters should have explicit limits and should use the appropriate search infrastructure rather than generating arbitrary database queries.

## Response Metadata

Paginated responses should communicate enough information for clients to continue traversal without exposing internal database details.

## Consistency

Document whether a paginated traversal represents:

- A moving dataset
- A snapshot
- Best-effort ordering

## Performance

Pagination must be aligned with database access patterns and indexes.

## AI APIs

AI history, runs, tool records, evaluation results, and retrieval results must use bounded pagination when collections can grow.

## Anti-Patterns

Avoid:

- Unlimited collections
- Client-selected arbitrary columns
- Unvalidated filters
- Unbounded date ranges
- Unstable sorting with cursor pagination

## AI Context

AI coding agents must inspect the underlying query and index strategy before implementing collection endpoints and must enforce server-side bounds.

# Next Document

**08-009 — Rate Limiting & Quota Management**
