---
title: Dark Mode
document_id: FA-021
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Dark Mode

> "Dark mode is a first-class experience, not an inverted theme."

## Purpose

Defines the implementation standards for dark mode across Ascend.

---

## Philosophy

Dark mode should improve comfort, maintain accessibility, and preserve the visual hierarchy established by the Design System.

---

## Design Principles

- Semantic color mapping
- Consistent elevation
- Accessible contrast
- Comfortable long-duration viewing
- No duplicated components

---

## Color Strategy

Use semantic tokens for:

- Backgrounds
- Surfaces
- Text
- Borders
- Accents
- Feedback colors

Never hardcode dark-specific colors inside components.

---

## Theme Behavior

Support:

- Light
- Dark
- System Preference

Theme changes should occur without page reloads.

---

## Media

Adapt:

- Logos
- Icons
- Illustrations
- Charts

Images should remain readable across themes.

---

## Accessibility

Every dark theme must satisfy:

- WCAG 2.2 AA contrast
- Visible focus indicators
- Color-independent status indicators
- Reduced motion compatibility

---

## Performance

- CSS variable switching
- Minimal repaint
- Shared component styles
- Persistent theme preference

---

## Anti-Patterns

Avoid:

- Pure black backgrounds by default
- Inverted images
- Theme-specific business logic
- Duplicate stylesheets

---

## AI Context

AI coding agents should build every component using semantic theme tokens so dark mode works automatically.

---

# Next Document

**FA-022 — Responsive Strategy**
