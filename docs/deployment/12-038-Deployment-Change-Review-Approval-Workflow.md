# Deployment Change Review & Approval Workflow

## Purpose

Defines how material production changes are reviewed and authorized.

## Principle

Review depth should reflect change risk.

## Change Classification

Consider:

- User impact
- Security impact
- Data impact
- Infrastructure impact
- Availability impact
- Reversibility
- Blast radius

## Low-Risk Changes

May use predefined automated policies where the architecture and organization permit it.

Examples can include routine dependency or configuration changes with strong automated validation.

## High-Risk Changes

May require explicit review for:

- Database migrations
- IAM changes
- Network changes
- Security controls
- Major infrastructure changes
- High-blast-radius releases
- Material AI behavior changes

## Review Evidence

Reviewers should have access to:

- Change summary
- Artifact identity
- Test evidence
- Security results
- Migration plan
- Rollout strategy
- Recovery plan

## Approval

Approval must be attributable.

Do not treat a successful automated build as implicit human approval for high-risk changes.

## Emergency Changes

Emergency procedures may reduce review time but must preserve accountability, evidence, and post-change review.

## AI-Assisted Review

AI may summarize changes or identify risks.

AI recommendations are advisory unless the organization's explicit approval policy says otherwise.

## Conflict of Interest

Where organizational policy requires separation of duties, the same identity should not both create and independently approve a high-risk production change.

## Audit

Record material approvals and exceptions according to the compliance architecture.

## Anti-Patterns

Avoid rubber-stamp reviews, approval without evidence, undocumented emergency changes, and treating AI-generated summaries as authoritative approval.

# Next Document

**12-039 — Deployment Lifecycle & Continuous Delivery Operations**
