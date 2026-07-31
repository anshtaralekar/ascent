---
title: Buttons
document_id: DS-011
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-001
  - DS-002
  - DS-005
  - DS-006
  - DS-007
  - DS-008
  - DS-009
  - DS-010

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Buttons

> "Buttons represent commitment. Every press should feel confident, intentional, and predictable."

## Purpose

This document defines the canonical button component for Ascend. Every actionable button in the product must use this specification.

---

# Philosophy

Buttons communicate importance through hierarchy rather than decoration.

Users should instantly recognize:

- Primary action
- Secondary action
- Destructive action
- Disabled action

---

# Variants

## Primary
Highest emphasis. One per major section whenever possible.

## Secondary
Supporting actions with medium emphasis.

## Tertiary
Low emphasis actions within content.

## Ghost
Minimal visual weight for contextual actions.

## Destructive
Irreversible or high-risk actions.

---

# Sizes

- Extra Small
- Small
- Medium (default)
- Large
- Extra Large

Height, padding, and typography must be derived from design tokens.

---

# States

Every variant supports:

- Default
- Hover
- Pressed
- Focused
- Disabled
- Loading
- Success (optional)
- Destructive confirmation (where applicable)

---

# Content Rules

Buttons may contain:

- Text
- Leading icon
- Trailing icon
- Loading spinner

Avoid more than one icon on a standard button.

Labels should begin with clear action verbs.

Examples:

- Create Goal
- Save Changes
- Start Focus Session

---

# Interaction

Buttons should:

- Respond immediately
- Show visual feedback
- Prevent duplicate submissions
- Support keyboard activation
- Preserve accessibility focus

---

# Accessibility

Buttons must:

- Meet minimum touch target sizes
- Support keyboard navigation
- Expose semantic roles
- Maintain WCAG contrast
- Display visible focus indicators

---

# Tokens

Buttons consume:

- Color Tokens
- Typography Tokens
- Radius Tokens
- Spacing Tokens
- Motion Tokens
- Elevation Tokens

No hardcoded values are permitted.

---

# Engineering Notes

Implement a single reusable Button component with variants, sizes, loading state, icon support, and accessibility baked into the API.

---

# AI Context

AI-generated interfaces should compose existing button variants and never invent new button styles.

---

# Next Document

**DS-012 — Icons**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
