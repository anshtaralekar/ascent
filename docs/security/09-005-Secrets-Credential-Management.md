---
title: Secrets & Credential Management
document_id: 09-005
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Secrets & Credential Management

## Purpose

Defines how passwords, API keys, tokens, certificates, signing keys, and other sensitive credentials are created, stored, accessed, rotated, revoked, and audited.

## Philosophy

A secret is a security boundary. Application code must consume secrets without becoming the long-term storage location for those secrets.

## Secret Classes

Examples include:

- Database credentials
- API keys
- OAuth client secrets
- Signing keys
- Encryption keys
- Webhook secrets
- Cloud credentials
- AI provider credentials
- Service-to-service credentials

## Storage

Secrets must use the approved secret-management system.

Never commit secrets to:

- Source code
- Git history
- Container images
- Frontend bundles
- Documentation
- Test fixtures containing real credentials

## Access

Secret access must follow least privilege.

Applications should receive only the secrets required for their runtime responsibilities.

## Environment Separation

Development, testing, staging, and production credentials must be isolated.

Production secrets must not be copied into local environments unless explicitly required and controlled.

## Rotation

Secrets should support planned rotation.

Rotation procedures must define:

- New credential creation
- Consumer update
- Validation
- Old credential retirement
- Failure recovery

## Revocation

Compromised credentials must be revocable.

Revocation should be tested for critical credentials.

## Exposure Prevention

Do not expose secrets through:

- Logs
- Error messages
- API responses
- Metrics
- Traces
- Client-side code
- Source-control metadata

## CI/CD

Deployment systems should use scoped credentials and short-lived authentication where practical.

Build pipelines must not print secret values.

## External Providers

Provider credentials should be isolated in integration layers and should never be embedded in domain logic.

## AI Providers

AI provider credentials are application secrets.

A model, prompt, tool, or user must never be allowed to reveal provider credentials.

## Encryption Keys

Encryption keys require stronger lifecycle controls than ordinary configuration values.

Key management must define:

- Ownership
- Rotation
- Access
- Backup/recovery
- Revocation

## Incident Response

If a secret is suspected to be compromised:

1. Contain exposure.
2. Revoke or rotate the credential.
3. Identify affected systems.
4. Review access logs.
5. Assess impact.
6. Restore trusted credentials.
7. Document the incident.

## Development

Use safe test credentials or mocks.

Never use real production credentials to make local development convenient.

## Anti-Patterns

Never:

- Hard-code secrets.
- Commit `.env` files containing real secrets.
- Share universal credentials across services.
- Put credentials into JWT payloads unnecessarily.
- Log authentication headers.
- Give AI agents direct access to secret stores without explicit authorization.

## AI Context

AI coding agents must reuse the approved secret-management architecture and must never invent a plaintext credential store or place secrets into generated source code.

# Next Document

**09-006 — Encryption & Data Protection**
