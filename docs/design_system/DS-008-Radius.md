---
title: Radius
document_id: DS-008
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

# Radius

> "Corners shape personality before color or typography."

## Purpose

This document defines the corner radius system for Ascend. All rounded corners must be derived from reusable radius tokens to ensure visual consistency.

---

# Radius Philosophy

Radius communicates the product's character while improving readability and touch ergonomics.

Use a limited, predictable radius scale across the entire interface.

---

# Token Hierarchy

## Primitive Tokens

Raw radius values representing the foundation of the system.

Typical scale:

- None
- XS
- SM
- MD
- LG
- XL
- Full

---

## Semantic Tokens

Meaning-based aliases for UI elements.

Examples:

- radius.card
- radius.button
- radius.input
- radius.dialog
- radius.badge

Components should consume semantic tokens only.

---

# Component Mapping

Standard radius assignments:

- Buttons
- Text Fields
- Cards
- Dialogs
- Bottom Sheets
- Chips
- Badges
- Avatars
- Images

Avoid arbitrary radius values.

---

# Responsive Behavior

Radius should remain consistent across breakpoints.

Increase values only when larger surfaces require softer visual balance.

---

# Accessibility

Rounded corners must never reduce touch target size or clip focus indicators.

---

# Engineering Notes

Expose radius tokens as reusable variables and implement through `border-radius` using semantic token names.

---

# AI Context

AI-generated interfaces should use approved radius tokens instead of custom corner values.

---

# Next Document

**DS-009 — Spacing**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
