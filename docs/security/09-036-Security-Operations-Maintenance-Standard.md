---
title: Security Operations & Maintenance Standard
document_id: 09-036
volume: 09
version: 1.0.0
status: Draft
owner: Security Operations Team
---

# Security Operations & Maintenance Standard

## Purpose

Defines the recurring security activities required to keep Ascend secure after initial implementation.

## Philosophy

Security is a continuous operating discipline. Controls must remain effective as infrastructure, dependencies, users, threats, and product capabilities change.

## Recurring Activities

Review:

- Vulnerabilities
- Dependencies
- Secrets
- Privileged access
- Security alerts
- Audit events
- Network exposure
- Configuration drift
- AI tools and permissions
- Security exceptions

## Patch Management

Security updates should be prioritized according to:

- Severity
- Exploitability
- Exposure
- Asset criticality
- Availability impact

Critical actively exploited issues require expedited handling.

## Access Reviews

Periodically review:

- Administrators
- Service identities
- API keys
- AI tools
- External integrations
- Privileged roles

Remove unnecessary access.

## Secret Maintenance

Review:

- Expired credentials
- Rotation status
- Unused secrets
- Credential exposure
- Provider changes

## Configuration Review

Check for:

- Unexpected public exposure
- Disabled security controls
- Excessive permissions
- Debug settings
- Configuration drift

## AI Security Maintenance

Review:

- Tool permissions
- Model/provider changes
- Prompt/configuration changes
- Retrieval sources
- AI memory
- Usage anomalies
- New side effects

## Security Monitoring

Review alert quality and ensure important security signals have an owner.

## Backup and Recovery

Security-relevant recovery procedures should be exercised according to system criticality.

## Documentation

Keep:

- Threat models
- Runbooks
- Security policies
- Architecture decisions
- Incident procedures

synchronized with implementation.

## Exceptions

Review open security exceptions periodically and close expired exceptions.

## Operational Changes

Security-sensitive maintenance must use controlled deployment and change-management processes.

## Anti-Patterns

Avoid:

- One-time security reviews with no maintenance
- Permanent exceptions
- Dormant privileged accounts
- Unreviewed AI tool permissions
- Ignoring security alerts because they are noisy

## AI Context

AI coding agents must preserve operational security requirements when modifying dependencies, permissions, infrastructure, integrations, or recurring jobs.

# Next Document

**09-037 — Security Cost, Capacity & Abuse Governance**
