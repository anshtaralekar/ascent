# Infrastructure Deployment & Change Management

## Purpose

Defines how infrastructure changes are planned, validated, deployed, and recovered.

## Authority

Volume 10 defines infrastructure and DevOps architecture. This document defines its production deployment process.

## Principle

Infrastructure changes are production changes even when application code is untouched.

## Infrastructure as Code

Where IaC is established, production infrastructure should be managed through version-controlled definitions.

Avoid undocumented manual configuration.

## Change Types

Examples include:

- Compute
- Networking
- Storage
- IAM
- Databases
- Containers
- Kubernetes resources
- DNS
- Certificates
- Monitoring
- CI/CD infrastructure

## Validation

Before production application:

- Validate syntax
- Validate policy
- Review impact
- Run applicable tests
- Inspect planned changes
- Verify dependencies

## Plan and Apply

Where supported, separate:

```text
Plan
→ Review
→ Approve
→ Apply
→ Verify
```

## Blast Radius

High-impact infrastructure changes should use progressive rollout or staged execution where practical.

## Dependencies

Consider dependencies between:

- Application
- Network
- Database
- Identity
- Storage
- External providers

## IAM Changes

IAM modifications require particular scrutiny because incorrect permissions can either break deployments or create security exposure.

## State

Infrastructure state must be protected, backed up where appropriate, and accessible only to authorized systems.

## Drift

Detect and investigate configuration drift between declared and actual infrastructure.

## Recovery

Infrastructure recovery must be defined before high-risk changes.

## AI Agents

An AI agent may generate or analyze IaC, but must not apply high-risk production infrastructure changes without the required authorization.

It must not guess resource identifiers or production configuration.

## Evidence

Record:

- Change
- Source revision
- Plan
- Approver where required
- Environment
- Result
- Recovery action if used

## Anti-Patterns

Avoid direct undocumented console changes, unreviewed IAM changes, unprotected state, and applying generated infrastructure blindly.

# Next Document

**12-015 — Container & Image Deployment Strategy**
