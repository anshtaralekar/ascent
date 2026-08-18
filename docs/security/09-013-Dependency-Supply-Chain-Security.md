---
title: Dependency & Supply-Chain Security
document_id: 09-013
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Dependency & Supply-Chain Security

## Purpose

Defines how third-party packages, services, models, tools, build artifacts, and other external components are evaluated and controlled.

## Philosophy

Every dependency expands the system's trust and attack surface.

Use dependencies deliberately rather than treating package installation as free infrastructure.

## Dependency Inventory

Maintain visibility into important:

- Runtime packages
- Build dependencies
- Container images
- SDKs
- Cloud services
- AI providers
- Agent frameworks
- Models
- Plugins
- External tools

## Selection

Evaluate dependencies for:

- Security history
- Maintenance activity
- Provenance
- License
- Privileges
- Transitive dependencies
- Operational importance

## Versioning

Prefer reproducible dependency versions.

Do not allow uncontrolled floating versions in production builds.

## Vulnerability Monitoring

Monitor dependencies for known vulnerabilities using approved security tooling.

## Critical Vulnerabilities

Critical vulnerabilities require prompt assessment and remediation or explicit risk treatment.

## Transitive Dependencies

Security review must account for important transitive dependencies, not only direct packages.

## Lockfiles

Production builds should use committed dependency lock information where supported.

## Package Sources

Use trusted package registries and verify package provenance/integrity where practical.

## Build Artifacts

Container images and build artifacts should originate from controlled pipelines.

## CI/CD Security

Build systems must:

- Protect credentials
- Restrict permissions
- Avoid executing untrusted build instructions with privileged access
- Produce traceable artifacts

## AI Supply Chain

Assess:

- Model providers
- Model artifacts
- Embedding models
- Agent frameworks
- Tool packages
- Prompt/tooling dependencies

AI components can introduce both software and data supply-chain risk.

## Dependency Removal

Unused dependencies should be removed to reduce attack surface and maintenance cost.

## Incident Response

If a dependency is compromised:

1. Identify affected versions.
2. Determine exposure.
3. Isolate or remove the component.
4. Rotate affected credentials if required.
5. Rebuild trusted artifacts.
6. Validate the environment.

## Anti-Patterns

Avoid:

- Unreviewed packages
- Unpinned production dependencies
- Unknown package sources
- Ignoring transitive vulnerabilities
- Giving third-party packages unnecessary privileges

## AI Context

AI coding agents must not add dependencies merely for convenience when existing project capabilities can satisfy the requirement.

# Next Document

**09-014 — Security Testing & Verification**
