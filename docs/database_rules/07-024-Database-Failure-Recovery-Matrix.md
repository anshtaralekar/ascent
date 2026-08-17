---
title: Database Failure & Recovery Matrix
document_id: 07-024
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Failure & Recovery Matrix

## Purpose

Defines expected database failure classes and the corresponding detection, containment, recovery, and validation strategies.

## Failure Matrix

| Failure | Detection | Primary Response | Recovery Validation |
|---|---|---|---|
| Connection exhaustion | Connection metrics | Throttle/fail fast | Stable connection pool |
| Slow queries | Query telemetry | Investigate/limit workload | Latency baseline restored |
| Deadlocks | DB errors/metrics | Retry safe operations | No persistent transaction errors |
| Replication lag | Replica metrics | Route critical reads appropriately | Lag within target |
| Failed migration | Deployment telemetry | Stop/forward-fix/restore | Schema compatibility verified |
| Data corruption | Integrity checks | Isolate affected data | Reconciliation complete |
| Accidental deletion | Audit/reconciliation | Restore/reconstruct | Expected records verified |
| Provider outage | Availability monitoring | Failover/degrade | Service restored |
| Backup failure | Backup monitoring | Retry/escalate | Successful restore evidence |
| Vector index failure | Retrieval monitoring | Rebuild from source | Retrieval quality validated |

## Failure Classification

Assess:

- Scope
- Duration
- Data impact
- User impact
- Security impact
- Recoverability

## Containment

Possible controls include:

- Rate limiting
- Feature disablement
- Read-only mode
- Traffic shifting
- Replica isolation
- Provider failover
- Job pausing

## Recovery

Recovery should prioritize:

1. Protect data
2. Stop propagation
3. Restore authoritative state
4. Validate integrity
5. Rebuild derived stores
6. Restore normal traffic
7. Monitor

## Derived Data

Derived stores should generally be rebuilt from authoritative data rather than restored blindly when reconstruction is safer.

## AI Workflows

For AI-related failures, determine whether the problem affects:

- Source data
- Retrieval
- Memory
- Embeddings
- Model behavior
- Tool execution
- Generated persistent state

## Post-Recovery

Validate:

- Data integrity
- Authorization
- Tenant isolation
- Application compatibility
- Query performance
- AI retrieval correctness

## Governance

Critical databases must have documented recovery owners and tested procedures.

## Anti-Patterns

Avoid:

- Recovery without integrity validation
- Treating replicas as guaranteed backups
- Rebuilding derived data without checking source versions
- Restarting failed workloads without controlling retries

## AI Context

AI coding agents should design failure behavior alongside database features rather than treating recovery as an operations task to be added later.

# Next Document

**07-025 — AI Build Instructions for Database Layer**
