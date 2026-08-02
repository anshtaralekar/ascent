---
title: Parallel Routes
document_id: FA-018
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Parallel Routes

> "Multiple workflows can coexist without competing for navigation."

## Purpose

Defines how Next.js Parallel Routes are used to build multi-panel, context-aware interfaces in Ascend.

---

## Philosophy

Parallel Routes allow independent UI regions to render simultaneously while preserving navigation state and improving productivity.

---

## Use Cases

- Split dashboards
- AI assistant panel
- Side-by-side editors
- Contextual modals
- Activity feeds
- Inspector panels

---

## Named Slots

Use named slots for independent regions such as:

- @main
- @sidebar
- @assistant
- @activity
- @modal

Each slot should have a single, well-defined responsibility.

---

## State Preservation

Parallel routes should preserve:

- Scroll position
- Local UI state
- Active selections
- Open panels

Avoid unnecessary remounts during navigation.

---

## Loading & Errors

Each slot may define:

- loading.tsx
- error.tsx
- default.tsx

Failures in one slot must not affect others.

---

## Streaming

Support independent streaming for:

- AI responses
- Live dashboards
- Notifications
- Search results

---

## Performance

- Lazy load inactive slots
- Stream independently
- Cache shared data
- Avoid duplicate fetching

---

## Accessibility

Provide:

- Keyboard navigation between regions
- Landmark roles
- Focus restoration
- Screen reader announcements

---

## Anti-Patterns

Avoid:

- Excessive simultaneous panels
- Duplicate navigation
- Cross-slot coupling
- Shared mutable state

---

## AI Context

AI coding agents should use Parallel Routes only when independent UI regions provide a measurable usability benefit.

---

# Next Document

**FA-019 — Tailwind Architecture**
