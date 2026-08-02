---
title: Image Optimization
document_id: FA-030
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Image Optimization

> "Every image should earn every byte it downloads."

## Purpose

Defines standards for delivering performant, responsive, and accessible images throughout Ascend.

---

## Philosophy

Serve the smallest, highest-quality image appropriate for the user's device and context.

---

## Standards

- Use `next/image` by default
- Prefer AVIF, then WebP
- Responsive `srcset`
- Lazy load non-critical images
- CDN-backed delivery

---

## Image Categories

- Hero images
- UI illustrations
- Icons
- User uploads
- AI-generated media
- Avatars

Each category follows appropriate sizing and caching rules.

---

## Loading Strategy

Load immediately:

- Above-the-fold media
- Brand assets

Lazy load:

- Gallery items
- Dashboard thumbnails
- User-generated content

---

## Accessibility

Every meaningful image must include descriptive alt text.

Decorative images should use empty alt attributes.

---

## Performance

- Compress assets
- Cache aggressively
- Prevent layout shift
- Use placeholders
- Resize server-side

---

## Anti-Patterns

Avoid:

- Full-resolution uploads
- PNG when modern formats suffice
- Missing dimensions
- Blocking hero rendering

---

## AI Context

AI coding agents should use shared image components and optimization defaults instead of raw `<img>` tags.

---

# Next Document

**FA-031 — Caching**
