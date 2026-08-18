---
title: API Naming & Convention Standards
document_id: 08-037
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# API Naming & Convention Standards

## Purpose

Defines consistent naming conventions for Ascend API resources, fields, operations, errors, events, headers, and implementation components.

## Philosophy

Consistent naming reduces cognitive load and makes APIs easier for humans and AI coding agents to discover.

## Resource Names

Resource names should:

- Represent domain concepts
- Be stable
- Avoid database-specific terminology
- Follow one pluralization convention

## Endpoint Paths

Paths should use the project's established casing and resource conventions consistently.

Do not introduce a second URL style for a new feature.

## Actions

Action names should clearly describe the domain operation.

Examples:

- `approve`
- `cancel`
- `retry`
- `generate`
- `execute`

Avoid vague actions such as `process` when the actual operation can be named precisely.

## Field Names

Use one consistent field naming convention across API contracts.

Names should communicate meaning rather than storage implementation.

## Identifiers

Use consistent suffixes or terminology for:

- IDs
- References
- Keys
- Tokens
- Cursors

## Boolean Fields

Prefer positive, explicit names such as:

- `is_active`
- `has_access`
- `can_edit`

Avoid confusing double negatives.

## Timestamps

Use predictable names such as:

- `created_at`
- `updated_at`
- `deleted_at`

where these match the project's established convention.

## Error Codes

Error codes should be:

- Stable
- Machine-readable
- Domain-aware
- Documented

Do not make clients parse human-readable messages.

## Headers

Custom headers should be rare, consistently named, and documented.

## Event Names

Event names should describe facts.

For example:

**`task.completed`**

rather than an ambiguous command-like name.

## AI Tools

Tool names should describe a narrow capability and remain stable.

A tool name should not conceal broad permissions.

## Repository Naming

Implementation files, services, controllers, schemas, and tests should follow repository conventions.

## Abbreviations

Avoid unexplained abbreviations.

Use established technical abbreviations only where they are universally understood within the project.

## Governance

Existing naming conventions take precedence over personal coding preferences.

## Anti-Patterns

Avoid:

- Mixed casing styles
- Database table names exposed as APIs
- Generic action names
- Inconsistent timestamp terminology
- Multiple names for the same domain concept

## AI Context

AI coding agents must inspect nearby API implementations before naming new endpoints, fields, errors, events, or tools and should follow existing conventions.

# Next Document

**08-038 — API Configuration & Environment Standards**
