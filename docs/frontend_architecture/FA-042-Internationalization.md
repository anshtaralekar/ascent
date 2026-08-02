---
title: Internationalization
document_id: FA-042
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Internationalization

> "Build once. Speak every language."

## Purpose

Defines the internationalization (i18n) and localization (l10n) architecture for Ascend.

---

## Philosophy

Language, region, and cultural conventions should be configurable without changing application logic.

---

## Supported Features

- Multiple languages
- Locale-aware routing
- Dynamic translations
- RTL support
- Time zone awareness
- Regional formatting

---

## Translation Strategy

Store all user-facing text in translation resources.

Never hardcode display strings inside components.

---

## Locale Management

Support:

- Automatic language detection
- Manual language selection
- Fallback locales
- Persistent language preference

---

## Formatting

Use locale-aware formatting for:

- Dates
- Time
- Numbers
- Currency
- Relative time

---

## RTL Support

Provide complete support for right-to-left layouts when required.

Components must avoid direction-specific assumptions.

---

## Performance

- Lazy load translation bundles
- Cache active locale
- Load only required namespaces

---

## Accessibility

Localized content must preserve semantic meaning and accessibility labels across all supported languages.

---

## Anti-Patterns

Avoid:

- Hardcoded strings
- Locale-specific business logic
- Partial translations
- Manual formatting

---

## AI Context

AI coding agents should retrieve all user-visible strings from shared localization resources and avoid embedding language directly in components.

---

# Next Document

**FA-043 — Deployment Build**
