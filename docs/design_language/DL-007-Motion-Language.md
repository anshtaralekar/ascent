---
title: Motion Language
document_id: DL-007
version: 1.0.0
status: Draft
owner: Design Team

depends_on:
  - DL-001
  - DL-003
  - DL-006

used_by:
  - UI
  - Motion Design
  - Engineering
---

# Motion Language

> "Motion should explain, reassure, and guide. Never distract."

## Purpose

This document defines how motion is used throughout Ascend to communicate hierarchy, state changes, spatial relationships, and user feedback.

Motion is not decoration. It is functional communication.

---

# Motion Philosophy

Every animation should answer at least one question:

- What changed?
- Where did it go?
- What should I focus on next?
- Was my action successful?

If it answers none of these, it should not exist.

---

# Motion Principles

## Purpose Before Beauty

Animations must communicate meaning before aesthetics.

Good motion reduces cognitive effort.

---

## Natural Continuity

Objects should move as though they exist in a consistent physical space.

Avoid sudden appearance or disappearance when continuity improves understanding.

---

## Calm by Default

Motion should feel smooth and subtle.

Avoid exaggerated effects, unnecessary bounces, or attention-seeking transitions.

---

## Responsive Feedback

Every user action deserves an appropriate response.

Examples:

- Button press
- Drag interaction
- Card expansion
- Task completion
- AI response generation

Feedback should feel immediate and predictable.

---

# Motion Hierarchy

### Level 1 — Micro Interactions

Examples:

- Hover
- Press
- Focus
- Checkbox
- Toggle
- Ripple

Duration:

100–200 ms

---

### Level 2 — Component Motion

Examples:

- Cards
- Dialogs
- Sheets
- Menus
- Tooltips

Duration:

200–350 ms

---

### Level 3 — Screen Transitions

Examples:

- Navigation
- Workflow progression
- Dashboard changes

Duration:

250–450 ms

---

# Easing

Prefer smooth acceleration and deceleration.

Avoid linear movement except for continuous indicators like progress bars.

---

# Loading States

Use:

- Skeleton loaders
- Progress indicators
- Gentle shimmer
- AI thinking animation

Avoid spinning indicators when meaningful progress can be shown.

---

# Success & Error Motion

Success should feel satisfying but restrained.

Errors should attract attention without creating anxiety.

---

# Accessibility

Users must be able to:

- Reduce motion
- Disable non-essential animations
- Preserve usability without animation

---

# Performance Goals

Animations should maintain:

- 60 FPS minimum
- 120 FPS where supported

Dropped frames are considered design defects.

---

# Engineering Notes

Motion timings, easing curves, and transitions should be implemented as reusable design tokens.

---

# AI Context

AI-generated interfaces should use motion only when it improves comprehension.

---

# Next Document

**DL-008 — Iconography**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
| 1.0.0 | TBD | Design Team | Initial draft |
