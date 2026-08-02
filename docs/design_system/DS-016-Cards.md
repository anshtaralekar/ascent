---
title: Cards
document_id: DS-016
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002
  - DS-003
  - DS-005
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

# Cards

> "Cards organize information into meaningful, reusable building blocks."

## Purpose

Defines the standard Card component used across Ascend for dashboards, tasks, goals, habits, projects, analytics, AI insights, and settings.

---

# Philosophy

Cards should group related information while remaining modular, scannable, and interactive.

---

# Anatomy

- Container
- Header
- Title
- Subtitle (optional)
- Body
- Metadata
- Actions
- Footer (optional)

---

# Variants

- Standard
- Elevated
- Outlined
- Interactive
- Analytics
- AI Insight
- Dashboard Widget
- Selection Card

---

# Sizes

- Small
- Medium
- Large
- Auto Height

---

# States

- Default
- Hover
- Focus
- Selected
- Expanded
- Collapsed
- Loading
- Disabled

---

# Interaction

Cards may support:

- Click
- Drag & Drop
- Swipe (mobile)
- Context Menu
- Expand / Collapse

Only one primary interaction should dominate.

---

# Content Rules

Cards should present one primary concept.

Avoid overcrowding with unrelated actions.

---

# Accessibility

- Keyboard focus
- Semantic regions
- Screen reader labels
- Visible focus ring
- WCAG-compliant contrast

---

# Tokens

Uses:

- Color
- Typography
- Radius
- Spacing
- Motion
- Elevation

---

# Engineering Notes

Provide a reusable Card component with composable slots for header, body, footer, media, and actions.

---

# AI Context

AI-generated layouts should assemble existing Card variants instead of creating custom containers.

---

# Next Document

**DS-017 — Lists**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
