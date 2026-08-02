---
title: Navigation Architecture
document_id: FA-014
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Navigation Architecture

> "Navigation should make every destination feel one step away."

## Purpose

Defines the navigation architecture across all Ascend applications.

---

## Philosophy

Navigation should be predictable, fast, accessible, and consistent across desktop, tablet, and mobile experiences.

---

## Navigation Layers

- Global Navigation
- Context Navigation
- Sidebar
- Top Bar
- Bottom Navigation
- Breadcrumbs
- Command Palette

---

## Global Navigation

Provides access to primary product areas.

Keep structure stable across sessions.

---

## Sidebar

Use for authenticated workspaces.

Supports:

- Collapse
- Pinning
- Favorites
- Recent items

---

## Top Navigation

Contains:

- Search
- Notifications
- AI Assistant
- User Profile
- Quick Actions

---

## Mobile Navigation

Use a bottom navigation bar for primary destinations and a drawer for secondary navigation.

---

## URL Design

URLs should be:

- Human readable
- Shareable
- Stable
- REST-like where applicable

---

## Keyboard Support

Support:

- Tab navigation
- Arrow navigation
- Cmd/Ctrl + K
- Escape
- Focus restoration

---

## Accessibility

Navigation must include:

- Landmark regions
- Visible focus
- Screen reader labels
- Keyboard-only usability

---

## Performance

- Prefetch likely routes
- Preserve layouts
- Avoid unnecessary remounts

---

## Anti-Patterns

Avoid:

- Hidden navigation
- Multiple competing menus
- Broken back navigation
- Inconsistent hierarchy

---

## AI Context

AI coding agents should integrate new features into the existing navigation hierarchy instead of creating isolated navigation paths.

---

# Next Document

**FA-015 — Protected Routes**
