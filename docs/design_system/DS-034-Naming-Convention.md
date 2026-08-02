---
title: Naming Convention
document_id: DS-034
version: 1.0.0
status: Draft
owner: Design System Team
---

# Naming Convention

> "Consistent names create consistent systems."

## Purpose

Defines the naming standards used across the Ascend Design System, ensuring every designer, engineer, and AI agent speaks the same language.

---

## Philosophy

Names should be:

- Descriptive
- Consistent
- Predictable
- Scalable
- Technology-agnostic where possible

Avoid abbreviations unless they are universally understood.

---

## Component Naming

Use PascalCase.

Examples:

- Button
- TextField
- CommandPalette
- NotificationCenter

---

## Design Token Naming

Use semantic dot notation.

Examples:

- color.text.primary
- spacing.section.large
- motion.duration.fast
- radius.card

---

## File & Folder Naming

Use kebab-case.

Examples:

- button.tsx
- command-palette.tsx
- design-tokens.json

---

## Variant Naming

Use clear semantic values:

- primary
- secondary
- destructive
- outlined
- filled
- disabled

---

## State Naming

Standard states:

- default
- hover
- focus
- active
- selected
- loading
- disabled
- error
- success

---

## Documentation

Every document should include:

- Title
- ID
- Version
- Dependencies
- Revision History

---

## Engineering Notes

Enforce naming conventions through linting, design review, and automated validation.

---

## AI Context

AI-generated code and documentation must follow these naming standards without exception.

---

# Next Document

**DS-035 — Figma Standards**

---

# Revision History

| Version | Date | Author | Changes |
|----------|------|--------|---------|
|1.0.0|TBD|Design System Team|Initial draft|
