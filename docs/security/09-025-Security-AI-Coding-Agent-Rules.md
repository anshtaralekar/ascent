---
title: Security AI Coding-Agent Rules
document_id: 09-025
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security AI Coding-Agent Rules

> "Security decisions belong to deterministic controls, not generated intent."

## Purpose

Defines mandatory behavior for AI coding agents working on security-sensitive parts of Ascend.

## Rule 1: Inspect Before Changing Security

Before modifying security behavior, inspect:

- Existing authentication
- Authorization
- Security middleware
- Secret management
- Encryption utilities
- Network controls
- Security tests
- Threat models
- ADRs
- Relevant Volume 07 and Volume 08 rules

## Rule 2: Reuse Approved Controls

Do not create a parallel:

- Authentication system
- Authorization system
- Secret store
- Encryption utility
- Session mechanism

when an approved implementation already exists.

## Rule 3: Never Trust the Client

Never treat client-provided values as authoritative for:

- User identity
- Role
- Permission
- Tenant
- Ownership
- Administrative status

## Rule 4: Never Trust Model Output

AI-generated:

- Tool calls
- URLs
- SQL
- Identifiers
- Commands
- Structured objects

must be validated and authorized before execution.

## Rule 5: Least Privilege

Grant the minimum permissions necessary to:

- Users
- Services
- Workers
- API clients
- AI agents
- CI/CD systems

## Rule 6: Fail Securely

Sensitive authorization decisions should fail closed when permission cannot be established.

Do not convert an authorization failure into permissive behavior.

## Rule 7: Protect Secrets

Never place secrets in:

- Source code
- Logs
- Test fixtures
- API responses
- AI prompts
- Generated documentation

## Rule 8: Protect Tenant Boundaries

Every tenant-scoped resource access must verify tenant scope server-side.

## Rule 9: Bound Resources

Security-sensitive and expensive operations must have appropriate:

- Rate limits
- Quotas
- Payload limits
- Concurrency limits
- Timeouts

## Rule 10: Treat External Data as Untrusted

User files, web pages, retrieved documents, webhook payloads, and external provider responses may contain malicious instructions or content.

## Rule 11: Secure AI Tools

Every AI tool must define:

- Exact capability
- Input schema
- Permission
- Resource scope
- Side effects
- Audit behavior
- Failure behavior

Prefer narrow capabilities.

## Rule 12: No Arbitrary Execution

Do not create unrestricted:

- Shell tools
- SQL tools
- Network fetchers
- Filesystem tools
- Infrastructure administration tools

unless the architecture explicitly requires them and provides equivalent containment.

## Rule 13: Security Testing

For security-sensitive changes, add appropriate tests for:

- Allowed access
- Denied access
- Boundary conditions
- Abuse
- Injection
- Data exposure
- AI/tool misuse

## Rule 14: Do Not Disable Security to Debug

Never solve development friction by weakening production security controls.

Use safe development configuration or controlled test environments.

## Rule 15: Dependency Discipline

Do not introduce a security-sensitive dependency without assessing whether an existing approved capability already exists.

## Rule 16: Document Security Decisions

Material changes to trust boundaries, privileges, cryptography, authentication, authorization, or AI capabilities require appropriate documentation.

## Rule 17: Incident Awareness

If a code change appears to expose a credential, bypass authorization, leak sensitive data, or introduce a critical security issue, stop normal implementation and surface the risk.

## Required Self-Review

Before completing a security-sensitive task:

- [ ] Trust boundaries identified
- [ ] Authentication identified
- [ ] Authorization enforced
- [ ] Tenant scope enforced
- [ ] Sensitive data minimized
- [ ] Secrets protected
- [ ] Inputs validated
- [ ] External data treated as untrusted
- [ ] Resource limits considered
- [ ] Security tests added
- [ ] Monitoring considered
- [ ] Threat model reviewed
- [ ] Deployment implications assessed
- [ ] AI tool permissions reviewed where applicable

## Forbidden Patterns

The agent must not:

- Bypass authorization
- Trust client roles
- Expose secrets
- Add custom cryptography
- Store plaintext passwords
- Add unrestricted AI tools
- Allow arbitrary SQL from AI
- Allow arbitrary shell execution
- Allow arbitrary network access from trusted infrastructure
- Disable security controls without explicit approval
- Silently ignore critical security findings

## Conflict Resolution

When a request conflicts with security architecture:

1. Identify the security boundary.
2. Identify the requested privilege.
3. Check applicable architecture/specification.
4. Explain the conflict.
5. Propose a compliant alternative where possible.
6. Do not silently weaken the control.

## Volume 13 Bridge

These rules must propagate into:

- Chapter 3: Tech Stack
- Chapter 6: Backend Rules
- Chapter 7: Database Rules
- Chapter 8: API Rules
- Chapter 9: AI Integration Rules
- Chapter 10: Coding Standards
- Chapter 14: Performance Rules
- Chapter 15: Security Rules
- Chapter 16: Accessibility Rules
- Chapter 17: Testing Rules
- Chapter 18: Deployment Rules
- Chapter 19: Definition of Done
- Chapter 20: Forbidden Patterns
- Chapter 21: Decision Tree
- Chapter 23: Self Review Checklist
- Chapter 25: AI Operating Manual

## Final Rule

**The AI coding agent operates inside the security architecture. It may implement and propose security improvements, but it must never silently reduce, bypass, or redefine security controls.**

# Volume 09 Progress

**09-001 through 09-025 complete.**

# Next Document

**09-026 — Security Data Classification & Handling Standard**
