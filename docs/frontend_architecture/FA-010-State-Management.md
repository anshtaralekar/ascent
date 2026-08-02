---
title: State Management
document_id: FA-010
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# State Management

> "Every piece of state should have one clear owner."

## Purpose

Defines how state is created, owned, shared, synchronized, and persisted across Ascend.

---

## Philosophy

Choose the smallest scope capable of solving the problem.

Avoid global state unless multiple independent features require shared ownership.

---

## State Hierarchy

Priority:

1. Local Component State
2. URL State
3. Server State
4. Global State

---

## State Types

### Local State

Use React state for temporary UI interactions.

### URL State

Use for filters, pagination, search, and shareable views.

### Server State

Managed with TanStack Query.

### Global State

Managed with Zustand.

---

## Responsibilities

### Zustand

- UI preferences
- Theme
- Sidebar state
- User session metadata
- Feature flags

### TanStack Query

- API data
- Caching
- Refetching
- Mutations
- Optimistic updates

---

## Persistence

Persist only durable preferences.

Never persist sensitive tokens in client storage.

---

## Performance

- Keep stores small
- Avoid unnecessary subscriptions
- Derive computed values
- Normalize shared data

---

## Anti-Patterns

Avoid:

- Duplicate state
- Fetching server data into Zustand
- Large global stores
- Unnecessary Context providers

---

## Testing

Validate:

- Store updates
- Query invalidation
- Optimistic mutations
- Persistence behavior

---

## AI Context

AI coding agents should always identify the correct state owner before introducing new state.

---

# Next Document

**FA-011 — Data Fetching**
