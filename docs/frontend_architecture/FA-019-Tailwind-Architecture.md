---
title: Tailwind Architecture
document_id: FA-019
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Tailwind Architecture

> "Utilities should express design decisions, not replace them."

## Purpose

Defines how Tailwind CSS v4 is implemented across Ascend using a token-driven, scalable architecture.

---

## Philosophy

Tailwind provides the implementation layer. The Design System remains the source of truth.

Avoid arbitrary values in production components.

---

## Styling Principles

- Utility-first
- Token-driven
- Mobile-first
- Component-friendly
- Accessible by default

---

## Design Tokens

All styling should consume semantic tokens for:

- Colors
- Typography
- Spacing
- Radius
- Shadows
- Motion

Never hardcode production values.

---

## File Organization

```text
styles/
├── globals.css
├── tokens.css
├── themes.css
└── utilities.css
```

---

## Component Styling

Prefer:

- Utility classes
- Variant utilities
- Composition

Avoid large custom CSS files.

---

## Responsive Design

Use standardized breakpoints.

Prefer container queries when appropriate.

---

## Dark Mode

Implement using theme variables.

Never duplicate component styles.

---

## Performance

- Purge unused classes
- Minimize custom CSS
- Reuse utility patterns
- Keep bundle size small

---

## Anti-Patterns

Avoid:

- Arbitrary values
- Deep selector nesting
- Inline styles
- Duplicated utilities

---

## AI Context

AI coding agents should generate Tailwind code using approved design tokens and reusable utility patterns.

---

# Next Document

**FA-020 — Theme System**
