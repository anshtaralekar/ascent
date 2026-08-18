---
title: Secure Software Development Lifecycle
document_id: 09-011
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Secure Software Development Lifecycle

## Purpose

Defines how security is incorporated throughout requirements, design, implementation, testing, deployment, and maintenance.

## Philosophy

Security must move left without becoming disconnected from production reality. Every stage should identify and reduce security risk appropriate to the change.

## Lifecycle

The security lifecycle is:

**Requirements → Threat Model → Secure Design → Implementation → Security Testing → Release Review → Monitoring → Incident Learning**

## Requirements

Identify:

- Sensitive data
- Trust boundaries
- Authentication needs
- Authorization requirements
- Compliance constraints where applicable
- Abuse scenarios
- Availability requirements

## Design

Security design should address:

- Identity
- Access control
- Data protection
- Network boundaries
- Secrets
- Dependencies
- Failure modes
- Auditability

## Implementation

Developers and AI coding agents must use approved security primitives.

Do not create parallel implementations of:

- Authentication
- Authorization
- Encryption
- Secret storage
- Session handling

## Code Review

Security-sensitive changes require review appropriate to risk.

Review for:

- Privilege changes
- Input handling
- Data exposure
- Dependency changes
- Authentication
- Authorization
- External access

## Testing

Security testing should include appropriate:

- Unit tests
- Integration tests
- Authorization tests
- Static analysis
- Dependency scanning
- Dynamic testing
- Penetration testing for relevant high-risk areas

## Dependency Management

New dependencies should be evaluated for:

- Purpose
- Maintenance
- Security history
- License requirements
- Supply-chain risk
- Required privileges

## Release

Before production release, verify security controls and unresolved risks.

Critical unresolved security failures block release unless formally accepted through the project's risk process.

## Runtime

Production monitoring should detect security anomalies and feed incidents back into the lifecycle.

## AI Development

AI-generated code receives the same security requirements as human-written code.

AI assistance does not reduce review requirements.

## Exceptions

Security exceptions must be:

- Explicit
- Scoped
- Owned
- Documented
- Reviewed periodically

## Anti-Patterns

Avoid:

- Security review only after deployment
- Blind trust in generated code
- Custom security primitives
- Ignoring dependency risk
- Treating passing functional tests as security validation

## AI Context

AI coding agents must incorporate security into implementation and self-review rather than treating it as a later handoff.

# Next Document

**09-012 — Secure Coding Standards**
