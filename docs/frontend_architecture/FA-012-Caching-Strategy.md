---
title: Caching Strategy
document_id: FA-012
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Caching Strategy

> "Cache intentionally. Invalidate intelligently."

## Purpose

Defines the caching architecture used across Ascend to maximize performance while maintaining data consistency.

---

## Philosophy

Use the closest appropriate cache to the data source while ensuring freshness requirements are met.

---

## Cache Layers

- React Server Component Cache
- Next.js Data Cache
- TanStack Query Cache
- Browser Cache
- CDN Cache
- Static Asset Cache

---

## Responsibilities

### Server Cache

- Initial page data
- Shared resources
- Metadata

### TanStack Query

- Client-side server state
- Background synchronization
- Optimistic updates

### Browser Cache

- Images
- Fonts
- Static assets

---

## Revalidation

Support:

- Time-based revalidation
- Tag-based revalidation
- Manual invalidation
- Mutation-triggered refresh

---

## Cache Invalidation

Invalidate only affected resources.

Avoid global cache resets unless absolutely necessary.

---

## Offline Support

Persist selected cached resources for offline functionality where appropriate.

---

## Performance

Optimize:

- Cache hit rate
- Memory usage
- Request deduplication
- Network efficiency

---

## Anti-Patterns

Avoid:

- Stale critical data
- Duplicate caches
- Excessive invalidation
- Unbounded cache growth

---

## AI Context

AI coding agents should select the appropriate cache layer before introducing new data-fetching logic.

---

# Next Document

**FA-013 — App Router**
