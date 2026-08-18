---
title: Security Implementation Sequence
document_id: 09-023
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Implementation Sequence

## Purpose

Defines the recommended sequence for implementing security-sensitive functionality.

## Standard Sequence

**Classify → Threat Model → Define Trust Boundary → Identity → Authorization → Data Protection → Implementation → Testing → Monitoring → Release**

## Phase 1: Classify

Determine:

- Data sensitivity
- Resource sensitivity
- Actor type
- Privilege level
- External exposure
- AI involvement

## Phase 2: Threat Model

Identify:

- Assets
- Attackers
- Trust boundaries
- Abuse cases
- Failure scenarios

## Phase 3: Trust Boundary

Explicitly define what is trusted and what is not.

Never rely on an implied boundary.

## Phase 4: Identity

Determine how every relevant actor is authenticated.

## Phase 5: Authorization

Define:

- Actor
- Action
- Resource
- Tenant
- Policy

## Phase 6: Data Protection

Determine:

- Encryption
- Minimization
- Retention
- Logging restrictions
- External sharing

## Phase 7: Implementation

Use established security libraries, middleware, policies, and infrastructure.

## Phase 8: Testing

Test both:

- Expected allowed behavior
- Adversarial denied behavior

## Phase 9: Monitoring

Define signals for:

- Abuse
- Authentication failures
- Authorization failures
- Privilege changes
- Data access
- AI tool use

## Phase 10: Release

Verify security readiness and unresolved risks before production deployment.

## AI-Specific Sequence

For AI capabilities:

**Input classification → Prompt/data boundary → Model → Proposed action → Schema validation → Authorization → Tool execution → Audit**

## Existing Controls

Before adding a new security mechanism, inspect whether an approved mechanism already exists.

## Exceptions

If architecture cannot follow the sequence, document the reason and compensating controls.

## AI Context

AI coding agents should follow this sequence for security-sensitive work and should not start implementation by adding ad-hoc permission or credential logic.

# Next Document

**09-024 — Security Readiness & Acceptance Criteria**
