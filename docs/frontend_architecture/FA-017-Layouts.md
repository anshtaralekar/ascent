---
title: Layouts
document_id: FA-017
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Layouts

> "Layouts provide continuity while pages provide context."

## Purpose

Defines the layout architecture used throughout Ascend to create consistent, reusable page structures.

---

## Philosophy

Layouts should persist shared UI, reduce duplication, preserve state, and improve navigation performance.

---

## Layout Hierarchy

- Root Layout
- Route Group Layouts
- Feature Layouts
- Nested Layouts

---

## Standard Layouts

- Marketing
- Authentication
- Dashboard
- Settings
- Admin

Each layout owns only shared structure, not feature-specific logic.

---

## Persistent Regions

Layouts may contain:

- Sidebar
- Top Navigation
- Footer
- Command Palette
- Notification Center

Persistent regions should remain mounted during navigation.

---

## Nested Layouts

Use nested layouts to:

- Share navigation
- Preserve UI state
- Reduce rerendering
- Improve user experience

---

## Responsive Behavior

Layouts should adapt across:

- Mobile
- Tablet
- Desktop
- Ultrawide

Without changing navigation concepts.

---

## Error & Loading

Each layout may provide:

- loading.tsx
- error.tsx
- not-found.tsx

---

## Accessibility

Layouts must include:

- Landmark regions
- Skip links
- Keyboard navigation
- Focus restoration

---

## Anti-Patterns

Avoid:

- Business logic in layouts
- Deep nesting
- Duplicated navigation
- Layout-specific data ownership

---

## AI Context

AI coding agents should extend existing layouts before introducing new layout hierarchies.

---

# Next Document

**FA-018 — Parallel Routes**
