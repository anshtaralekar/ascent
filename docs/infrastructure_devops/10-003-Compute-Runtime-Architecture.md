---
title: Compute & Runtime Architecture
document_id: 10-003
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Compute & Runtime Architecture

## Purpose

Defines how Ascend application workloads execute and how runtime responsibilities are separated.

## Workload Categories

Infrastructure should distinguish between:

- Web/API services
- Background workers
- Scheduled jobs
- Event consumers
- AI workers
- Build/deployment workloads
- Administrative jobs

Each workload should have a defined runtime responsibility.

## Stateless Services

Application services should be stateless where practical.

State that must survive process replacement belongs in approved external systems such as:

- Database
- Object storage
- Cache
- Queue

## Runtime Identity

Every workload requiring protected resources must have an explicit service identity.

Do not rely on a shared universal runtime identity.

## Resource Controls

Define appropriate:

- CPU limits
- Memory limits
- Process limits
- Concurrency limits
- Request limits
- Timeouts

Resource controls protect both availability and cost.

## Health Checks

Services should expose appropriate health signals.

Distinguish:

- Liveness
- Readiness
- Dependency health

A service being alive does not necessarily mean it can safely receive traffic.

## Graceful Shutdown

Services must handle shutdown predictably.

They should:

- Stop accepting new work where appropriate
- Finish safe in-flight work
- Close connections
- Persist required state
- Avoid corrupting operations

## Horizontal Scaling

Services should scale horizontally when their architecture permits.

Scaling should not create:

- Duplicate scheduled jobs
- Race conditions
- Uncontrolled external calls
- Data-integrity issues

## Background Workers

Workers should use controlled queues and idempotent processing where retries can occur.

## Scheduled Jobs

Scheduled operations must define behavior when:

- A job is delayed
- A job overlaps
- A worker crashes
- A job is retried

## AI Workers

AI workers require additional controls for:

- Token usage
- Tool-call limits
- Execution time
- Concurrency
- Provider failures
- Side effects

## Runtime Configuration

Runtime configuration must be externalized and validated at startup.

Invalid security-critical configuration should prevent unsafe startup rather than silently using insecure defaults.

## Failure Isolation

One workload failure should not automatically cascade into unrelated services.

## Process Boundaries

Use separate workloads where different:

- Permissions
- Scaling characteristics
- Reliability requirements
- Security boundaries

justify separation.

## Observability

Runtime should expose:

- Logs
- Metrics
- Traces where applicable
- Health state
- Resource usage

## Anti-Patterns

Avoid:

- Unbounded memory usage
- Unlimited worker concurrency
- Shared credentials across unrelated workloads
- Stateful application processes without explicit design
- Running privileged workloads unnecessarily

## AI Context

AI coding agents must define the runtime characteristics of a new service or worker before implementing deployment configuration.

# Next Document

**10-004 — Containerization & Image Standards**
