---
title: Security Identity Lifecycle & Privileged Access
document_id: 09-027
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Identity Lifecycle & Privileged Access

## Purpose

Defines how identities and privileges are created, changed, reviewed, suspended, and removed.

## Lifecycle

The identity lifecycle is:

**Provision → Authenticate → Authorize → Review → Modify → Suspend/Revoke → Remove**

## User Provisioning

Create access according to:

- Verified identity
- Tenant membership
- Required role
- Product workflow
- Least privilege

## Role Changes

Privilege changes must take effect predictably.

Removing a privilege should not depend on client-side state.

## Deprovisioning

When an identity no longer requires access, revoke access promptly.

Consider:

- Sessions
- Tokens
- API keys
- Service credentials
- External integrations
- Shared resources

## Privileged Access

Privileged operations include activities such as:

- User administration
- Security configuration
- Data export
- Credential management
- Infrastructure changes
- Billing/configuration changes
- High-impact AI tool execution

These require stronger controls appropriate to risk.

## Privilege Separation

Avoid giving one identity unrelated privileges merely for convenience.

Separate operational responsibilities where practical.

## Service Identities

Service accounts should have:

- Named owner
- Defined purpose
- Minimal permissions
- Credential lifecycle
- Monitoring

## API Keys

Keys should be scoped to the minimum capability required.

## AI Identities

AI agents and workflows should have explicit service or application identities.

A model must not inherit unrestricted permissions from the human who initiated a workflow.

## Privilege Escalation

Any privilege escalation path must be explicit, authorized, and auditable.

## Access Reviews

Review privileged access periodically and after material role changes.

## Emergency Access

Emergency access should be:

- Restricted
- Time-bounded where practical
- Audited
- Reviewed afterward

## Dormant Identities

Unused privileged identities and credentials should be identified and removed or disabled according to lifecycle policy.

## Anti-Patterns

Avoid:

- Permanent universal administrator accounts
- Shared privileged credentials
- AI agents inheriting full user permissions
- Privileges that cannot be traced to an owner

## AI Context

AI coding agents must preserve identity lifecycle controls and must never solve an authorization problem by granting broader privileges.

# Next Document

**09-028 — Security Session, Token & Credential Lifecycle**
