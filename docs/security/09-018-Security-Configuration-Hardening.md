---
title: Security Configuration & Hardening
document_id: 09-018
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Configuration & Hardening

## Purpose

Defines baseline hardening principles for application, infrastructure, database, containers, cloud resources, and operational tooling.

## Philosophy

Unused capabilities are attack surface. Secure systems should expose only what they require.

## Baseline

Production environments should have documented secure defaults for:

- Network access
- Services
- Accounts
- Permissions
- Logging
- Encryption
- Runtime settings
- Containers
- Storage

## Least Functionality

Disable unnecessary:

- Ports
- Services
- Protocols
- Administrative interfaces
- Debug features
- Default accounts

## Administrative Accounts

Privileged accounts must be controlled and individually attributable where practical.

Shared administrator credentials should be avoided.

## Debugging

Debug modes, development endpoints, verbose stack traces, and test credentials must not be exposed in production.

## Containers

Containers should:

- Run with minimal privileges
- Use trusted base images
- Avoid unnecessary packages
- Avoid embedding secrets
- Use read-only filesystems where practical
- Drop unnecessary Linux capabilities where supported

## Cloud Resources

Cloud resources should use:

- Least-privilege IAM
- Private networking where appropriate
- Explicit storage policies
- Encryption
- Audit logging

## Database Hardening

Follow Volume 07 security controls.

Applications should not use unrestricted administrative database accounts.

## Storage Hardening

Object/file storage should default to private access unless public access is explicitly required.

## TLS

Use approved TLS configuration and disable obsolete insecure protocols according to supported infrastructure.

## Security Headers

Browser-facing services should apply the approved security-header policy.

## Configuration Drift

Monitor important production configuration for unexpected changes.

## Hardening vs Availability

Hardening must not be performed blindly. Changes should be tested so that security improvements do not create avoidable outages.

## AI Infrastructure

AI workers and tools must run with only the permissions and network access required for their workflows.

## Verification

Hardening should be validated through:

- Configuration scans
- Infrastructure tests
- Deployment checks
- Runtime monitoring

## Anti-Patterns

Avoid:

- Default credentials
- Public storage by default
- Privileged containers without justification
- Debug production endpoints
- Unnecessary open ports
- Universal cloud permissions

## AI Context

AI coding agents must follow established hardening baselines and must not weaken production configuration to make development or debugging easier.

# Next Document

**09-019 — Privacy & Data Security**
