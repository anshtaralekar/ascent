---
title: Security Monitoring & Detection
document_id: 09-015
volume: 09
version: 1.0.0
status: Draft
owner: Security Operations & Architecture Team
---

# Security Monitoring & Detection

## Purpose

Defines the telemetry, detection, alerting, and investigation capabilities required to identify security-relevant activity.

## Philosophy

Prevention is necessary but insufficient. The system must also make important security events visible.

## Security Signals

Monitor appropriate signals including:

- Authentication failures
- Authorization failures
- Privilege changes
- Credential events
- Unusual data access
- Large exports
- Rate-limit abuse
- Suspicious network activity
- File security events
- Administrative actions
- AI tool execution

## Logging

Security logs should be:

- Structured
- Timestamped
- Correlatable
- Access-controlled
- Protected from unauthorized modification

## Audit Events

Record important security-sensitive actions such as:

- Role changes
- Permission changes
- Account recovery
- Credential rotation
- Administrative configuration
- Data export
- Deletion of sensitive resources
- High-impact AI tool actions

## Correlation

Security events should be correlatable across:

- User
- Service
- Request
- Session
- Tenant
- Workflow
- Resource

Do not collect more identity information than necessary.

## Detection

Detection rules should identify patterns such as:

- Repeated authentication failure
- Impossible or anomalous access patterns
- Sudden privilege changes
- Unusual exports
- Repeated authorization failures
- Unexpected service identities
- AI tool abuse
- Credential anomalies

## Alerting

Alerts should be:

- Actionable
- Prioritized
- Routed to the appropriate owner
- Resistant to unnecessary noise

## AI Monitoring

AI-specific signals may include:

- Tool-call spikes
- Repeated denied tool calls
- Unexpected tool combinations
- Retrieval anomalies
- Excessive token consumption
- Prompt-injection indicators
- High-impact actions

## Privacy

Security monitoring must follow data-minimization principles.

Security telemetry must not become an uncontrolled copy of application data.

## Retention

Retention must balance:

- Investigation requirements
- Security value
- Privacy
- Storage cost
- Applicable obligations

## Incident Integration

Detection systems should feed the incident-response process.

## Testing Detection

Security detection rules should be tested to ensure important events actually produce expected signals.

## Anti-Patterns

Avoid:

- Logging everything without classification
- Alerting without ownership
- Ignoring authorization failures
- Recording sensitive content unnecessarily
- Treating monitoring as a replacement for prevention

## AI Context

AI coding agents must add appropriate security telemetry when introducing privileged workflows, authentication changes, sensitive data access, external integrations, or AI tools.

# Volume 09 Progress

**09-001 through 09-015 complete.**

# Next Document

**09-016 — Security Incident Response**
