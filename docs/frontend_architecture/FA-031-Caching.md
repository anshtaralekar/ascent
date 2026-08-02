---
title: Caching
document_id: FA-031
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Caching

> "Cache where it improves speed. Invalidate where correctness matters."

## Purpose

Defines the frontend caching architecture for Ascend.

---

## Philosophy

Use layered caching to minimize latency while ensuring users receive accurate, up-to-date information.

---

## Cache Layers

- Browser Cache
- CDN Cache
- Next.js Data Cache
- React Server Component Cache
- TanStack Query Cache
- Memory Cache

Each layer has a clearly defined responsibility.

---

## Browser Cache

Cache:

- Fonts
- Images
- Static assets
- Icons

Use long-lived immutable cache headers.

---

## Application Cache

Use Next.js and TanStack Query for:

- API responses
- Server-rendered data
- Background synchronization
- Optimistic updates

---

## Invalidation

Support:

- Time-based expiration
- Tag-based revalidation
- Mutation-driven invalidation
- Manual refresh

Invalidate only affected resources.

---

## Offline

Persist selected cache entries to support offline functionality.

Avoid caching sensitive information locally.

---

## Monitoring

Track:

- Cache hit ratio
- Miss ratio
- Revalidation frequency
- Stale responses

---

## Anti-Patterns

Avoid:

- Infinite cache growth
- Duplicate cache layers
- Global invalidation
- Caching confidential data

---

## AI Context

AI coding agents should use existing cache abstractions and define invalidation rules whenever introducing cached data.

---

# Next Document

**FA-032 — PWA**
