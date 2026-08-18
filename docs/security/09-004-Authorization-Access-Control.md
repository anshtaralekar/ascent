---
title: Authorization & Access Control
document_id: 09-004
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Authorization & Access Control

## Purpose

Defines how the system determines whether an authenticated identity is permitted to perform a specific action on a specific resource.

## Philosophy

Authorization is a server-side security decision.

Possessing:

- A valid account
- A valid token
- A resource ID
- A client-provided role

does not automatically grant access.

## Authorization Model

The decision should consider:

```text
Actor
  +
Action
  +
Resource
  +
Tenant / Context
  +
Policy
  =
Authorization Decision
```

## Access Control Models

The project may use:

- RBAC
- ABAC
- Resource ownership
- Policy-based access
- Capability-based access

The chosen model must match the product domain and remain consistent.

## RBAC

Roles should represent meaningful permission groups.

Avoid creating roles for every individual endpoint when a capability-based permission model is more appropriate.

## Resource Authorization

Authorization must be evaluated against the actual resource.

Example:

A user being authenticated does not imply access to `/users/{id}` for every user.

## Tenant Isolation

Every tenant-scoped operation must verify that the actor is authorized within that tenant.

Tenant IDs supplied by clients must never be treated as authoritative without verification.

## Privileged Operations

Sensitive actions should require explicit permissions.

Examples:

- User management
- Billing/configuration
- Data export
- Deletion
- Security settings
- AI tools with external side effects

## Deny by Default

If authorization cannot establish permission, deny the operation.

Failing closed is preferred for security-sensitive decisions.

## Delegation

Delegated access must define:

- Who delegated
- What was delegated
- Scope
- Duration
- Revocation

## Service Authorization

Services should receive only the permissions required for their workflows.

## AI Authorization

AI models cannot grant themselves permissions.

Tool execution must independently verify:

- Actor
- Workflow
- Tenant
- Resource
- Action
- Required permission

## Authorization Context

Do not rely solely on client-provided:

- User ID
- Role
- Tenant ID
- Permission list
- Ownership flag

## Auditing

Material authorization decisions and privileged actions should be auditable according to the audit architecture.

## Performance

Authorization checks should be designed efficiently without weakening correctness.

Caching authorization decisions requires careful invalidation and scope controls.

## Anti-Patterns

Never:

- Enforce authorization only in the frontend.
- Assume authenticated means authorized.
- Trust role fields from clients.
- Allow AI-generated permissions.
- Skip resource-level authorization.

## AI Context

AI coding agents must explicitly identify the authorization boundary for every protected capability and must test both allowed and denied access paths.

# Next Document

**09-005 — Secrets & Credential Management**
