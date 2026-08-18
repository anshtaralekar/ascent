---
title: Infrastructure Identity & Access Management
document_id: 10-006
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Identity & Access Management

## Purpose

Defines how infrastructure identities, permissions, service accounts, and privileged access are created and controlled.

## Principle

Infrastructure access must be attributable, least-privileged, environment-scoped, and revocable.

## Identity Categories

Distinguish between:

- Human operators
- Developers
- CI/CD identities
- Application workloads
- Background workers
- AI workers
- Monitoring systems
- External providers

Do not use one universal identity for unrelated responsibilities.

## Human Access

Human infrastructure access should use the approved organizational identity system.

Privileged access should require stronger controls appropriate to risk.

## Service Identities

Every production workload that accesses protected infrastructure should have an explicit service identity.

Each identity should have:

- Owner
- Purpose
- Scope
- Environment
- Permissions
- Lifecycle

## Least Privilege

Permissions should be granted at the narrowest useful scope.

Avoid broad permissions such as universal administrator access for ordinary workloads.

## Environment Scoping

Development identities should not automatically have production privileges.

Production access must be explicitly granted.

## CI/CD Identity

Deployment pipelines should use dedicated identities.

CI/CD identities should have only the permissions required for the deployment operation.

## AI Infrastructure Identity

AI workers must have explicit identities and limited infrastructure permissions.

An AI coding or runtime agent must not inherit unrestricted infrastructure privileges from the initiating human.

## Privilege Escalation

Temporary escalation should be:

- Explicit
- Authorized
- Time-bounded where practical
- Audited

## Credential Management

Infrastructure credentials must use approved secret-management systems.

Do not commit credentials to source control.

## Access Review

Review privileged infrastructure identities periodically.

Remove:

- Unused accounts
- Expired access
- Unnecessary permissions
- Orphaned service identities

## Auditability

Privileged infrastructure operations should be attributable to an identity and recorded through appropriate audit mechanisms.

## Break-Glass Access

Emergency access should be tightly controlled and reviewed after use.

## Federation

Where external infrastructure providers support federation, prefer centralized identity management over unmanaged long-lived credentials.

## Anti-Patterns

Avoid:

- Shared administrator accounts
- Permanent universal credentials
- Production access from ordinary developer identities
- CI pipelines with unrestricted cloud permissions
- AI workers with administrator privileges

## AI Context

AI coding agents must inspect existing IAM roles, service accounts, deployment identities, and permission boundaries before modifying infrastructure access.

# Next Document

**10-007 — Infrastructure Configuration & Secrets Management**
