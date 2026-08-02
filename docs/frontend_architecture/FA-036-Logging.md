---
title: Logging
document_id: FA-036
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Logging

> "If it matters, it should be observable."

## Purpose

Defines the logging and observability standards for the Ascend frontend.

---

## Philosophy

Logs should provide actionable insight for debugging, monitoring, auditing, and performance analysis while protecting user privacy.

---

## Log Levels

- Debug
- Info
- Warning
- Error
- Critical

Use the lowest level that accurately reflects severity.

---

## Structured Logging

Every log should include:

- Timestamp
- Severity
- Component
- Session ID
- Correlation ID
- Event name

---

## Log Categories

- UI Events
- API Requests
- Performance Metrics
- Authentication Events
- AI Interactions
- Error Reports

---

## Privacy

Never log:

- Passwords
- Tokens
- Personal secrets
- Sensitive user content

Redact confidential values before transmission.

---

## Monitoring

Integrate with centralized monitoring for:

- Error tracking
- Performance dashboards
- User-impact metrics
- Availability alerts

---

## Production Policy

- Disable verbose debug logs
- Sample high-volume events
- Retain only necessary telemetry

---

## Anti-Patterns

Avoid:

- Console logging in production
- Duplicate logs
- Logging sensitive data
- Excessive verbosity

---

## AI Context

AI coding agents should use shared logging utilities and structured events instead of direct console statements.

---

# Next Document

**FA-037 — Configuration**
