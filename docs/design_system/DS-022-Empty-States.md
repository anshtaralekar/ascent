---
title: Empty States
document_id: DS-022
version: 1.0.0
status: Draft
owner: Design System Team
---

# Empty States

> "An empty screen is the beginning of a journey, not the end of one."

## Purpose

Defines how Ascend presents empty states across the application, transforming moments without content into opportunities for guidance and action.

---

## Philosophy

Every empty state should answer three questions:

- Why is this empty?
- What can I do next?
- Why should I care?

---

## Empty State Types

- First-time Experience
- No Tasks
- No Projects
- No Goals
- No Habits
- No Notes
- No Search Results
- No Notifications
- Offline
- Permission Required

---

## Anatomy

- Illustration or Icon
- Title
- Supporting Text
- Primary Action
- Secondary Action (optional)
- AI Suggestion (optional)

---

## Copy Guidelines

Copy should be:

- Encouraging
- Action-oriented
- Concise
- Human

Avoid blaming the user.

---

## AI Integration

AI may suggest:

- Create your first task
- Import your calendar
- Generate a study plan
- Build today's schedule
- Recommend habits

Suggestions must always be optional.

---

## States

- Default
- Loading Empty
- Filtered Empty
- Search Empty
- Offline Empty

---

## Accessibility

- Readable text
- Keyboard-accessible actions
- Screen reader support
- Sufficient contrast

---

## Tokens

Uses:

- Color
- Typography
- Spacing
- Motion
- Illustration
- Elevation

---

## Engineering Notes

Provide reusable EmptyState components configurable through title, description, illustration, actions, and AI recommendations.

---

## AI Context

AI should personalize empty states without hiding standard actions.

---

# Next Document

**DS-023 — Loading Components**
