# Volume 12 → Volume 13 Deployment Handoff

## Purpose

Transfers the authoritative deployment rules of Volume 12 into Volume 13, where they become implementation instructions for the AI coding agent.

## Handoff Status

**Volume 12: 44 / 45 complete before this handoff document.**

## Authority

Volume 12 is authoritative for deployment and production rollout behavior.

Volume 13 must coordinate with, but must not silently override:

- Volume 07: Database
- Volume 08: API
- Volume 09: Security
- Volume 10: Infrastructure & DevOps
- Volume 11: Testing & QA

## Mandatory Deployment Invariants

The AI agent must preserve:

1. Artifact traceability
2. Environment separation
3. Least-privilege production access
4. Secure secret management
5. Controlled promotion
6. Health/readiness verification
7. Progressive rollout where appropriate
8. Recovery capability
9. Deployment observability
10. Auditability
11. Database compatibility
12. Dependency compatibility
13. Cost/resource limits
14. Release validation
15. Operational ownership

## AI Deployment Invariants

The agent must also preserve:

- Model/configuration provenance
- AI evaluation evidence
- Tool authorization
- Provider credential isolation
- Token/cost limits
- Safe rollback or fallback
- AI-specific monitoring

## Forbidden Actions

The AI agent must not:

- Deploy to production without authorized workflow
- Grant itself production permissions
- Expose secrets
- Disable security gates
- Modify audit evidence
- Fabricate approvals
- Fabricate test or deployment results
- Guess production configuration
- Bypass migration compatibility
- Rebuild approved artifacts without traceability

## Decision Rule

Before changing deployment architecture:

1. Inspect existing deployment implementation.
2. Identify the authoritative requirement.
3. Determine the smallest compatible change.
4. Validate the change.
5. Preserve artifact and audit traceability.
6. Verify recovery behavior where relevant.

## Final Principle

> **Deployment automation is a controlled system, not an unrestricted execution environment for the coding agent.**

# Next Document

**12-045 — Volume 12 Final Architecture & AI Build Contract**
