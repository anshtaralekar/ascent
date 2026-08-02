---
title: Data Fetching
document_id: FA-011
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Data Fetching

> "Fetch data once, cache it intelligently, and keep it fresh."

## Purpose

Defines the standardized data-fetching architecture for Ascend.

---

## Philosophy

Prefer server-side data fetching whenever possible. Client-side fetching should be reserved for interactive, frequently changing, or user-triggered data.

---

## Fetching Hierarchy

1. Server Components
2. Server Actions
3. TanStack Query
4. Direct browser requests (only when justified)

---

## Responsibilities

### Server Components

- Initial page data
- SEO content
- Dashboard composition

### TanStack Query

- Cached server state
- Background refetching
- Mutations
- Pagination
- Infinite queries

---

## API Layer

All requests should pass through a shared API client.

Avoid direct fetch calls scattered throughout components.

---

## Error Handling

Provide:

- Retry policies
- User-friendly errors
- Error boundaries
- Graceful degradation

---

## Performance

Optimize through:

- Request deduplication
- Parallel fetching
- Streaming
- Pagination
- Lazy loading

---

## Authentication

Authenticated requests should automatically attach session credentials through the API client.

---

## Anti-Patterns

Avoid:

- Duplicate requests
- Fetching in deeply nested components
- Business logic inside UI
- Ignoring cache invalidation

---

## AI Context

AI coding agents should always determine whether data belongs in Server Components or TanStack Query before introducing client-side fetching.

---

# Next Document

**FA-012 — Caching Strategy**
