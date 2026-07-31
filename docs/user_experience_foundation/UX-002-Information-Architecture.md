---
title: Information Architecture
document_id: UX-002
version: 1.0.0
status: Draft
owner: UX Team

depends_on:
  - UX-001
  - PF-001

used_by:
  - Product Design
  - Engineering
  - Product Management
---

# Information Architecture

> "Users should never wonder where something belongs or where to find it."

## Purpose

This document defines how information, features, and workflows are organized within Ascend. A well-structured information architecture reduces cognitive load, improves discoverability, and creates a scalable foundation for future features.

---

# IA Philosophy

Information should be organized around the user's mental model, not the product's internal architecture.

Navigation should answer three questions instantly:

- Where am I?
- What can I do here?
- Where do I go next?

---

# Primary Product Areas

Ascend is organized into distinct but interconnected domains:

1. Dashboard
2. Tasks
3. Calendar
4. Goals
5. Habits
6. Projects
7. Notes
8. Journal
9. AI Assistant
10. Analytics
11. Settings

Each domain has a clear responsibility and should avoid unnecessary overlap.

---

# Relationships Between Features

Tasks
- Can belong to Projects
- Can contribute to Goals
- Can be scheduled on the Calendar

Goals
- Are achieved through Projects, Habits, and Tasks

Habits
- Generate long-term progress
- Feed Analytics
- Influence Goal completion

Journal
- Captures reflection
- Connects to Goals, Habits, and AI insights

AI Assistant
- Acts across every domain
- Never replaces core navigation

---

# Navigation Hierarchy

## Global Navigation

Persistent navigation between major product areas.

## Local Navigation

Navigation within a specific module.

## Contextual Navigation

Shortcuts based on the current screen or selected object.

---

# Organization Principles

- Group related information together.
- Minimize navigation depth.
- Keep frequently used actions close.
- Avoid duplicate destinations.
- Prefer recognition over recall.

---

# Scalability

New features should integrate into existing domains whenever possible.

If a feature cannot naturally fit within the current structure, the architecture should be reviewed before creating a new top-level section.

---

# Engineering Notes

Routes, deep links, permissions, and data models should align with this information architecture.

---

# AI Context

AI-generated navigation and recommendations should respect the established hierarchy and never create hidden information structures.

---

# Next Document

**UX-003 — User Journey Framework**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
| 1.0.0 | TBD | UX Team | Initial draft |
