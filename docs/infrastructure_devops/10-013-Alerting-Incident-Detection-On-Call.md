---
title: Alerting, Incident Detection & On-Call
document_id: 10-013
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Alerting, Incident Detection & On-Call

## Purpose

Defines how infrastructure detects operational failures and routes actionable incidents to responsible responders.

## Philosophy

An alert is a request for human or automated action, not a notification of interesting data.

## Alert Classes

Distinguish where appropriate:

- Critical outage
- Major degradation
- Security incident
- Capacity risk
- Dependency failure
- Deployment failure
- Warning/early signal

## Alert Quality

Every production alert should answer:

1. What is wrong?
2. How severe is it?
3. Which service is affected?
4. What is the likely impact?
5. What should the responder do next?

## Ownership

Every important alert must have an owner or escalation path.

## Severity

Severity should reflect user/system impact, not merely metric magnitude.

## Routing

Route alerts based on service, environment, severity, and operational ownership.

## Deduplication

Avoid multiple alerts representing the same underlying incident.

## Escalation

Critical incidents require escalation if not acknowledged or resolved within the defined response window.

## On-Call

On-call responsibilities include:

- Alert response
- Initial diagnosis
- Containment
- Escalation
- Recovery
- Incident documentation

## Runbooks

Important alerts should link to actionable runbooks containing symptoms, checks, safe actions, escalation, recovery, and validation.

## Deployment Correlation

Deployment metadata should be available during incident investigation.

## Security Incidents

Security-related alerts must integrate with Volume 09 incident response.

## AI Incidents

Alert on relevant AI anomalies such as:

- Sudden token spikes
- Tool-call explosions
- Provider failures
- Unexpected model changes
- Repeated denied privileged operations
- Retrieval anomalies

## Alert Fatigue

Repeated non-actionable alerts must be tuned or removed.

## Synthetic Monitoring

For critical user journeys, use controlled synthetic checks where practical.

## Incident Timeline

Operational systems should make it possible to reconstruct detection time, deployment changes, configuration changes, failures, and recovery actions.

## Anti-Patterns

Avoid:

- Alerts without owners
- Alerts requiring a dashboard hunt to understand
- Paging for non-actionable warnings
- No runbook for critical alerts
- Ignoring alert fatigue

## AI Context

AI coding agents must not create noisy alerts merely to demonstrate observability. New alerts should correspond to meaningful operational action.

# Next Document

**10-014 — Reliability, Availability & SLO Architecture**
