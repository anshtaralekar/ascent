---
title: Theme System
document_id: FA-020
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Theme System

> "Themes change appearance, never behavior."

## Purpose

Defines the theming architecture used across Ascend.

---

## Philosophy

Themes are powered by semantic design tokens and CSS variables. Components consume semantic values rather than fixed colors.

---

## Supported Themes

- Light
- Dark
- System
- Future Custom Themes

---

## Theme Architecture

Use:

- CSS Variables
- Semantic Tokens
- Theme Provider

Components must never hardcode theme values.

---

## Theme Switching

Support:

- Manual selection
- System preference detection
- Runtime switching
- Persistent preference

---

## Token Hierarchy

Foundation Tokens → Semantic Tokens → Component Tokens → UI

---

## Accessibility

Every theme must satisfy:

- WCAG AA contrast
- Visible focus
- Reduced motion compatibility
- Color-independent meaning

---

## Performance

- No page reload
- Minimal repaint
- Shared component styles
- Variable-driven updates

---

## Anti-Patterns

Avoid:

- Hardcoded colors
- Theme-specific components
- Duplicate stylesheets
- Runtime style generation

---

## AI Context

AI coding agents should implement styling using semantic theme tokens and CSS variables only.

---

# Next Document

**FA-021 — Dark Mode**
