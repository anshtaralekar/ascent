---
title: Resource & Endpoint Design
document_id: 08-007
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# Resource & Endpoint Design

## Purpose

Defines how Ascend API resources and endpoints should be structured so that APIs remain coherent as the product grows.

## Philosophy

Endpoints should represent meaningful product capabilities and domain resources rather than exposing database structure.

## Resource Boundaries

A resource should have:

- Clear ownership
- Defined identity
- Lifecycle
- Authorization rules
- Stable representation

## Endpoint Design

Endpoint names should be:

- Predictable
- Consistent
- Domain-oriented
- Free of unnecessary implementation terminology

## CRUD Operations

Use conventional resource operations where they accurately represent the domain.

Do not force every domain workflow into CRUD.

## Actions

Explicit action endpoints may be appropriate for domain operations that are not naturally resource updates.

Examples include:

- Submit
- Approve
- Cancel
- Retry
- Generate
- Execute

Actions must still have explicit authorization, validation, idempotency, and error semantics.

## Nested Resources

Use nesting when the relationship is intrinsic and improves clarity.

Avoid deeply nested paths that create unnecessary coupling.

## Identifiers

Use stable identifiers appropriate to the resource.

Do not expose internal identifiers merely because they are convenient if a safer domain identifier exists.

## Filtering

Filtering parameters must be:

- Explicit
- Validated
- Bounded
- Authorized

Do not permit arbitrary database query expressions through public APIs.

## Sorting

Supported sort fields should be allowlisted.

Clients should not be able to select arbitrary internal columns.

## Bulk Operations

Bulk APIs must define:

- Maximum batch size
- Atomicity
- Partial failure behavior
- Idempotency
- Rate limits

## AI Resources

AI resources such as conversations, runs, tools, memories, and generated artifacts should have explicit lifecycle and authorization semantics.

## Long-Running Operations

Use job resources or asynchronous operation patterns when processing may exceed normal request timeouts.

## Governance

New resources should be reviewed for domain ownership, authorization, lifecycle, and compatibility.

## Anti-Patterns

Avoid:

- CRUD-only modeling of complex workflows
- Database table names as API resources
- Arbitrary query languages exposed publicly
- Unlimited bulk requests
- Deeply nested endpoint structures

## AI Context

AI coding agents must identify the domain resource before creating an endpoint and should prefer established endpoint patterns over inventing new conventions.

# Next Document

**08-008 — Pagination, Filtering & Sorting**
