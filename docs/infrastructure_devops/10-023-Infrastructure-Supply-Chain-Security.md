---
title: Infrastructure Supply-Chain Security
document_id: 10-023
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Supply-Chain Security

## Purpose

Defines controls protecting the infrastructure and software supply chain from compromised dependencies, build systems, registries, providers, and artifacts.

## Supply-Chain Scope

Consider:

- Source repositories
- Dependencies
- Package registries
- Container base images
- IaC providers
- CI/CD systems
- Build runners
- Artifact registries
- Deployment tools
- AI/model providers

## Dependency Trust

Dependencies should be:

- Identifiable
- Versioned
- Maintained
- Scanned
- Obtained from approved sources

## Locking

Application and infrastructure dependencies should use deterministic versioning where practical.

Avoid unconstrained dependency ranges in production-critical paths.

## Build Isolation

Build environments should receive only the credentials and network access required for the build.

Untrusted source code must not automatically gain production privileges.

## Build Reproducibility

Builds should produce artifacts traceable to source and dependency state.

## Provenance

Maintain sufficient provenance to establish how an artifact was produced.

## Artifact Integrity

Verify artifact integrity before promotion and deployment.

## Registry Security

Restrict who can:

- Publish
- Delete
- Promote
- Modify metadata

## CI/CD Security

CI/CD is a high-value target.

Protect:

- Pipeline configuration
- Runner identities
- Secrets
- Build artifacts
- Deployment permissions

## Third-Party Actions and Plugins

External CI actions, plugins, modules, and scripts should be evaluated before adoption.

Prefer pinned versions or immutable references where supported.

## AI Supply Chain

AI-specific dependencies include:

- Model weights
- Model packages
- Prompt/configuration packages
- Tool integrations
- Retrieval components

Track provenance and integrity for any artifact that can influence production behavior.

## Compromise Response

If a dependency or build component is suspected to be compromised:

1. Stop promotion.
2. Identify affected artifacts.
3. Quarantine versions.
4. Assess exposure.
5. Rebuild from trusted inputs.
6. Rotate credentials where necessary.
7. Validate deployments.

## Monitoring

Watch for:

- Unexpected dependency changes
- Suspicious build activity
- Registry anomalies
- Unknown artifacts
- Unusual credential use

## Anti-Patterns

Avoid:

- Unpinned production dependencies
- Untrusted base images
- CI runners with unrestricted production credentials
- Unknown artifact sources
- Unverified model artifacts

## AI Context

AI coding agents must not introduce dependencies, actions, providers, or infrastructure modules solely because they appear convenient. Provenance and trust must be considered.

# Next Document

**10-024 — Infrastructure Cost & FinOps Architecture**
