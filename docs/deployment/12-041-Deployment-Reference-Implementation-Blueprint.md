# Deployment Reference Implementation Blueprint

## Purpose

Defines how the Volume 12 deployment architecture should be translated into the actual repository, CI/CD system, infrastructure, and operational tooling.

## Implementation Principle

Deployment implementation must follow the existing authoritative architecture rather than introducing parallel mechanisms.

## Repository Inspection

Before changing deployment behavior, inspect:

- Existing CI/CD workflows
- Deployment manifests
- Infrastructure-as-code
- Environment definitions
- Container configuration
- Secret references
- Database migration tooling
- Monitoring integrations
- Release conventions

## Pipeline Implementation

The implementation should make the lifecycle explicit:

```text
Validate
→ Build
→ Publish
→ Verify
→ Promote
→ Deploy
→ Verify
→ Observe
```

## Artifact Handling

Artifacts should have immutable or otherwise reliable identities and remain traceable to source.

## Environment Configuration

Environment-specific values must be separated from source code and managed through approved mechanisms.

## Deployment Strategies

Implement only strategies actually required by the architecture:

- Rolling
- Canary
- Blue/green
- Feature-flagged
- Staged promotion

Do not add unnecessary deployment complexity.

## Database

Migration execution must integrate with the authoritative Volume 07 strategy and Volume 12 compatibility rules.

## Frontend

Frontend builds must preserve cache and backend compatibility requirements.

## Workers

Worker deployments must preserve queue/message compatibility and graceful shutdown behavior.

## Infrastructure

Infrastructure deployment must follow Volume 10 IaC and security controls.

## AI

AI deployment configuration must include appropriate traceability for:

- Model
- Provider
- Prompt/configuration
- Tools
- Retrieval
- Evaluation state

## AI Coding Agent

The agent must inspect existing implementation before proposing files, pipelines, manifests, or scripts.

Reuse existing tools where compatible.

## Anti-Patterns

Avoid creating a second CI/CD system, duplicating environment configuration, or introducing a deployment framework without architectural justification.

# Next Document

**12-042 — Deployment Automation & Runbook Reference**
