---
title: Infrastructure Incident Response & Forensics
document_id: 10-032
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Incident Response & Forensics

## Purpose

Defines how infrastructure incidents are detected, contained, investigated, recovered, and documented.

## Incident Types

Infrastructure incidents may include:

- Service outage
- Security compromise
- Credential compromise
- Network exposure
- Data loss
- Deployment failure
- Supply-chain compromise
- Provider outage
- Resource exhaustion

## Response Lifecycle

```text
Detect
→ Triage
→ Contain
→ Preserve Evidence
→ Recover
→ Validate
→ Learn
```

## Triage

Determine:

- Scope
- Severity
- Affected environments
- Affected services
- Security implications
- User/business impact

## Containment

Contain the smallest effective boundary.

Possible actions include:

- Disable affected service
- Restrict network access
- Revoke credentials
- Stop deployment
- Disable compromised tool
- Isolate workload

## Evidence Preservation

Preserve relevant:

- Logs
- Audit events
- Deployment records
- Configuration history
- Infrastructure state
- Artifact metadata

Do not destroy evidence through premature cleanup.

## Security Incidents

Follow Volume 09 incident response requirements.

Infrastructure responders must coordinate with the security response process when compromise is suspected.

## Credential Compromise

Immediately consider:

- Revocation
- Rotation
- Affected consumers
- Historical access
- Persistence

## Forensics

Investigation should establish:

- Timeline
- Initial entry
- Affected resources
- Actions performed
- Persistence mechanisms
- Data exposure
- Recovery point

## Recovery

Recover from trusted artifacts and configurations.

Do not assume the compromised environment is trustworthy.

## AI-Related Incidents

If AI tooling contributed to an incident, investigate:

- Prompt/context
- Tool permissions
- Tool arguments
- Authorization decision
- Retrieved data
- Model/provider
- Human approvals
- Resulting side effects

Do not treat model text alone as the complete audit trail.

## Communication

Incident communication should identify:

- Current status
- Impact
- Actions
- Owner
- Next decision point

Avoid speculation presented as fact.

## Post-Incident Review

Record:

- Root cause
- Contributing factors
- Detection quality
- Response quality
- Recovery quality
- Preventive actions

## Anti-Patterns

Avoid:

- Cleaning systems before evidence preservation
- Restoring compromised credentials
- Treating security compromise as ordinary downtime
- Relying on AI conversation history as the only forensic evidence

## AI Context

AI coding agents must preserve infrastructure auditability and recovery paths when implementing automation or operational tooling.

# Next Document

**10-033 — Infrastructure Resilience & Fault-Tolerance Patterns**
