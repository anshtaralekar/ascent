---
title: Continuous Evaluation
document_id: AI-038
volume: 06
version: 1.0.0
status: Draft
owner: AI Architecture Team
---

# Continuous Evaluation

> "An AI system is never finished being evaluated."

## Purpose

Defines the continuous evaluation framework for detecting regressions, drift, failures, and quality changes throughout the AI lifecycle.

## Philosophy

Evaluation must continue after deployment and remain connected to telemetry, feedback, testing, and release management.

## Evaluation Loop

1. Observe production
2. Collect representative data
3. Detect anomalies
4. Evaluate behavior
5. Compare baselines
6. Identify root causes
7. Apply improvements
8. Re-evaluate

## Evaluation Sources

Use:

- Automated benchmarks
- Production telemetry
- User feedback
- Human review
- Incident analysis
- Regression datasets

## Drift Detection

Monitor:

- Quality drift
- Data drift
- Model behavior changes
- Prompt performance
- Retrieval quality
- Tool reliability

## Release Integration

Require evaluation before:

- Model changes
- Prompt changes
- Tool changes
- Knowledge updates
- Agent behavior changes

## Alerting

Trigger investigation when:

- Quality falls below threshold
- Safety failures increase
- Latency exceeds target
- Cost rises unexpectedly
- Regression patterns appear

## Monitoring

Track:

- Evaluation trends
- Baseline changes
- Regression frequency
- Time to detection
- Time to remediation

## Governance

Require:

- Continuous benchmarks
- Versioned baselines
- Auditability
- Incident linkage
- Defined ownership

## Anti-Patterns

Avoid:

- Evaluating only before launch
- Ignoring production feedback
- Changing baselines without review
- Alerting without remediation ownership

## AI Context

AI coding agents should connect production behavior to continuous evaluation and prevent unmeasured behavioral changes from silently reaching users.

# Next Document

**AI-039 — Safety Architecture**
