---
title: Data Access Performance & Connection Management
document_id: 07-029
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Access Performance & Connection Management

## Purpose

Defines application-level database access practices for efficient connection use, predictable query execution, and controlled concurrency.

## Philosophy

A correctly designed database can still fail when application services misuse connections, create excessive queries, or allow uncontrolled concurrency.

## Connection Pooling

Use bounded connection pools.

Configure and monitor:

- Minimum connections
- Maximum connections
- Acquisition timeout
- Idle timeout
- Connection lifetime
- Health checks

Pool sizing must consider total application replicas, workers, and background processes.

## Connection Budget

The total potential database connections across the deployment must remain within database capacity.

Scaling application replicas without adjusting connection budgets can cause connection exhaustion.

## Request Lifecycle

Database connections should be:

1. Acquired
2. Used for the smallest required period
3. Released promptly

Never hold connections while waiting for unrelated network calls.

## Query Boundaries

Avoid:

- Unbounded result sets
- Repeated identical queries
- Queries inside large loops
- Unnecessary column retrieval
- Long-running transactions

## Batch Operations

Use batching for:

- Bulk inserts
- Updates
- Deletes
- Backfills

Batch size should balance throughput, lock duration, memory use, and recovery time.

## Concurrency

Bound concurrent database work.

Use backpressure when the database becomes saturated rather than allowing application concurrency to amplify the failure.

## Read/Write Routing

If replicas exist, route only workloads that can tolerate their consistency behavior.

Critical read-after-write operations should use an appropriate authoritative path.

## Caching

Cache repeated expensive reads when correctness permits.

Cache decisions must follow Volume 07 persistence and invalidation rules.

## Observability

Measure:

- Pool utilization
- Connection wait time
- Query latency
- Query frequency
- Batch throughput
- Database saturation

## Failure Handling

Handle:

- Connection timeout
- Pool exhaustion
- Database restart
- Transient network failures
- Deadlocks

Retries must be bounded and safe for the operation.

## AI Workloads

AI agents can create bursty database workloads through:

- Parallel tool calls
- Retrieval fan-out
- Batch evaluation
- Background indexing

These workflows require explicit concurrency limits.

## Governance

Performance-sensitive data-access changes should include realistic workload tests and connection-capacity analysis.

## Anti-Patterns

Avoid:

- One connection per request without pooling
- Unlimited connection pools
- Holding connections across external calls
- Unbounded parallel queries
- Blind retries on writes

## AI Context

AI coding agents must account for connection capacity and concurrency when implementing repositories, workers, retrieval pipelines, and agent workflows.

# Next Document

**07-030 — Data Quality & Reconciliation**
