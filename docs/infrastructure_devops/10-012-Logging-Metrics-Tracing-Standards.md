---
title: Logging, Metrics & Distributed Tracing Standards
document_id: 10-012
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Logging, Metrics & Distributed Tracing Standards

## Purpose

Defines implementation standards for telemetry emitted by Ascend workloads.

## Structured Logging

Prefer structured records over free-form strings.

Useful fields may include:

- Timestamp
- Level
- Service
- Environment
- Request/correlation ID
- Operation
- Result
- Duration

Do not expose sensitive values merely for debugging.

## Log Levels

Use levels consistently:

- DEBUG
- INFO
- WARN
- ERROR

Production DEBUG logging should be controlled and temporary.

## Error Logging

Errors should contain enough context for diagnosis without exposing passwords, tokens, API keys, private keys, or sensitive payloads.

## Correlation IDs

Requests crossing service boundaries should preserve a correlation identifier where appropriate.

Correlation IDs must not become authorization credentials.

## Metrics

Metrics should represent measurable operational behavior such as request count, error count, latency, queue depth, worker duration, resource utilization, cache behavior, and external provider failures.

## Metric Cardinality

Avoid unbounded metric labels.

Do not use arbitrary user IDs, request IDs, or raw URLs as metric labels unless there is a controlled bounded domain.

## Distributed Tracing

Tracing may be used for workflows spanning multiple services.

Trace data must respect the same privacy and security boundaries as other telemetry.

## Sampling

Trace sampling should balance diagnostic value with cost and storage.

## AI Telemetry

AI telemetry may include:

- Model/provider
- Request duration
- Token counts
- Tool-call count
- Outcome
- Error class
- Cost estimate

Avoid storing raw prompts or sensitive retrieved content by default.

## External Providers

Record enough provider metadata to diagnose timeout, rate limit, authentication failure, provider outage, and invalid response conditions.

## Access Control

Telemetry systems require access control because operational data may reveal sensitive architecture or user activity.

## Privacy

Prefer redaction, masking, tokenization, or references instead of sensitive payloads.

## Performance

Telemetry should not materially degrade application performance.

## Failure Behavior

Telemetry failure should not normally take down the primary application unless the telemetry is itself a mandatory security or compliance control with an explicit fail-closed requirement.

## Anti-Patterns

Avoid:

- Logging entire request bodies
- High-cardinality metrics
- Unbounded trace storage
- Secrets in telemetry
- Using trace IDs as authorization
- Logging AI context indiscriminately

## AI Context

AI coding agents must follow these telemetry rules whenever generating logging, metrics, tracing, or monitoring code.

# Next Document

**10-013 — Alerting, Incident Detection & On-Call**
