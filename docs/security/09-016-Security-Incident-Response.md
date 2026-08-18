---
title: Security Incident Response
document_id: 09-016
volume: 09
version: 1.0.0
status: Draft
owner: Security Operations Team
---

# Security Incident Response

## Purpose

Defines how security incidents are detected, contained, investigated, recovered, and converted into preventive improvements.

## Philosophy

Incident response must be prepared before an incident occurs. The goal is to limit harm, preserve evidence, restore trusted operation, and learn from the failure.

## Incident Lifecycle

```text
Detect
  ↓
Triage
  ↓
Contain
  ↓
Investigate
  ↓
Eradicate
  ↓
Recover
  ↓
Validate
  ↓
Review
```

## Incident Classification

Classify incidents by:

- Confidentiality impact
- Integrity impact
- Availability impact
- Security scope
- Number of affected tenants/users
- Credential exposure
- Regulatory significance where applicable

## Initial Triage

Determine:

1. What happened?
2. When did it begin?
3. What systems are affected?
4. Is the incident still active?
5. What data or credentials may be exposed?
6. What immediate containment is available?

## Containment

Possible actions include:

- Disable affected credentials
- Revoke sessions
- Disable compromised tools
- Isolate services
- Block malicious traffic
- Disable vulnerable functionality
- Restrict affected accounts

Containment should minimize unnecessary collateral impact.

## Evidence

Preserve relevant:

- Logs
- Audit events
- Configuration state
- Deployment information
- Request identifiers
- Security telemetry

Do not modify evidence unnecessarily during investigation.

## Credential Compromise

If credentials are suspected to be exposed:

1. Revoke or rotate them.
2. Identify dependent systems.
3. Review access history.
4. Replace credentials through approved mechanisms.
5. Validate consumers.

## AI Incidents

AI-specific incidents may involve:

- Prompt injection
- Unauthorized tool execution
- Data leakage
- Retrieval poisoning
- Excessive agency
- Compromised provider/tool

Contain the affected capability rather than disabling unrelated systems by default.

## Recovery

Recovery must restore a trusted state, not merely restore availability.

Validate:

- Authentication
- Authorization
- Data integrity
- Tenant isolation
- Credentials
- Dependencies
- Monitoring

## Communication

Incident communication should be factual, controlled, and appropriate to the incident's scope and obligations.

## Post-Incident Review

Review:

- Root cause
- Contributing factors
- Detection
- Response
- Recovery
- Missed controls
- Preventive actions

## Anti-Patterns

Avoid:

- Deleting evidence
- Blindly restarting systems without investigation
- Rotating one credential while leaving related credentials exposed
- Treating recovery as complete because the service is online

## AI Context

AI coding agents must not weaken incident-response controls to restore functionality quickly. Security containment takes precedence over convenience.

# Next Document

**09-017 — Vulnerability Management**
