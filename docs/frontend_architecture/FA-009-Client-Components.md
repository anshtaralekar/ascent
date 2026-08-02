---
title: Client Components
document_id: FA-009
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Client Components

> "Use the client only when the browser has meaningful work to do."

## Purpose

Defines standards for React Client Components within Ascend.

---

## Philosophy

Client Components enable interactivity, browser APIs, and local state. They should be introduced only when these capabilities are required.

---

## When to Use

Use Client Components for:

- Forms
- Event handlers
- Local state
- Context providers
- Browser APIs
- Animations
- Drag and drop
- Real-time UI updates

---

## "use client"

Place the directive only at the entry point of an interactive component tree.

Avoid unnecessary propagation of Client Components.

---

## Responsibilities

Client Components may:

- Manage local state
- Handle user interaction
- Consume browser APIs
- Compose other Client Components
- Receive props from Server Components

---

## State

Prefer:

1. Local state
2. Context
3. Zustand (global)
4. TanStack Query (server state)

---

## Performance

- Keep bundles small
- Lazy load interactive features
- Avoid unnecessary re-renders
- Memoize only when beneficial

---

## Accessibility

Interactive components must support:

- Keyboard navigation
- Focus management
- Screen readers
- Reduced motion

---

## Anti-Patterns

Avoid:

- Fetching protected data directly
- Large client-only pages
- Excessive global state
- Browser logic in reusable utilities

---

## AI Context

AI coding agents should justify every `"use client"` directive and prefer Server Components whenever browser capabilities are unnecessary.

---

# Next Document

**FA-010 — State Management**
