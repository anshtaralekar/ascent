---
title: HTTP & Transport Standards
document_id: 08-003
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# HTTP & Transport Standards

## Purpose

Defines transport-level conventions for Ascend HTTP APIs, including methods, status codes, headers, content types, caching, and request behavior.

## Philosophy

Transport semantics should be predictable so clients can reason about API behavior without reverse-engineering individual endpoints.

## HTTP Methods

Use methods according to their intended semantics:

- GET for retrieval
- POST for actions or creation where appropriate
- PUT for full replacement where supported
- PATCH for partial modification
- DELETE for deletion semantics

Do not use method names merely because they are convenient.

## Safety and Idempotency

GET should not mutate application state.

Operations that may be retried must define whether they are naturally idempotent or require an idempotency mechanism.

## Status Codes

Use status codes consistently to communicate broad outcomes.

Examples include:

- 2xx for successful operations
- 4xx for client/request problems
- 5xx for server-side failures

The response body should provide the machine-readable application error where required.

## Content Types

Declare and validate expected content types.

Reject unsupported or malformed representations predictably.

## Request Limits

Define limits for:

- Body size
- Query length
- Header size where applicable
- Upload size
- Batch size
- Pagination parameters

Limits protect both security and infrastructure stability.

## Headers

Use standard headers for:

- Content type
- Caching
- Correlation
- Authentication
- Conditional requests where supported

Custom headers should have clear ownership and documentation.

## Caching

Only cache responses where authorization, freshness, and invalidation semantics are understood.

Never allow shared caches to mix tenant-sensitive responses.

## Conditional Requests

Use conditional retrieval mechanisms when they materially reduce unnecessary data transfer and the resource semantics support them.

## Compression

Compression should be enabled where appropriate for large textual responses, while avoiding unnecessary overhead for already compressed data.

## Timeouts

Define server-side and client-facing timeout expectations.

Long-running work should generally use asynchronous job patterns rather than holding an HTTP request indefinitely.

## Streaming

Streaming APIs must define:

- Framing
- Completion semantics
- Error behavior
- Cancellation
- Reconnection expectations

This is particularly relevant to AI generation.

## Transport Security

Production APIs must use encrypted transport.

Sensitive credentials or tokens must never be transmitted through insecure channels.

## Anti-Patterns

Avoid:

- Mutating state through GET
- Arbitrary status codes
- Unlimited request bodies
- Indefinite HTTP requests
- Shared caching of private responses
- Undocumented custom transport behavior

## AI Context

AI coding agents must follow existing transport conventions and should define timeout, streaming, cancellation, and request-size behavior for AI endpoints explicitly.

# Next Document

**08-004 — Authentication & Authorization APIs**
