---
title: Caching & Persistence Strategy
document_id: 07-009
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Caching & Persistence Strategy

> "Fast data is useful only when its freshness and authority are understood."

## Purpose

Defines how Ascend combines durable persistence with caching and derived storage while preserving correctness and clear source-of-truth boundaries.

## Philosophy

Caching is an optimization layer, never an accidental second database.

Every cached value must have a defined:

- Source of truth
- Freshness expectation
- Invalidation strategy
- Authorization scope

## Persistence Classes

Distinguish:

- Primary transactional data
- Derived data
- Ephemeral cache
- Search indexes
- Vector indexes
- Analytics data
- Object storage

## Source of Truth

Each data class must identify its authoritative store.

Derived stores should be reconstructable or refreshable from authoritative data where practical.

## Cache Patterns

Support appropriate patterns such as:

- Cache-aside
- Read-through
- Write-through
- Write-behind where explicitly justified

Choose based on consistency and failure requirements.

## Cache Keys

Keys should include relevant dimensions such as:

- Entity identity
- Query parameters
- Tenant
- Permission scope
- Version
- Locale where applicable

## Invalidation

Use:

- TTL
- Event-driven invalidation
- Version changes
- Explicit invalidation

High-risk stale data should have stronger freshness guarantees.

## AI Data

AI-specific persistence may include:

- Embeddings
- Retrieval indexes
- Conversation summaries
- Long-term memory
- Tool-result caches

These must remain clearly separated between authoritative user data and derived AI artifacts.

## Failure Handling

If a cache fails:

- Fall back to the source where feasible
- Avoid treating cache absence as data absence
- Prevent repeated failures from overwhelming the source
- Monitor recovery

## Privacy

Caches must respect the same or stronger access boundaries as their source data.

Never use shared cache keys that can expose one user's or tenant's data to another.

## Performance

Measure:

- Hit rate
- Miss penalty
- Staleness
- Storage cost
- Invalidation latency
- Source-load reduction

## Governance

Document caching decisions for critical or sensitive data.

## Anti-Patterns

Avoid:

- Caching authorization-sensitive data without scope
- Infinite TTLs
- Cache as the only copy of critical data
- Treating derived indexes as authoritative
- Invalidating without understanding dependency relationships

## AI Context

AI coding agents should identify whether data is authoritative, derived, or ephemeral before choosing a persistence mechanism and must define cache invalidation and privacy boundaries explicitly.

# Next Document

**07-010 — Database Security & Privacy**
