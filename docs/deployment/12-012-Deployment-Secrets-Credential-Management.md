# Deployment Secrets & Credential Management

## Purpose

Defines how credentials, keys, tokens, certificates, and other sensitive deployment configuration are provisioned and used.

## Principle

Secrets are dependencies with lifecycle, ownership, rotation, and access requirements.

## Secret Storage

Use approved secret-management infrastructure.

Never commit secrets to source control.

## Secret Categories

Examples include:

- Database credentials
- Cloud credentials
- API keys
- OAuth secrets
- Signing keys
- TLS certificates
- Registry credentials
- AI provider credentials

## Environment Separation

Production secrets must be distinct from development and test secrets.

A test environment must never accidentally inherit production credentials.

## Injection

Secrets should be injected at runtime or through approved deployment mechanisms rather than embedded into application artifacts.

## Least Privilege

Each credential should have only the permissions required for its purpose.

## Rotation

Define rotation procedures for material credentials.

Rotation should avoid unnecessary service interruption.

## Expiration

Credentials and certificates with expiry dates require monitoring before expiration.

## Exposure Prevention

Prevent secrets from appearing in:

- Logs
- Exceptions
- Screenshots
- CI artifacts
- Container layers
- Client bundles
- Metrics labels

## AI Providers

AI provider credentials must remain server-side and must never be exposed to untrusted clients or model output.

## Compromise

If a credential is suspected to be compromised:

1. Restrict or revoke it.
2. Rotate it.
3. Assess affected systems.
4. Review relevant logs.
5. Restore service using the new credential.
6. Follow applicable security incident procedures.

## Local Development

Developers and AI agents should use local/test credentials with minimal privileges.

## AI Agent Rule

An AI agent must never fabricate, reveal, or persist a secret merely to make a deployment succeed.

If a secret is unavailable, it must report the missing dependency.

## Anti-Patterns

Avoid secrets in `.env` files committed to source control, shared credentials, long-lived administrator tokens, secrets baked into images, and logging credential-bearing configuration.

# Next Document

**12-013 — Database Migration Deployment Strategy**
