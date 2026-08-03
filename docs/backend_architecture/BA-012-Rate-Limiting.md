---
title: Rate Limiting
document_id: BA-012
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Rate Limiting

> "Protect shared resources while preserving a fair experience."

## Purpose

Defines the rate limiting architecture for every Ascend API.

---

## Philosophy

Rate limiting prevents abuse, protects infrastructure, and ensures equitable access for legitimate clients.

---

## Rate Limit Categories

- User-based
- IP-based
- API key
- AI endpoints
- Authentication endpoints
- File uploads

---

## Algorithms

Support:

- Sliding Window
- Token Bucket
- Fixed Window (where appropriate)

Choose the algorithm based on endpoint characteristics.

---

## Distributed Enforcement

Use Redis-backed distributed counters to ensure consistent limits across multiple backend instances.

---

## Responses

When limits are exceeded:

- Return HTTP 429
- Include Retry-After header
- Preserve correlation ID
- Log the event

---

## AI Endpoints

Apply stricter controls for:

- Token generation
- Tool execution
- Model invocation

Prevent excessive resource consumption.

---

## Monitoring

Track:

- Requests per client
- Rejected requests
- Burst traffic
- Abuse patterns

---

## Security

Integrate with:

- DDoS protection
- Abuse detection
- Automated blocking
- Alerting

---

## Anti-Patterns

Avoid:

- Global static limits
- Silent throttling
- Inconsistent policies
- Missing Retry-After headers

---

## AI Context

AI coding agents should implement rate limiting using shared middleware and centralized Redis-backed policies.

---

# Next Document

**BA-013 — Authentication Architecture**
