---
title: Threat Modeling & Security Risk Management
document_id: 09-002
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Threat Modeling & Security Risk Management

## Purpose

Defines how security threats are identified, analyzed, prioritized, mitigated, and reviewed throughout product development.

## Philosophy

Threat modeling should happen before vulnerabilities become implementation details.

## Threat Modeling Scope

Threat models should consider:

- Users
- Services
- APIs
- Databases
- Files
- External integrations
- AI systems
- Administrative interfaces
- Infrastructure
- Deployment pipelines

## Assets

Identify assets such as:

- Credentials
- Authentication tokens
- Personal data
- Tenant data
- Business data
- Source code
- Infrastructure credentials
- AI context
- Files
- Configuration
- Audit records

## Trust Boundaries

Document where trust changes between components.

For each boundary ask:

- Who controls the source?
- Can the data be modified?
- How is identity established?
- How is authorization enforced?
- What happens if the source is compromised?

## Threat Categories

At minimum consider:

- Spoofing
- Tampering
- Repudiation
- Information disclosure
- Denial of service
- Elevation of privilege

Also consider modern application threats such as:

- SSRF
- Credential theft
- Supply-chain compromise
- Cross-tenant access
- API abuse
- Prompt injection
- Tool abuse
- Data poisoning

## Risk Assessment

Prioritize risks using:

- Likelihood
- Impact
- Exploitability
- Exposure
- Detectability

Critical risks should not be deferred without explicit acceptance.

## Mitigation

Mitigations should be:

- Specific
- Testable
- Owned
- Appropriate to the threat

## Residual Risk

After mitigation, document material residual risks rather than assuming risk has become zero.

## AI Threat Modeling

AI workflows must explicitly model:

- Prompt injection
- Indirect prompt injection
- Tool misuse
- Data exfiltration through tools
- Excessive agency
- Unauthorized actions
- Retrieval poisoning
- Sensitive-context leakage
- Model/provider compromise

## Review Triggers

Revisit threat models when introducing:

- New trust boundaries
- New authentication mechanisms
- New external providers
- New sensitive data
- New administrative capabilities
- New AI tools
- Major architecture changes

## Security Exceptions

Exceptions must document:

- Threat
- Reason for exception
- Compensating control
- Owner
- Expiration/review date

## Anti-Patterns

Avoid:

- Threat modeling only after implementation
- Treating a checklist as a complete threat model
- Ignoring AI-specific threats
- Accepting critical risks without ownership

## AI Context

AI coding agents must identify security-sensitive changes and consult the applicable threat model before implementation.

# Next Document

**09-003 — Identity & Authentication Architecture**
