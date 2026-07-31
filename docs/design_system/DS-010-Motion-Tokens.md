---
title: Motion Tokens
document_id: DS-010
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002
  - DS-009

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Motion Tokens

> "Motion should explain change, reinforce continuity, and never compete for attention."

## Purpose

This document defines the motion token system for Ascend. Animations and transitions should be driven by reusable tokens rather than custom timing values.

---

# Motion Philosophy

Motion should:

- Guide attention
- Clarify cause and effect
- Reinforce hierarchy
- Provide feedback
- Feel responsive

Avoid decorative animation that slows users or distracts from tasks.

---

# Token Hierarchy

## Primitive Tokens

Raw values for:

- Duration
- Delay
- Easing
- Scale
- Opacity

---

## Semantic Tokens

Meaning-based motion tokens.

Examples:

- motion.duration.fast
- motion.duration.normal
- motion.easing.standard
- motion.transition.page
- motion.feedback.success

Components should consume semantic tokens only.

---

# Duration Scale

Standard durations:

- Instant
- Fast
- Normal
- Slow

Choose the shortest duration that communicates the change clearly.

---

# Easing

Approved easing curves include:

- Standard
- Emphasized
- Decelerate
- Accelerate
- Linear

Use consistent easing across the product.

---

# Motion Patterns

Support standardized patterns for:

- Hover
- Press
- Focus
- Expand / Collapse
- Dialogs
- Navigation
- Page transitions
- Loading
- AI responses

---

# Accessibility

Respect reduced-motion preferences.

Critical information must never rely solely on animation.

---

# Performance

Prefer GPU-accelerated properties such as transform and opacity.

Avoid expensive layout-triggering animations where possible.

---

# Engineering Notes

Expose motion values as reusable design tokens. Centralize transitions to ensure consistency across platforms.

---

# AI Context

AI-generated interfaces should apply approved motion tokens and avoid inventing new animation behaviors.

---

# Next Document

**DS-011 — Buttons**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
