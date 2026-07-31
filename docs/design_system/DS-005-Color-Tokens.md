---
title: Color Tokens
document_id: DS-005
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Color Tokens

> "Color should communicate meaning before decoration."

## Purpose

This document defines the color token architecture for Ascend. All UI colors must originate from design tokens rather than hardcoded values.

---

# Token Structure

## Primitive Tokens

Raw palette values grouped into:

- Neutral
- Primary
- Secondary
- Success
- Warning
- Error
- Info

These values should never be referenced directly by components.

---

## Semantic Tokens

Semantic tokens describe intent rather than appearance.

Examples:

- color.background.primary
- color.surface.secondary
- color.text.primary
- color.border.default
- color.action.primary

Components must consume semantic tokens.

---

# Surface Hierarchy

Standard surfaces include:

- App background
- Primary surface
- Secondary surface
- Elevated surface
- Modal surface
- Overlay

Each surface must maintain sufficient contrast with its contents.

---

# Text Hierarchy

Define tokens for:

- Primary text
- Secondary text
- Tertiary text
- Disabled text
- Inverse text
- Link text

---

# Interactive States

Each interactive element supports:

- Default
- Hover
- Pressed
- Focus
- Disabled

State colors should be derived from semantic tokens.

---

# Status Colors

Provide consistent tokens for:

- Success
- Warning
- Error
- Information

These tokens should be reused across alerts, badges, forms, and notifications.

---

# Themes

Support:

- Light Theme
- Dark Theme
- High Contrast (future)

Themes should override semantic values while preserving token names.

---

# Accessibility

All color combinations must satisfy contrast requirements for text, icons, controls, and focus indicators.

Color alone must never convey critical information.

---

# Engineering Notes

Expose tokens as platform-specific variables (CSS variables, mobile resources, etc.) generated from a single source.

---

# AI Context

AI-generated interfaces should reference semantic color tokens only.

---

# Next Document

**DS-006 — Typography Tokens**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
