---
title: Error Responses
document_id: BA-011
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Error Responses

> "Errors should be consistent, actionable, and secure."

## Purpose

Defines the standardized error response model for every Ascend backend service.

---

## Philosophy

Every error should communicate what happened, why it happened, and how the client can recover, without exposing internal implementation details.

---

## Error Categories

- Validation Errors
- Authentication Errors
- Authorization Errors
- Business Rule Errors
- Resource Errors
- Database Errors
- AI Provider Errors
- External Service Errors
- Rate Limit Errors
- Internal Server Errors

---

## Standard Error Schema

Every error response should include:

- Error Code
- Human-readable Message
- Optional Details
- Correlation ID
- Timestamp

---

## HTTP Status Mapping

Use appropriate HTTP status codes.

Examples include:

- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 409 Conflict
- 422 Unprocessable Entity
- 429 Too Many Requests
- 500 Internal Server Error

---

## Security

Never expose:

- Stack traces
- SQL queries
- Internal identifiers
- Secrets

---

## Recovery

Errors should indicate when:

- Retry is appropriate
- Authentication is required
- User action is required
- Support intervention is required

---

## Logging

Every error should be logged with:

- Correlation ID
- Severity
- Service
- Context

Sensitive information must be redacted.

---

## Anti-Patterns

Avoid:

- Generic error messages
- HTTP 200 for failures
- Leaking implementation details
- Inconsistent error formats

---

## AI Context

AI coding agents should return standardized error responses using shared error models and preserve consistent error semantics across all services.

---

# Next Document

**BA-012 — Rate Limiting**
