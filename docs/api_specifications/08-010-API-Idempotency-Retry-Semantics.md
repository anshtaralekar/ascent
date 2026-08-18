---
title: API Idempotency & Retry Semantics
document_id: 08-010
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# API Idempotency & Retry Semantics

## Purpose

Defines how Ascend APIs behave when requests are repeated because of client retries, network ambiguity, worker retries, timeouts, or distributed-system failures.

## Philosophy

A request can be delivered more than once even when a client intended it only once. APIs must make duplicate execution safe where the operation requires it.

## Idempotent Operations

Naturally idempotent operations should preserve their result when repeated under equivalent conditions.

Examples commonly include safe reads and deliberate full replacements.

## Non-Idempotent Operations

Operations that create resources or trigger side effects may require an explicit idempotency mechanism.

Examples:

- Payment-like actions
- Job creation
- External notifications
- AI tool actions
- Resource provisioning

## Idempotency Keys

Where required, clients should provide an idempotency key according to the API contract.

The server should associate the key with:

- Operation scope
- Authenticated identity
- Request semantics
- Result
- Expiration/lifecycle

A key must not allow one identity to retrieve another identity's result.

## Duplicate Requests

The API must define behavior for:

- Same key and same request
- Same key and conflicting request
- Key reuse after expiration
- Concurrent duplicate requests

## Transactions

Idempotency should coordinate with database transactions and persistent operation records where necessary.

## External Side Effects

When an API performs an external action, use durable state or an equivalent pattern to prevent ambiguous retries from duplicating the side effect.

## Retryable Failures

Not every failure is safe to retry.

Classify failures based on:

- Whether the operation committed
- Whether the side effect occurred
- Whether the request can be safely repeated

## Timeouts

A timeout does not prove that the operation failed.

Clients and servers must account for the possibility that the operation completed but its response was lost.

## Background Jobs

Job submission APIs should define whether duplicate submissions produce:

- One job
- Multiple jobs
- A deduplicated result

## AI Operations

AI workflows may retry due to:

- Provider timeouts
- Tool failures
- Worker restarts
- Network interruptions

Persist enough workflow state to distinguish retries from genuinely new operations.

## Observability

Log safe operation identifiers and idempotency outcomes without logging secrets or sensitive payloads.

## Anti-Patterns

Avoid:

- Retrying every POST automatically
- Using random client-side deduplication without server support
- Assuming timeout means failure
- Repeating external side effects without idempotency
- Sharing idempotency keys across unrelated scopes

## AI Context

AI coding agents must explicitly determine retry and idempotency behavior for every state-changing endpoint and must not introduce automatic retries that can duplicate side effects.

# Volume 08 Progress

**08-001 through 08-010 complete.**

# Next Document

**08-011 — Asynchronous APIs & Job Operations**
