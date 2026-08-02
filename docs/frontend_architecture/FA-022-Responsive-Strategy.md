---
title: Responsive Strategy
document_id: FA-022
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Responsive Strategy

> "Design once. Adapt everywhere."

## Purpose

Defines how responsive behavior is implemented across Ascend.

---

## Philosophy

Adopt a mobile-first approach while ensuring experiences scale naturally to tablets, desktops, ultrawide displays, and future device categories.

---

## Breakpoints

Support standardized breakpoints for:

- Mobile
- Tablet
- Laptop
- Desktop
- Large Desktop
- Ultrawide

Use design tokens rather than hardcoded values.

---

## Layout Strategy

- Fluid layouts
- Flexible grids
- Container queries where appropriate
- Responsive spacing
- Adaptive typography

---

## Navigation

Adapt navigation by device:

- Bottom navigation (mobile)
- Sidebar (desktop)
- Collapsible navigation (tablet)

---

## Input

Optimize for:

- Touch
- Mouse
- Keyboard
- Stylus

Meet minimum touch target sizes.

---

## Media

Images and video should:

- Scale responsively
- Preserve aspect ratio
- Lazy load when appropriate

---

## Accessibility

Support:

- Zoom
- Orientation changes
- Reduced motion
- Keyboard navigation

---

## Performance

- Responsive images
- Conditional loading
- Code splitting
- Efficient layouts

---

## Anti-Patterns

Avoid:

- Fixed-width layouts
- Device-specific forks
- Horizontal scrolling
- Hidden critical content

---

## AI Context

AI coding agents should build responsive layouts using shared layout primitives instead of device-specific implementations.

---

# Next Document

**FA-023 — Animation Architecture**
