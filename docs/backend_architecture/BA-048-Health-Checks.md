---
title: Health Checks
document_id: BA-048
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Health Checks

> "Healthy services prove their readiness continuously."

## Purpose

Defines the health check architecture used to determine the operational status of Ascend services.

---

## Philosophy

Health checks should accurately represent whether a service can start, accept traffic, and continue operating safely.

---

## Health Check Types

- Startup probes
- Liveness probes
- Readiness probes
- Dependency checks

---

## Probe Lifecycle

1. Service starts
2. Startup validation
3. Readiness verification
4. Traffic acceptance
5. Continuous liveness monitoring
6. Graceful shutdown

---

## Dependency Checks

Verify health of:

- PostgreSQL
- Redis
- Object storage
- Queue system
- AI providers
- External APIs

Dependencies should not block startup unless essential.

---

## Aggregation

Expose a unified health endpoint summarizing component status while protecting sensitive implementation details.

---

## Reliability

Support:

- Graceful degradation
- Temporary dependency failures
- Cached health where appropriate
- Fast probe execution

---

## Monitoring

Track:

- Probe latency
- Success rate
- Failure frequency
- Restart count
- Dependency availability

---

## Security

- Restrict detailed health data
- Separate public and internal endpoints
- Authenticate privileged diagnostics
- Audit health failures

---

## Anti-Patterns

Avoid:

- Expensive health queries
- Blocking probes
- Exposing secrets
- Returning healthy during critical failures

---

## AI Context

AI coding agents should implement standardized startup, liveness, and readiness endpoints compatible with orchestration platforms.

---

# Next Document

**BA-049 — Observability**
