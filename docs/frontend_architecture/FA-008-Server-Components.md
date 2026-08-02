---
title: Server Components
document_id: FA-008
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Server Components

> "Run work on the server whenever the browser gains nothing from doing it."

## Purpose

Defines standards for using React Server Components (RSC) in Ascend.

---

## Philosophy

Server Components are the default building block for pages and layouts. They reduce client-side JavaScript, improve performance, and simplify secure data access.

---

## Use Cases

Use Server Components for:

- Page composition
- Layouts
- Initial data fetching
- Dashboard rendering
- Metadata generation
- SEO content

Avoid them for browser-only interactions.

---

## Responsibilities

Server Components may:

- Fetch data
- Read cookies and headers
- Call backend services
- Compose Client Components
- Stream UI

They must not depend on browser APIs.

---

## Composition

- Server Components may render Client Components.
- Client Components cannot import Server Components.
- Pass serializable props across boundaries.

---

## Data Fetching

Prefer fetching directly in Server Components.

Avoid duplicate requests between server and client.

---

## Caching

Use framework caching where appropriate.

Choose cache policies intentionally based on data freshness.

---

## Security

Keep secrets, tokens, and privileged logic on the server.

Never expose confidential values to the client.

---

## Performance

- Minimize waterfalls
- Stream independent sections
- Keep payloads small
- Reduce hydration

---

## Anti-Patterns

- Browser APIs in RSC
- Interactive state in RSC
- Over-fetching
- Duplicate network requests

---

## AI Context

AI coding agents should default to Server Components unless client-side interactivity explicitly requires a Client Component.

---

# Next Document

**FA-009 — Client Components**
