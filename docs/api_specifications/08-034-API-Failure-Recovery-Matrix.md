---
title: API Failure & Recovery Matrix
document_id: 08-034
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# API Failure & Recovery Matrix

## Purpose

Defines expected API failure classes and the appropriate response, containment, recovery, and validation approach.

## Failure Matrix

| Failure | Detection | Primary Response | Recovery Validation |
|---|---|---|---|
| Invalid request | Validation metrics | Return client-safe error | Contract behavior verified |
| Authentication outage | Auth dependency health | Fail safely / degrade where possible | Authentication restored |
| Database outage | Dependency telemetry | Fail/queue according to workflow | Data access restored |
| Database timeout | Latency/error metrics | Bounded retry where safe | Latency normal |
| External provider outage | Provider telemetry | Retry/queue/degrade | Provider recovered |
| Queue outage | Queue metrics | Reject/queue safely | Jobs processing |
| Webhook delivery failure | Delivery metrics | Retry/backoff | Consumer receiving |
| Rate-limit saturation | Limit metrics | Throttle | Capacity normalized |
| AI provider failure | AI telemetry | Retry/fallback/queue | Workflow recovery |
| Cache failure | Cache telemetry | Bypass/fallback | Cache healthy |
| Search outage | Search telemetry | Fallback or degrade | Search restored |

## Failure Classification

Assess:

- User impact
- Data impact
- Security impact
- Duration
- Recoverability
- Scope

## Retry Rule

Retries must be:

- Bounded
- Backed off
- Idempotency-aware
- Limited to transient failures

## Degradation

Disable optional functionality before allowing failures to cascade into core services.

## Async Recovery

For jobs, preserve durable state and make processing retry-safe.

## Data Recovery

Follow Volume 07 database recovery procedures.

## Security Recovery

If credentials or authorization systems are compromised:

- Revoke/rotate access
- Contain affected workflows
- Preserve evidence
- Validate authorization after recovery

## AI Recovery

AI workflows should distinguish:

- Provider failure
- Tool failure
- Retrieval failure
- Partial generation
- Persistent side-effect completion

Do not blindly rerun a workflow whose side effects may already have occurred.

## Post-Recovery

Validate:

- Error rates
- Latency
- Dependency health
- Queue state
- Data consistency
- Tenant isolation

## Incident Review

Material failures should produce a documented review and preventive actions.

## Anti-Patterns

Avoid:

- Infinite retries
- Treating every timeout as failure
- Returning raw dependency errors
- Recovery without validation
- Replaying side effects blindly

## AI Context

AI coding agents must define the failure path at the same time as the success path for new API functionality.

# Next Document

**08-035 — API AI Coding-Agent Rules**
