---
title: Model Routing
document_id: AI-045
volume: 06
version: 1.0.0
status: Draft
owner: AI Architecture Team
---

# Model Routing

> "Use the right amount of intelligence for the right task."

## Purpose

Defines the architecture for dynamically selecting AI models based on task requirements, quality targets, latency, cost, and operational constraints.

## Philosophy

Model selection should be workload-aware rather than permanently bound to a single model.

## Routing Lifecycle

1. Receive task
2. Classify workload
3. Determine requirements
4. Filter eligible models
5. Score candidates
6. Select model
7. Execute
8. Evaluate outcome
9. Update routing signals

## Routing Signals

Consider:

- Task complexity
- Context size
- Required quality
- Latency target
- Cost budget
- Tool requirements
- Safety classification
- Model availability

## Routing Strategies

Support:

- Rule-based routing
- Capability-based routing
- Cost-aware routing
- Quality-aware routing
- Adaptive routing

## Fallbacks

Support:

- Secondary models
- Provider failover
- Reduced-capability modes
- Retry with alternative models

## Performance

Monitor:

- Selection latency
- Model success rate
- Cost per task
- Quality by route
- Fallback frequency

## Evaluation

Compare routing policies using consistent workloads and measure whether routing improves overall system utility.

## Governance

Require:

- Approved model inventory
- Capability metadata
- Routing policy versions
- Audit logs
- Safety eligibility checks

## Anti-Patterns

Avoid:

- Routing solely by price
- Selecting unavailable models
- Ignoring context requirements
- Changing routing without regression testing

## AI Context

AI coding agents should use model routing to balance capability, cost, latency, and safety while retaining deterministic fallback behavior.

# Next Document

**AI-046 — Caching Architecture**
