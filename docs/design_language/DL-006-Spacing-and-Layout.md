---
title: Spacing & Layout
document_id: DL-006
version: 1.0.0
status: Draft
owner: Design Team

depends_on:
  - DL-001
  - DL-003
  - DL-005

used_by:
  - UI
  - Engineering
  - Design System
---

# Spacing & Layout

> "Whitespace is not empty. It is structure made visible."

## Purpose

This document defines the spacing, grid, alignment, and layout principles that create consistency across every Ascend experience.

---

# Philosophy

Layouts should feel:

- Balanced
- Predictable
- Spacious
- Efficient
- Calm

Spacing is used to communicate relationships before borders or colors.

---

# Core Principles

- Align before decorating.
- Group related content through spacing.
- Separate unrelated content with larger gaps.
- Maintain a consistent visual rhythm.
- Avoid arbitrary values.

---

# Spacing Scale

Ascend uses an 8-point spacing system.

Recommended tokens:

- XS
- SM
- MD
- LG
- XL
- 2XL
- 3XL

These values should be shared across design and code.

---

# Grid System

Use responsive grids:

- Mobile: 4-column
- Tablet: 8-column
- Desktop: 12-column

Components should snap to the grid whenever practical.

---

# Layout Hierarchy

Every screen contains:

1. Safe Area
2. Navigation
3. Primary Content
4. Supporting Panels
5. Persistent Actions

The primary task should remain visually dominant.

---

# Containers

Use consistent padding for:

- Cards
- Dialogs
- Sheets
- Panels
- Forms

Nested containers should reduce padding gradually to preserve hierarchy.

---

# Alignment Rules

Prefer:

- Left alignment for text
- Consistent edge alignment
- Even spacing between sibling components
- Predictable margins

Avoid visual "jumps" between sections.

---

# Responsive Behavior

Interfaces should adapt without redesign.

Content should reflow gracefully while preserving hierarchy and readability.

---

# Accessibility

Spacing must support:

- Touch targets of at least 44 × 44 px
- Keyboard navigation
- Zoomed layouts
- Reduced cognitive load

---

# Engineering Notes

Spacing values should be implemented as reusable design tokens rather than hard-coded pixel values.

---

# AI Context

AI-generated layouts should use semantic spacing tokens and grid constraints instead of arbitrary positioning.

---

# Next Document

**DL-007 — Motion Language**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
| 1.0.0 | TBD | Design Team | Initial draft |
