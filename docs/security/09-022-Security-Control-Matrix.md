---
title: Security Control Matrix
document_id: 09-022
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Control Matrix

## Purpose

Maps major security objectives to their expected controls, evidence, and ownership.

## Control Matrix

| Security Objective | Primary Controls | Verification Evidence |
|---|---|---|
| Identity integrity | Authentication, token validation | Authentication tests |
| Access control | RBAC/policy/resource authorization | Positive/negative authorization tests |
| Tenant isolation | Tenant-scoped queries and authorization | Cross-tenant tests |
| Secret protection | Secret manager, scanning, rotation | Secret scans and rotation tests |
| Data confidentiality | Encryption, access control | Configuration and access verification |
| Data integrity | Transactions, validation, authorization | Integrity and workflow tests |
| Network protection | Segmentation, TLS, egress controls | Network/configuration tests |
| API protection | Validation, rate limits, auth | API security tests |
| Application security | Safe APIs, input validation | Static/dynamic testing |
| Supply chain | Dependency controls | Dependency reports |
| AI security | Tool authorization, output validation | AI security tests |
| Detection | Security telemetry, audit | Detection tests |
| Recovery | Incident procedures, backups | Recovery exercises |

## Control Ownership

Each control should have a responsible technical or operational owner.

## Preventive Controls

Examples:

- Authentication
- Authorization
- Encryption
- Network restrictions
- Input validation
- Secret management

## Detective Controls

Examples:

- Security logs
- Alerts
- Anomaly detection
- Audit events
- Vulnerability scanning

## Corrective Controls

Examples:

- Credential rotation
- Incident containment
- Vulnerability remediation
- Recovery procedures

## Compensating Controls

If a primary control cannot be implemented immediately, use a documented compensating control with explicit residual risk.

## Automation

Prefer controls that can be automatically verified in CI/CD or runtime systems.

## Evidence

Security claims should be supported by executable or operational evidence.

## Review

Review the matrix after material architecture changes.

## AI Controls

AI-specific controls must include:

- Prompt-injection resistance
- Tool authorization
- Data minimization
- Structured output validation
- Usage controls
- Auditability

## Anti-Patterns

Avoid:

- Controls without owners
- Controls without verification
- Documentation-only controls for high-risk requirements
- Assuming one control provides complete protection

## AI Context

AI coding agents should map security-sensitive implementation decisions to the relevant control instead of treating security as an unstructured checklist.

# Next Document

**09-023 — Security Implementation Sequence**
