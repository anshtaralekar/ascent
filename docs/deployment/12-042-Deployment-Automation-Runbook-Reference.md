# Deployment Automation & Runbook Reference

## Purpose

Defines the expected operational interface between automated deployment workflows and human runbooks.

## Principle

Automation handles deterministic repeatable work. Runbooks explain decisions, exceptions, diagnosis, and recovery.

## Automated Operations

Automate where practical:

- Validation
- Artifact creation
- Artifact publication
- Environment deployment
- Health checks
- Smoke tests
- Evidence collection
- Rollout progression
- Safe recovery triggers

## Human Operations

Human intervention may be required for:

- High-risk approvals
- Ambiguous failures
- Security incidents
- Irreversible migrations
- Exceptional recovery
- Business decisions

## Runbook Structure

A deployment runbook should contain:

1. Preconditions
2. Inputs
3. Procedure
4. Verification
5. Failure handling
6. Recovery
7. Escalation

## Automation Safety

Automated actions require:

- Bounded retries
- Explicit permissions
- Clear failure states
- Auditability
- Idempotency where possible

## Production Commands

Commands capable of modifying production must be clearly scoped and must not depend on undocumented local state.

## AI Assistance

AI may explain a failed workflow and suggest the relevant runbook section.

It must not fabricate command output or claim an operation was executed when it was only proposed.

## Recovery

Runbooks must identify whether recovery means rollback, roll-forward, traffic reversal, feature disablement, or another approved mechanism.

## Evidence

Automated workflows should expose useful evidence for operators without exposing secrets or unnecessary sensitive data.

## Maintenance

Runbooks must be updated when deployment architecture changes materially.

## Anti-Patterns

Avoid runbooks that merely repeat commands without decision logic, automation with hidden side effects, and AI-generated procedures that have not been verified against the repository.

# Next Document

**12-043 — Deployment Readiness & Operational Acceptance**
