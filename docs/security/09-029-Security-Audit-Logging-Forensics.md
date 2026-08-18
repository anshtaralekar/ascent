---
title: Security Audit, Logging & Forensics
document_id: 09-029
volume: 09
version: 1.0.0
status: Draft
owner: Security Operations Team
---

# Security Audit, Logging & Forensics

## Purpose

Defines the audit and forensic evidence required to investigate security-sensitive activity without turning telemetry into an uncontrolled copy of application data.

## Audit Principle

Security audit records should answer:

**Who did what, to which resource, when, from which context, and what happened?**

## Security Events

Important events may include:

- Authentication
- Failed authentication
- Authorization denial
- Privilege change
- Credential creation/revocation
- Administrative action
- Data export
- Sensitive deletion
- Security configuration change
- AI tool execution

## Event Fields

Where appropriate, audit records should include:

- Timestamp
- Actor/service identity
- Action
- Resource
- Tenant/context
- Result
- Correlation/request ID
- Relevant source metadata

Do not collect unnecessary sensitive payloads.

## Audit Integrity

Security audit records should be protected against unauthorized modification or deletion.

## Access

Audit data must itself be access-controlled because it may contain sensitive operational information.

## Retention

Retention should be defined according to:

- Security investigation value
- Privacy requirements
- Operational needs
- Storage cost
- Applicable obligations

## Application Logs vs Audit Logs

Application logs support diagnosis.

Audit logs establish security-relevant accountability.

Do not assume ordinary application logs are sufficient for privileged actions.

## Sensitive Data

Do not place credentials, full secrets, or unnecessary sensitive content into audit events.

Use references or metadata where possible.

## Correlation

Correlate events across:

- Request
- Session
- User
- Service
- Tenant
- Workflow
- Resource

## Forensic Readiness

The architecture should preserve enough evidence to investigate material incidents.

Important evidence may include:

- Authentication events
- Authorization decisions
- Configuration changes
- Deployment history
- Credential events
- Network/security telemetry

## AI Forensics

AI workflows should make important actions traceable to:

- Initiating actor
- AI workflow
- Tool
- Resource
- Authorization decision
- Result

Do not treat model text alone as an audit trail.

## Tamper Resistance

Security logs should be stored and transported using mechanisms that reduce unauthorized alteration.

## Incident Investigation

During an incident:

1. Preserve relevant evidence.
2. Establish timeline.
3. Identify affected identities/resources.
4. Determine access and actions.
5. Contain the incident.
6. Record findings.

## Anti-Patterns

Avoid:

- Logging secrets
- Relying only on free-form text
- Deleting audit records during incidents
- Giving application users unrestricted access to security logs
- Treating AI conversation history as the only evidence of an action

## AI Context

AI coding agents must add structured security telemetry for material privileged workflows and must avoid logging raw sensitive context.

# Next Document

**09-030 — Security Resilience & Recovery Architecture**
