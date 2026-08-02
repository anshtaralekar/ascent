---
title: Monorepo Structure
document_id: FA-003
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Monorepo Structure

> "One repository. Many applications. Shared standards."

## Purpose

Defines the monorepo architecture used to organize all frontend applications, shared packages, and tooling within Ascend.

---

## Philosophy

A monorepo enables code sharing, consistent tooling, unified versioning, and faster development while maintaining clear boundaries.

---

## Tooling

- Turborepo
- pnpm Workspaces

---

## Repository Layout

```text
apps/
packages/
configs/
docs/
scripts/
```

### apps/

- web
- admin
- docs
- storybook

### packages/

- ui
- design-tokens
- api-client
- types
- hooks
- utils
- config

---

## Rules

- Shared code belongs in packages.
- Applications consume packages.
- No duplicated business logic.
- No circular dependencies.

---

## Import Strategy

- Prefer package imports.
- Avoid deep relative paths.
- Use path aliases consistently.

---

## Build Strategy

Support:

- Incremental builds
- Task caching
- Parallel execution
- Independent package publishing

---

## CI Integration

Validate:

- Lint
- Typecheck
- Test
- Build
- Storybook

before merge.

---

## AI Context

AI coding agents should place new code in the appropriate workspace and avoid creating duplicate utilities across applications.

---

# Next Document

**FA-004 — Project Structure**
