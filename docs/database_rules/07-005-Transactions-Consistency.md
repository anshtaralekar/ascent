---
title: Transactions & Data Consistency
document_id: 07-005
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Transactions & Data Consistency

> "Consistency is a contract about what the system is allowed to believe."

## Purpose

Defines transaction boundaries, consistency guarantees, concurrency controls, and failure-handling rules for Ascend's persistent data.

## Philosophy

Transactions should be as small and explicit as possible while guaranteeing the invariants required by the domain.

## Transaction Boundary

A transaction should group operations that must succeed or fail together to preserve a defined business invariant.

Do not extend database transactions across long-running external operations unless the architecture explicitly supports such coordination.

## ACID Properties

Where relational transactions are used, preserve:

- Atomicity
- Consistency
- Isolation
- Durability

The required isolation level should be selected according to actual concurrency requirements.

## Consistency Models

Distinguish between:

- Strong transactional consistency
- Eventual consistency
- Read-after-write expectations
- Derived-data consistency

Each asynchronous workflow must document when derived state is expected to become consistent.

## Concurrency

Protect against:

- Lost updates
- Duplicate writes
- Race conditions
- Double processing
- Inconsistent state transitions

Use appropriate mechanisms such as:

- Row-level locking
- Optimistic concurrency
- Unique constraints
- Version fields
- Idempotency keys

## Isolation

Choose isolation levels deliberately based on:

- Read/write contention
- Data correctness requirements
- Transaction duration
- Performance impact

Do not use the strongest isolation level by default without workload justification.

## Idempotency

Operations that may be retried should define whether they are idempotent.

For externally triggered commands, use idempotency keys or equivalent mechanisms when duplicate execution would be harmful.

## Distributed Operations

When a workflow spans a database and external systems, prefer explicit coordination patterns such as:

- Transactional outbox
- Idempotent consumers
- Retry-safe commands
- Compensation

Avoid assuming that a single database transaction can atomically control unrelated external systems.

## Failure Handling

Handle:

- Transaction rollback
- Deadlocks
- Serialization failures
- Connection loss
- Partial external failures
- Retry exhaustion

Retries must be bounded and safe.

## State Transitions

Critical state changes should be protected by database constraints and appropriate transaction boundaries.

## Auditability

For important mutations, preserve enough information to reconstruct:

- What changed
- When it changed
- Which actor or service initiated it
- Relevant request or operation identity

## Monitoring

Track:

- Transaction latency
- Rollbacks
- Deadlocks
- Lock contention
- Serialization failures
- Retry rates
- Consistency incidents

## Governance

Consistency decisions should be documented for critical workflows involving:

- Identity
- Permissions
- Billing
- User state
- AI memory
- Job execution
- External side effects

## Anti-Patterns

Avoid:

- Long-running database transactions
- Retrying non-idempotent writes blindly
- Assuming eventual consistency is immediate
- Distributed operations without failure strategy
- Using application checks where database constraints are required

## AI Context

AI coding agents must explicitly define transaction boundaries and consistency guarantees for state-changing workflows, especially when retries, asynchronous jobs, agents, or external tools are involved.

# Next Document

**07-006 — Data Integrity & Constraints**
