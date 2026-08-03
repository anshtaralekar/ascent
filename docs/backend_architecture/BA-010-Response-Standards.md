---
title: Response Standards
document_id: BA-010
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Response Standards

> "Every response should be predictable, self-describing, and consistent."

## Purpose

Defines the standard response format for every Ascend backend API.

---

## Philosophy

All APIs should return a unified response structure regardless of the underlying service.

---

## Success Response

Include:

- Status
- Data
- Metadata
- Timestamp
- Correlation ID

Return only relevant fields.

---

## Error Response

Include:

- Error code
- Message
- Details
- Correlation ID
- Timestamp

Never expose internal implementation details.

---

## Collections

Collection responses should support:

- Pagination
- Total count
- Page information
- Links where applicable

---

## File Responses

Provide:

- Correct MIME type
- Cache headers
- Content length
- Safe filenames

---

## AI Responses

Support:

- Streaming
- Partial results
- Tool execution metadata
- Completion status

---

## Status Codes

Use appropriate HTTP status codes.

Avoid returning HTTP 200 for failures.

---

## Consistency

Every service should:

- Share response schemas
- Reuse DTOs
- Preserve backward compatibility

---

## Anti-Patterns

Avoid:

- Inconsistent payloads
- Missing metadata
- Leaking stack traces
- Service-specific response formats

---

## AI Context

AI coding agents should generate endpoints using the standardized response envelope and shared response models.

---

# Next Document

**BA-011 — Error Responses**
