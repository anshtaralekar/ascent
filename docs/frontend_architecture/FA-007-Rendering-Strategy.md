---
title: Rendering Strategy
document_id: FA-007
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Rendering Strategy

> "Render only what is needed, where it is needed."

## Purpose

Defines the rendering strategies used across Ascend to maximize performance, scalability, SEO, and user experience.

---

## Philosophy

Prefer server rendering by default. Introduce client-side rendering only when interactivity requires it.

---

## Supported Rendering Modes

- React Server Components (RSC)
- Server-Side Rendering (SSR)
- Client-Side Rendering (CSR)
- Static Site Generation (SSG)
- Incremental Static Regeneration (ISR)
- Partial Prerendering (PPR)
- Streaming Rendering

---

## Decision Hierarchy

Choose rendering in this order:

1. RSC
2. SSG / ISR
3. SSR
4. CSR

Use the simplest strategy that satisfies the feature requirements.

---

## Streaming

Use streaming with Suspense boundaries for:

- AI responses
- Dashboards
- Search results
- Long-running requests

---

## Hydration

Hydrate only interactive components.

Avoid hydrating static content.

---

## Performance

Prioritize:

- Fast Time to First Byte
- Fast Largest Contentful Paint
- Minimal JavaScript
- Reduced hydration cost

---

## SEO

Use server rendering for public content requiring indexing.

Avoid client-only rendering for SEO-critical pages.

---

## Anti-Patterns

Avoid:

- Client-rendering entire pages unnecessarily
- Over-hydration
- Nested Suspense without purpose
- Duplicate data fetching

---

## AI Context

AI coding agents should justify every Client Component and rendering strategy according to this document.

---

# Next Document

**FA-008 — Server Components**
