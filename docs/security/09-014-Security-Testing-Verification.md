---
title: Security Testing & Verification
document_id: 09-014
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Testing & Verification

## Purpose

Defines how security controls are tested and how evidence is produced before and after release.

## Philosophy

A security control that has never been tested is an assumption.

## Testing Layers

Use an appropriate combination of:

- Unit security tests
- Integration tests
- Contract tests
- Static analysis
- Dependency scanning
- Dynamic application testing
- Infrastructure scanning
- Penetration testing
- Configuration validation

## Authentication Testing

Test:

- Missing credentials
- Invalid credentials
- Expired credentials
- Revoked credentials
- Token manipulation
- Session invalidation

## Authorization Testing

Test:

- Allowed access
- Denied access
- Cross-user access
- Cross-tenant access
- Privilege escalation
- Administrative boundaries

## Input Security Testing

Test malicious and boundary inputs for:

- Injection
- Path traversal
- SSRF
- Oversized payloads
- Malformed structures
- Unexpected types

## API Security Testing

Validate:

- Rate limits
- CORS behavior
- CSRF protections where applicable
- Error disclosure
- Object-level authorization
- File permissions
- Webhook verification

## AI Security Testing

Test:

- Direct prompt injection
- Indirect prompt injection
- Malicious retrieved content
- Tool argument manipulation
- Unauthorized tool access
- Data exfiltration attempts
- Excessive agency
- Unsafe structured outputs

## Secrets Testing

Verify that secrets do not appear in:

- Source
- Logs
- Build artifacts
- Client bundles
- Error responses

## Dependency Testing

Automated scanning should identify known vulnerable components.

## Regression Testing

Security tests should remain in the suite after a vulnerability is fixed where practical.

## Penetration Testing

High-risk surfaces should receive appropriately scoped manual testing.

## Evidence

Record meaningful test evidence such as:

- Tool results
- Test reports
- Findings
- Remediation
- Risk acceptance

## False Positives

Security findings should be triaged rather than blindly ignored.

Document justified exceptions.

## Release Gate

Critical unresolved security findings block release unless explicitly accepted through the security risk process.

## AI Context

AI coding agents must add relevant security regression tests when modifying security-sensitive behavior.

# Next Document

**09-015 — Security Monitoring & Detection**
