---
title: Database Security Threat Model
document_id: 07-033
volume: 07
version: 1.0.0
status: Draft
owner: Security & Data Architecture Team
---

# Database Security Threat Model

## Purpose

Defines the principal threats against Ascend data stores and the architectural controls used to reduce their likelihood and impact.

## Threat Model

Consider threats involving:

- Unauthorized database access
- Credential compromise
- SQL injection
- Privilege escalation
- Cross-tenant access
- Data exfiltration
- Malicious or accidental deletion
- Backup exposure
- Insider misuse
- Vulnerable dependencies
- Misconfigured network access
- AI-mediated unauthorized retrieval

## Trust Boundaries

Important boundaries include:

**User → API**

**API → Service**

**Service → Data Access Layer**

**Application → Database**

**Database → Derived Stores**

**AI Agent → Tool/Data Interface**

Credentials must never cross into untrusted boundaries.

## SQL Injection

Prevent through:

- Parameterized queries
- Safe query builders
- ORM parameter binding
- Input validation as defense in depth

Never rely on escaping alone.

## Privilege Escalation

Use separate identities and least-privilege roles.

Administrative capabilities must not be inherited by ordinary application services.

## Tenant Isolation

Treat tenant isolation as a security control.

Test:

- Direct queries
- APIs
- Background workers
- Caches
- Search
- Vector retrieval
- Administrative workflows

## Data Exfiltration

Control:

- Large exports
- Administrative queries
- Backup access
- Data replication
- Debug tooling
- Analytics pipelines

## Credential Security

Protect database credentials using managed secret storage, rotation, restricted access, and auditability.

## Backup Threats

Backups must have access controls and encryption equivalent to the sensitivity of the protected data.

## AI Threats

AI systems introduce additional risks:

- Prompt-driven unauthorized retrieval
- Tool misuse
- Data leakage through context
- Insecure generated queries
- Cross-tenant semantic retrieval
- Persistent memory of sensitive information

AI must never receive unrestricted database credentials simply because it can generate SQL.

## Detection

Monitor for:

- Failed authentication
- Unusual access volume
- Privilege changes
- Large exports
- Unexpected query patterns
- Cross-tenant access attempts
- Administrative activity

## Response

Security incidents require:

1. Detection
2. Containment
3. Credential or access revocation where necessary
4. Evidence preservation
5. Scope assessment
6. Recovery
7. Root-cause remediation

## Governance

Security-sensitive database changes require threat assessment proportional to their impact.

## Anti-Patterns

Avoid:

- Public database exposure without strong justification
- Shared admin credentials
- Direct AI database access
- Logging secrets
- Trusting client-controlled authorization fields

## AI Context

AI coding agents must evaluate database changes for injection, privilege, tenant isolation, data exposure, credential handling, and AI-mediated access risks.

# Next Document

**07-034 — Database Capacity Planning**
