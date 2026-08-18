---
title: Infrastructure Compliance & Policy-as-Code
document_id: 10-022
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Compliance & Policy-as-Code

## Purpose

Defines how infrastructure policies are encoded, validated, and continuously enforced.

## Principle

Important infrastructure rules should be machine-checkable wherever practical.

## Policy Domains

Policies may govern:

- Public exposure
- IAM permissions
- Encryption
- Network configuration
- Resource tagging
- Container privileges
- Storage access
- Backup configuration
- Region restrictions
- Secret handling

## Preventive Controls

Where practical, invalid infrastructure should be rejected before deployment.

## Detective Controls

Existing infrastructure should also be scanned periodically for drift or policy violations.

## Policy Severity

Policies should distinguish:

- Blocking violations
- High-risk warnings
- Advisory findings

Critical security violations should block deployment where appropriate.

## Exceptions

Policy exceptions must follow Volume 09 exception handling.

Each exception should have:

- Owner
- Reason
- Scope
- Compensating control
- Expiration/review date

## Infrastructure Scanning

Scan:

- IaC
- Cloud configuration
- Containers
- Dependencies
- Runtime settings

## Policy Versioning

Policy changes must be version-controlled and reviewable.

## Testing Policies

Policy definitions should have tests proving:

- Valid configurations pass
- Invalid configurations fail
- Exceptions behave as intended

## False Positives

Policies should be tuned to reduce noise without weakening the underlying security requirement.

## Drift Detection

Detect when deployed infrastructure no longer matches approved policy.

## Compliance Evidence

Where required, retain evidence of:

- Policy evaluation
- Deployment checks
- Exceptions
- Remediation

## AI-Generated Infrastructure

AI-generated IaC must pass the same policy gates as human-generated infrastructure.

AI authorship is not an exemption.

## Anti-Patterns

Avoid:

- Manual compliance checklists as the only control
- Unversioned policy logic
- Permanent wildcard exceptions
- Disabling scanners because they are inconvenient

## AI Context

AI coding agents should run or reference applicable policy checks before declaring infrastructure changes complete.

# Next Document

**10-023 — Infrastructure Supply-Chain Security**
