---
title: Spacing
document_id: DS-009
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002
  - DS-003

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Spacing

> "Spacing is the rhythm that makes interfaces feel calm, readable, and intentional."

## Purpose

This document defines the spacing system for Ascend. Every margin, padding, gap, and inset must be derived from reusable spacing tokens instead of arbitrary values.

---

# Spacing Philosophy

Ascend uses a predictable spacing scale to create visual harmony across screens. Consistent spacing reduces cognitive load and improves scanability.

---

# Base Unit

The primary spacing unit is **8 pt**.

A **4 pt** subdivision may be used for compact adjustments where finer control is required.

---

# Token Hierarchy

## Primitive Tokens

Raw spacing values.

Typical scale:

- 0
- 4
- 8
- 12
- 16
- 24
- 32
- 40
- 48
- 64
- 80
- 96

---

## Semantic Tokens

Meaning-based aliases.

Examples:

- spacing.page.padding
- spacing.card.padding
- spacing.form.gap
- spacing.section
- spacing.inline.small

Components should reference semantic tokens only.

---

# Usage Guidelines

Apply spacing consistently for:

- Page margins
- Section separation
- Card padding
- Form layouts
- Lists
- Tables
- Navigation
- Dialogs

Avoid manual pixel adjustments.

---

# Vertical Rhythm

Maintain a consistent rhythm between headings, body text, controls, and content blocks.

Group related content more closely than unrelated content.

---

# Responsive Behavior

Spacing should scale gracefully across:

- Mobile
- Tablet
- Desktop

Larger displays may increase whitespace without changing the underlying spacing scale.

---

# Density Modes

Support:

- Comfortable
- Compact

Density changes should affect spacing tokens rather than component logic.

---

# Accessibility

Spacing must preserve readable layouts, minimum touch targets, and clear separation between interactive elements.

---

# Engineering Notes

Expose spacing tokens as reusable variables and implement with standardized spacing utilities.

---

# AI Context

AI-generated layouts should compose approved spacing tokens instead of arbitrary gaps.

---

# Next Document

**DS-010 — Motion Tokens**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
