---
title: Database Capacity Planning
document_id: 07-034
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Capacity Planning

## Purpose

Defines how Ascend estimates and manages database capacity across storage, compute, connections, I/O, and workload growth.

## Philosophy

Capacity planning should connect product behavior to infrastructure requirements instead of relying on arbitrary server sizing.

## Workload Model

Estimate:

- Active users
- Requests per second
- Read/write ratio
- Queries per request
- Background jobs
- AI retrieval volume
- Batch workloads
- Data growth rate

## Storage Capacity

Track:

- Row growth
- Index growth
- Historical data
- Audit data
- AI artifacts
- Backup requirements

Include headroom for operational growth and maintenance.

## Compute Capacity

Evaluate:

- CPU utilization
- Memory pressure
- Query concurrency
- Transaction volume
- I/O demand

Use measured production behavior when available.

## Connection Capacity

Calculate aggregate connection demand across:

- API replicas
- Workers
- Scheduled jobs
- Admin tools
- Migration processes

Connection limits must account for peak concurrency rather than average traffic alone.

## AI Workload Bursts

AI workloads may produce sudden increases through:

- Parallel retrieval
- Evaluation jobs
- Re-indexing
- Agent tool execution
- Batch processing

These workloads require explicit rate and concurrency controls.

## Growth Forecasting

Forecast using:

- Historical trends
- Product growth assumptions
- Feature launches
- Retention policies
- Expected AI data growth

Review assumptions periodically.

## Capacity Thresholds

Define thresholds for:

- Storage
- CPU
- Memory
- Connections
- I/O
- Replication lag
- Query latency

Thresholds should trigger a documented response.

## Scaling Options

Evaluate in order where appropriate:

1. Query optimization
2. Index optimization
3. Connection/concurrency control
4. Caching
5. Vertical scaling
6. Read scaling
7. Partitioning
8. Specialized storage
9. Sharding

Do not skip directly to distributed complexity without evidence.

## Cost

Capacity decisions must consider:

- Infrastructure cost
- Storage cost
- Backup cost
- Replication cost
- Operational complexity
- Engineering cost

## Load Testing

Use representative workloads to validate capacity assumptions before major launches.

## Governance

Capacity assumptions should be documented for critical systems and reviewed after major architectural changes.

## Anti-Patterns

Avoid:

- Planning from average load only
- Ignoring background workloads
- Ignoring AI-generated bursts
- Scaling without measuring bottlenecks
- Treating storage growth as free

## AI Context

AI coding agents should consider query volume, connection usage, storage growth, and concurrency whenever adding data-heavy features or AI pipelines.

# Next Document

**07-035 — Database AI Coding-Agent Rules**
