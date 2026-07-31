---
title: Elevation & Shadows
document_id: DS-007
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002
  - DS-005

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Elevation & Shadows

> "Depth should explain relationships, not decorate interfaces."

## Purpose

This document defines how Ascend communicates depth, hierarchy, and focus through elevation, shadows, overlays, and layering.

---

# Elevation Philosophy

Elevation conveys meaning by showing which elements are interactive, floating, or temporarily above other content.

Use elevation sparingly. More depth should indicate greater importance or user focus.

---

# Elevation Levels

Standard elevation tiers:

- Level 0: Background
- Level 1: Cards and surfaces
- Level 2: Floating controls
- Level 3: Dropdowns and popovers
- Level 4: Dialogs and side panels
- Level 5: Critical overlays and system prompts

Components should reference elevation tokens rather than custom shadow values.

---

# Shadow Tokens

Shadow tokens define reusable depth styles.

Each token includes:

- Offset
- Blur radius
- Spread
- Opacity

Example naming:

- elevation.surface.low
- elevation.surface.medium
- elevation.overlay.high

---

# Layering Principles

Higher layers should:

- Never obscure critical navigation unnecessarily
- Maintain clear visual separation
- Preserve contextual awareness

Use overlays to reduce background distraction rather than increasing shadow intensity.

---

# Interactive States

Interactive components may adjust elevation for:

- Hover
- Pressed
- Dragging
- Focus

Changes should be subtle and accompanied by motion where appropriate.

---

# Themes

Shadow and elevation tokens should adapt for:

- Light Theme
- Dark Theme

Dark mode may rely more on tonal contrast than heavy shadows.

---

# Accessibility

Depth must not be the sole indicator of state or hierarchy.

Ensure focus indicators remain visible regardless of elevation.

---

# Engineering Notes

Implement elevation using reusable shadow tokens and z-index layers. Avoid arbitrary shadow values within components.

---

# AI Context

AI-generated interfaces should compose approved elevation tokens instead of introducing custom shadow styles.

---

# Next Document

**DS-008 — Radius**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
