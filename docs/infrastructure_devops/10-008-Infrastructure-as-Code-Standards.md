---
title: Infrastructure as Code Standards
document_id: 10-008
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure as Code Standards

## Purpose

Defines how infrastructure is represented, reviewed, tested, and deployed as code.

## Principle

Production infrastructure should be reproducible from version-controlled definitions.

## Source of Truth

Each infrastructure domain must have one clearly identified authoritative definition.

Avoid manual changes that are not subsequently reconciled into source control.

## Modularity

Infrastructure modules should represent meaningful reusable boundaries.

Do not create abstractions solely to reduce line count.

## Environments

Use environment-specific configuration over duplicated infrastructure definitions where practical.

## Variables

Variables should have:

- Clear names
- Validated types
- Safe defaults where appropriate
- Explicit required values

Do not use insecure defaults for production.

## Secrets

IaC should reference approved secret systems rather than containing secret values.

## State

Infrastructure state must be:

- Protected
- Access-controlled
- Backed up where appropriate
- Consistent with the deployment system

Sensitive state must receive appropriate protection.

## Plans and Changes

Material changes should be reviewed before application.

Where the tooling supports it, generate a plan/diff that makes the intended infrastructure change visible.

## Drift

Detect and resolve infrastructure drift.

Manual emergency changes must be reconciled back into the canonical definition.

## Testing

IaC should receive appropriate:

- Syntax validation
- Static analysis
- Policy checks
- Security scanning
- Plan validation
- Integration testing

## Dependency Management

Infrastructure modules and providers must be versioned and evaluated for security and compatibility.

## Destructive Operations

Destructive infrastructure operations require explicit safeguards.

Examples:

- Production database deletion
- Network teardown
- Storage destruction
- Identity removal

## Rollback

Infrastructure changes should have a defined rollback or forward-recovery strategy.

## AI-Generated IaC

AI-generated infrastructure code must be reviewed for:

- Privilege
- Public exposure
- Network access
- Data loss
- Cost
- Resource limits
- Provider behavior
- Security configuration

## Anti-Patterns

Avoid:

- Manual-only infrastructure
- Hidden production changes
- Hard-coded credentials
- Unreviewed destructive operations
- Copy-pasted environment configurations with divergent behavior

## AI Context

AI coding agents should inspect existing IaC conventions and modules before creating new infrastructure definitions.

# Next Document

**10-009 — CI/CD Pipeline Architecture**
