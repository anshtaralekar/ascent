---
title: Human Evaluation
document_id: AI-037
volume: 06
version: 1.0.0
status: Draft
owner: AI Architecture Team
---

# Human Evaluation

> "Some qualities of intelligence require human judgment."

## Purpose

Defines the human review framework used to assess AI outputs where automated metrics are insufficient.

## Philosophy

Human evaluation should complement automated testing by measuring usefulness, clarity, appropriateness, and nuanced quality.

## Evaluation Dimensions

Review:

- Correctness
- Relevance
- Clarity
- Helpfulness
- Safety
- Instruction adherence
- Overall quality

## Review Process

1. Define evaluation criteria
2. Select representative samples
3. Normalize evaluation conditions
4. Collect ratings
5. Capture reviewer feedback
6. Analyze disagreement
7. Aggregate results
8. Feed findings into improvement cycles

## Reviewer Guidelines

Reviewers should receive:

- Clear rubrics
- Consistent examples
- Evaluation context
- Conflict-of-interest guidance
- Escalation procedures

## Inter-Rater Reliability

Monitor:

- Agreement rate
- Rating variance
- Ambiguous criteria
- Reviewer drift

Use calibration sessions when consistency declines.

## Sampling

Prioritize:

- High-impact tasks
- New capabilities
- Regression candidates
- Safety-sensitive outputs
- Low-confidence outputs

## Governance

Require:

- Reviewer access controls
- Evaluation audit trails
- Versioned rubrics
- Reviewer calibration

## Anti-Patterns

Avoid:

- Vague evaluation criteria
- Single-reviewer decisions for critical changes
- Untracked reviewer drift
- Treating subjective ratings as absolute truth

## AI Context

AI coding agents should use human evaluation where automated metrics cannot adequately capture user value, nuance, or safety.

# Next Document

**AI-038 — Continuous Evaluation**
