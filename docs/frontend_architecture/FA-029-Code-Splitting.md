---
title: Code Splitting
document_id: FA-029
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Code Splitting

> "Ship only the code needed for the current experience."

## Purpose

Defines the code splitting strategy for Ascend.

---

## Philosophy

Split code by routes, features, and user interactions to minimize initial downloads while maximizing cache efficiency.

---

## Splitting Strategy

- Route-level bundles
- Feature bundles
- Dynamic imports
- Vendor chunk isolation
- Shared runtime chunks

---

## Dynamic Imports

Use dynamic imports for:

- Heavy editors
- Charts
- AI providers
- Analytics
- Rarely used dialogs

---

## Vendor Dependencies

Isolate large third-party libraries into stable cacheable chunks.

Review new dependencies for bundle impact.

---

## Tree Shaking

Ensure unused exports are removed.

Prefer ESM-compatible packages.

---

## Performance

- Reduce initial bundle size
- Maximize cache reuse
- Avoid duplicate modules
- Analyze bundles continuously

---

## Monitoring

Validate with:

- Bundle Analyzer
- Lighthouse
- Web Vitals
- Build reports

---

## Anti-Patterns

Avoid:

- Monolithic bundles
- Duplicate dependencies
- Over-fragmentation
- Unused imports

---

## AI Context

AI coding agents should prefer dynamic imports for large, non-critical features and avoid increasing the initial bundle unnecessarily.

---

# Next Document

**FA-030 — Image Optimization**
