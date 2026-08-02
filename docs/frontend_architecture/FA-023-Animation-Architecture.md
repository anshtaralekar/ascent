---
title: Animation Architecture
document_id: FA-023
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Animation Architecture

> "Motion should communicate, not decorate."

## Purpose

Defines how animations are implemented across Ascend using reusable motion primitives.

---

## Philosophy

Animations should reinforce hierarchy, provide feedback, and guide attention while remaining performant and accessible.

---

## Technology

Primary library:

- Framer Motion

Native CSS transitions should be preferred for simple interactions.

---

## Motion Categories

- Route transitions
- Layout animations
- Microinteractions
- Hover states
- Focus transitions
- Loading animations
- Skeletons
- AI streaming
- Notifications

---

## Principles

- Functional first
- Consistent timing
- Interruptible
- GPU accelerated
- Reduced motion support

---

## Performance

- Animate transforms and opacity
- Avoid layout thrashing
- Lazy load animation libraries
- Respect 60 FPS budget

---

## Accessibility

Support:

- prefers-reduced-motion
- Keyboard parity
- Focus visibility
- Non-animated alternatives

---

## Design Tokens

Use shared motion tokens for:

- Duration
- Easing
- Delay
- Springs

---

## Anti-Patterns

Avoid:

- Autoplay animations
- Excessive motion
- Blocking transitions
- Multiple competing animations

---

## AI Context

AI coding agents should implement animations using shared motion primitives and tokenized timing values.

---

# Next Document

**FA-024 — AI Integration**
