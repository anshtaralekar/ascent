---
title: Project Structure
document_id: FA-004
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Project Structure

> "A predictable project structure is a productivity feature."

## Purpose

Defines the standard folder structure for every frontend application in Ascend.

---

## Philosophy

Projects should be organized by feature and responsibility, making navigation intuitive for both engineers and AI coding agents.

---

## Standard Structure

```text
app/
components/
features/
hooks/
lib/
services/
stores/
styles/
types/
utils/
assets/
public/
```

### app/

Contains App Router pages, layouts, route groups, loading, error, and metadata files.

### components/

Reusable UI components shared across multiple features.

### features/

Feature-specific components, hooks, services, and state kept together.

### hooks/

Reusable custom React hooks.

### lib/

Framework integrations and third-party configuration.

### services/

API communication and client-side service wrappers.

### stores/

Global state stores.

### types/

Shared TypeScript types and interfaces.

### utils/

Framework-independent helper functions.

### styles/

Global styles and theme configuration.

---

## Rules

- Co-locate feature files.
- Keep shared code separate.
- Prefer absolute imports.
- Avoid circular dependencies.
- Keep folders shallow where possible.

---

## AI Context

AI coding agents must place new files according to this structure and avoid creating duplicate directories.

---

# Next Document

**FA-005 — Module Organization**
