---
title: Lists
document_id: DS-017
version: 1.0.0
status: Draft
owner: Design System Team

depends_on:
  - DS-002
  - DS-009
  - DS-010

used_by:
  - Product Design
  - Frontend Engineering
  - QA
  - Figma Library
---

# Lists

> "Lists are the backbone of productivity. They should make scanning, prioritizing, and acting effortless."

## Purpose

Defines the reusable List component system used across Ascend for tasks, habits, projects, notes, notifications, search results, and analytics.

---

# Philosophy

Lists should optimize for rapid scanning, low cognitive load, and efficient interaction.

---

# List Types

- Simple List
- Grouped List
- Hierarchical List
- Checklist
- Virtualized List
- Timeline List
- Search Results
- Notification List

---

# Anatomy

- Container
- List Item
- Leading Icon / Avatar
- Primary Text
- Secondary Text
- Metadata
- Status Indicator
- Actions
- Divider (optional)

---

# States

- Default
- Hover
- Focus
- Selected
- Expanded
- Collapsed
- Loading
- Empty
- Error
- Disabled

---

# Interaction

Support:

- Click / Tap
- Keyboard Navigation
- Drag & Drop
- Swipe Actions
- Multi-select
- Context Menu

---

# Grouping

Lists may be grouped by:

- Date
- Priority
- Project
- Goal
- Tag
- Status

Section headers should remain visually distinct.

---

# Accessibility

Lists must support:

- Semantic list roles
- Keyboard navigation
- Screen readers
- Visible focus
- Accessible drag-and-drop alternatives

---

# Tokens

Uses:

- Color
- Typography
- Spacing
- Radius
- Motion
- Elevation

---

# Engineering Notes

Implement reusable List and ListItem components supporting virtualization, grouping, selection, and drag-and-drop.

---

# AI Context

AI-generated interfaces should compose standard list patterns instead of creating custom collection layouts.

---

# Next Document

**DS-018 — Tables**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
