---
title: Dialogs
document_id: DS-025
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-007
  - DS-010

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Dialogs

> "Interrupt the user only when the interruption is more valuable than their current task."

## Purpose

Defines reusable dialog, modal, and overlay components used across Ascend.

---

## Philosophy

Dialogs should capture attention only when necessary and always provide a clear path forward.

---

## Dialog Types

- Modal Dialog
- Alert Dialog
- Confirmation Dialog
- Destructive Confirmation
- AI Review Dialog
- Bottom Sheet
- Side Sheet
- Full-screen Dialog
- Popover

---

## Anatomy

- Overlay
- Container
- Title
- Description
- Content
- Actions
- Close Control

---

## States

- Opening
- Open
- Loading
- Error
- Success
- Closing

---

## Interaction

Support:

- Keyboard navigation
- Escape key
- Outside click (when appropriate)
- Focus trapping
- Multi-step workflows

---

## Accessibility

Dialogs must:

- Trap focus
- Restore focus on close
- Support screen readers
- Expose semantic roles
- Meet WCAG contrast requirements

---

## Tokens

Uses:

- Color
- Typography
- Radius
- Spacing
- Motion
- Elevation

---

## Engineering Notes

Implement reusable dialog primitives supporting composable content, accessibility, transitions, and responsive layouts.

---

## AI Context

AI-generated confirmations and review flows should reuse approved dialog components.

---

# Next Document

**DS-026 — AI Components**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
