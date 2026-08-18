# Deployment Automation & AI Agent Operating Rules

## Purpose

Defines how AI coding agents and automated systems may interact with Ascend's deployment lifecycle.

## Principle

Automation may accelerate deployment work, but it must not become an uncontrolled production authority.

## Allowed AI Assistance

An AI agent may:

- Inspect repository deployment configuration
- Explain pipeline failures
- Generate deployment manifests
- Validate configuration
- Prepare release notes
- Summarize test evidence
- Propose rollout strategies
- Generate rollback plans
- Identify dependency risks

## Restricted Actions

An AI agent must not independently:

- Grant itself production permissions
- Extract secrets
- Disable security gates
- Modify audit records
- Fabricate approvals
- Claim tests passed when they did not
- Promote code to production without explicit authorized workflow
- Change production infrastructure without required authorization

## Repository Inspection

Before changing deployment configuration, the agent must inspect:

- Existing pipeline
- Deployment manifests
- Environment conventions
- Infrastructure definitions
- Secret references
- Testing gates
- Release conventions

## Change Principle

Prefer minimal changes that preserve established architecture.

Do not introduce a new deployment framework merely because it is familiar to the agent.

## Evidence

The agent must distinguish:

- Verified fact
- Tool output
- Inference
- Recommendation
- Missing information

## Secrets

If deployment requires a missing secret, the agent must report the dependency.

It must never invent credentials.

## Production

Production actions must occur only through the authorized deployment mechanism.

Repository access is not equivalent to production authorization.

## Rollback

AI may prepare or recommend rollback.

Execution must follow the approved authorization and safety controls.

## AI Product Changes

When deploying AI behavior, the agent must consider:

- Model version
- Prompt/configuration
- Tool definitions
- Retrieval configuration
- Evaluation results
- Cost
- Latency
- Safety

## Self-Review

Before proposing deployment, the agent should verify:

1. What changed?
2. What artifact will be deployed?
3. What evidence supports it?
4. What dependencies are affected?
5. What could fail?
6. How will failure be detected?
7. How will recovery occur?
8. Is the action authorized?

## Final Rule

> **An AI agent can prepare, analyze, validate, and assist. Production authority remains an explicit system and organizational control.**

# Volume 12 Progress

**12-001 through 12-035 complete.**

# Next Document

**12-036 — Deployment Documentation & Runbook Standards**
