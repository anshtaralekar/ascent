---
title: Tables
document_id: DS-018
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

# Tables

> "Tables transform large amounts of information into decisions."

## Purpose

Defines the reusable table component system for analytics, reports, logs, settings, and structured datasets across Ascend.

---

# Philosophy

Tables should maximize readability, comparison, and efficient interaction without overwhelming users.

---

# Table Types

- Standard Table
- Sortable Table
- Filterable Table
- Editable Table
- Analytics Table
- Virtualized Table
- Comparison Table

---

# Anatomy

- Header Row
- Column Header
- Data Cell
- Row
- Footer
- Pagination
- Toolbar
- Bulk Actions

---

# States

- Default
- Hover
- Selected
- Focus
- Editing
- Loading
- Empty
- Error
- Disabled

---

# Interaction

Support:

- Sorting
- Filtering
- Search
- Pagination
- Infinite Scroll
- Inline Editing
- Multi-select
- Keyboard Navigation

---

# Responsive Behavior

Large tables should adapt through:

- Horizontal scrolling
- Column priority
- Responsive collapse
- Card transformation (mobile)

---

# Accessibility

Support:

- Semantic table roles
- Keyboard navigation
- Screen readers
- Visible focus
- Accessible sorting announcements

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

Implement reusable Table components with virtualization, server-side pagination, sorting, filtering, and accessibility.

---

# AI Context

AI-generated dashboards should reuse approved table components instead of creating custom data layouts.

---

# Next Document

**DS-019 — Navigation Components**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
