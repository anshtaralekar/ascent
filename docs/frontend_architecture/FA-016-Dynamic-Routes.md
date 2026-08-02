---
title: Dynamic Routes
document_id: FA-016
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Dynamic Routes

> "URLs should represent resources, not implementation."

## Purpose

Defines standards for implementing dynamic routes throughout Ascend.

---

## Philosophy

Dynamic routes should be predictable, stable, SEO-friendly, and map directly to business entities.

---

## Route Types

- Dynamic Segments
- Nested Dynamic Routes
- Catch-all Routes
- Optional Catch-all Routes

---

## Naming

Prefer meaningful slugs when user-facing.

Use immutable IDs internally when appropriate.

Example:

`/projects/my-first-project`

rather than opaque identifiers where possible.

---

## Data Fetching

Dynamic pages should fetch data in Server Components by default.

Validate route parameters before querying.

---

## Rendering

Choose between:

- Static Generation
- ISR
- Server Rendering

based on data freshness.

---

## Error Handling

Provide:

- Invalid parameter handling
- 404 pages
- Authorization checks
- Graceful fallbacks

---

## SEO

Generate metadata dynamically.

Include:

- Canonical URLs
- Open Graph
- Structured metadata

---

## Performance

- Prefetch likely routes
- Cache appropriate data
- Avoid duplicate fetches

---

## Security

Never trust route parameters.

Validate ownership and permissions for protected resources.

---

## Anti-Patterns

Avoid:

- Exposing internal identifiers unnecessarily
- Duplicate route structures
- Client-side authorization
- Invalid slug generation

---

## AI Context

AI coding agents should follow established route conventions and validate all dynamic parameters before use.

---

# Next Document

**FA-017 — Layouts**
