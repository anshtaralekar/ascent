---
title: App Router
document_id: FA-013
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# App Router

> "Routes should mirror user journeys, not implementation details."

## Purpose

Defines the routing architecture for Ascend using the Next.js App Router.

---

## Philosophy

Routes are organized by features and user flows while leveraging nested layouts, server rendering, and shared UI.

---

## Route Structure

```text
app/
├── (marketing)/
├── (auth)/
├── (dashboard)/
├── api/
├── layout.tsx
├── loading.tsx
├── error.tsx
└── not-found.tsx
```

---

## Route Types

- Static Routes
- Dynamic Routes
- Catch-all Routes
- Route Groups
- Parallel Routes
- Intercepting Routes
- Route Handlers

---

## Layouts

Use nested layouts to:

- Share navigation
- Preserve state
- Reduce duplication
- Improve transitions

---

## Loading & Errors

Every major route should provide:

- loading.tsx
- error.tsx
- not-found.tsx

Gracefully handle failures.

---

## Metadata

Generate metadata on the server.

Include:

- Title
- Description
- Open Graph
- Twitter Cards
- Canonical URLs

---

## Navigation

Prefer:

- Link prefetching
- Progressive loading
- Shared layouts
- Streaming

---

## Anti-Patterns

Avoid:

- Deeply nested routes
- Duplicate layouts
- Route-specific business logic
- Client-only routing without justification

---

## AI Context

AI coding agents should follow the App Router conventions and place new pages within the correct route group.

---

# Next Document

**FA-014 — Navigation Architecture**
