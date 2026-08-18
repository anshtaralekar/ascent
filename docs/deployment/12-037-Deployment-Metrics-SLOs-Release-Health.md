# Deployment Metrics, SLOs & Release Health

## Purpose

Defines the metrics used to determine whether deployments preserve service health and operational objectives.

## Principle

Deployment health should be measured through meaningful user and system outcomes.

## Core Signals

Monitor relevant:

- Availability
- Error rate
- Latency
- Throughput
- Saturation
- Resource usage
- Queue health
- Dependency health

## SLO Relationship

Deployment decisions should respect the service objectives established by the broader reliability architecture.

A release that technically deploys but materially threatens an SLO is not healthy.

## Error Budget

Where error budgets are used, release velocity may be constrained when reliability consumption becomes excessive.

## Release Health

Compare:

- Current release
- Previous stable release
- Defined baseline
- Required thresholds

## Business Health

Where appropriate include:

- Workflow completion
- Failed transactions
- User-visible errors
- Important product metrics

## AI Health

For AI features monitor relevant:

- Response latency
- Provider errors
- Token consumption
- Cost
- Tool-call failures
- Safety/evaluation regressions

Do not expose sensitive AI content merely to improve dashboards.

## Alerting

Alerts should have:

- Clear thresholds
- Severity
- Owner
- Action
- Escalation path

## Deployment Correlation

Metrics should be correlated with release and configuration changes.

## Observation

High-risk releases require an appropriate observation period.

## Anti-Patterns

Avoid dashboards full of vanity metrics, average-only latency, alerts with no owner, and declaring release health from infrastructure uptime alone.

# Next Document

**12-038 — Deployment Change Review & Approval Workflow**
