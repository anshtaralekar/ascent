# Container & Image Deployment Strategy

## Purpose

Defines how Ascend builds, verifies, stores, promotes, and deploys container images where containerized workloads are used.

## Principle

The deployed image must be identifiable, verified, and equivalent to the artifact that passed release validation.

## Image Construction

Images should be:

- Reproducible where practical
- Minimal
- Versioned
- Free of unnecessary tooling
- Built through approved pipelines

## Base Images

Base images should be:

- Approved
- Maintained
- Scanned
- Version-controlled

Avoid silently changing base images between validation and production.

## Dependency Integrity

Lock and verify dependencies where practical.

## Image Scanning

Validate applicable:

- OS vulnerabilities
- Package vulnerabilities
- Malware/security policy
- Secret exposure
- Configuration policy

## Registry

Use an approved registry with:

- Access control
- Auditability
- Retention
- Artifact integrity

## Promotion

Promote the verified image rather than rebuilding an equivalent image for production.

## Runtime Configuration

Environment-specific configuration and secrets should be injected through approved mechanisms.

Do not bake production secrets into images.

## Image Identity

Track:

- Repository
- Tag/version
- Immutable digest
- Source revision
- Build identity

Prefer immutable digests for production deployment where supported.

## Runtime User

Containers should avoid unnecessary root privileges.

## Health

Container deployment must integrate appropriate startup, liveness, and readiness behavior.

## AI Workloads

AI services may require special handling for:

- Model assets
- GPU/runtime dependencies
- Provider credentials
- Large artifacts
- Resource limits

Model artifacts must be versioned and traceable where they are packaged into the deployment.

## Recovery

Previously approved images should remain available for the required rollback/recovery window.

## Anti-Patterns

Avoid `latest` as the sole production identity, mutable registry tags, production secrets in images, unscanned base images, and rebuilding after validation without traceability.

# Volume 12 Progress

**12-001 through 12-015 complete.**

# Next Document

**12-016 — Serverless & Managed Runtime Deployment**
