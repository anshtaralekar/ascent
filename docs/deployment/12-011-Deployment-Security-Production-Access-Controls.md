# Deployment Security & Production Access Controls

## Purpose

Defines security controls governing deployment systems, production access, deployment identities, and privileged release operations.

## Principle

Production deployment is a privileged security operation.

Access must be limited, authenticated, authorized, traceable, and revocable.

## Deployment Identities

Deployment identities should be:

- Dedicated to deployment
- Least-privileged
- Environment-specific
- Auditable
- Rotatable

Do not use personal credentials as the permanent identity of automated deployment.

## Production Access

Direct production access should be minimized.

Prefer controlled automation for repeatable deployment operations.

Human access should be granted only when required for:

- Approval
- Diagnosis
- Emergency recovery
- Authorized operational tasks

## Authentication

Production deployment access must use approved strong authentication mechanisms.

## Authorization

Separate permissions for:

- Build
- Test
- Artifact publication
- Staging deployment
- Production deployment
- Rollback
- Infrastructure administration

A CI job that runs tests should not automatically receive production deployment privileges.

## Approval

High-risk changes may require explicit approval according to organizational policy.

Approval must not be inferred merely from code review.

## Secrets

Deployment credentials must be stored through approved secret-management systems.

Secrets must not appear in:

- Source code
- Build logs
- Test output
- Deployment manifests
- Chat messages
- Artifacts

## Audit

Record material production actions including:

- Identity
- Action
- Artifact
- Environment
- Time
- Result

## Emergency Access

Emergency access must be:

- Explicit
- Time-bounded where possible
- Auditable
- Revoked after use

## AI Agents

An AI coding agent must not:

- Request unnecessary production privileges
- Extract production secrets
- Circumvent approval gates
- Grant itself permissions
- Treat repository write access as production authority

## Anti-Patterns

Avoid shared production accounts, permanent administrator access, personal credentials in automation, and deployment permissions bundled into unrelated CI jobs.

# Next Document

**12-012 — Deployment Secrets & Credential Management**
