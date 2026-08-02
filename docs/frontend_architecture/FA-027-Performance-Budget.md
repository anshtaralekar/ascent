---
title: Performance Budget
document_id: FA-027
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Performance Budget

> "Performance is a feature with measurable limits."

## Purpose

Defines measurable performance targets for every frontend feature in Ascend.

---

## Philosophy

Every feature must remain within predefined performance budgets before reaching production.

---

## Core Web Vitals

Target:

- LCP: ≤ 2.5 s
- INP: ≤ 200 ms
- CLS: ≤ 0.1

Monitor continuously.

---

## Loading Budgets

- Fast initial render
- Minimal JavaScript
- Deferred non-critical resources
- Progressive loading

---

## Bundle Budgets

Optimize:

- JavaScript bundles
- CSS bundles
- Fonts
- Images

Avoid unnecessary dependencies.

---

## Rendering

Prefer:

- Server Components
- Streaming
- Lazy loading
- Code splitting

---

## Media

- Responsive images
- Modern formats
- Lazy loading
- CDN delivery

---

## Memory

- Minimize retained objects
- Dispose listeners
- Avoid leaks
- Virtualize large lists

---

## Monitoring

Measure using:

- Lighthouse
- Web Vitals
- Real User Monitoring
- Build-time bundle analysis

---

## Regression Prevention

Every release should include:

- Performance testing
- Bundle analysis
- Lighthouse validation
- Web Vitals review

---

## Anti-Patterns

Avoid:

- Oversized bundles
- Blocking scripts
- Unbounded rendering
- Excessive hydration

---

## AI Context

AI coding agents should evaluate performance impact before introducing new dependencies or client-side logic.

---

# Next Document

**FA-028 — Lazy Loading**
