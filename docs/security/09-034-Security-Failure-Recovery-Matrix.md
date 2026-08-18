---
title: Security Failure & Recovery Matrix
document_id: 09-034
volume: 09
version: 1.0.0
status: Draft
owner: Security Operations & Architecture Team
---

# Security Failure & Recovery Matrix

## Purpose

Defines expected security failure scenarios and the required containment, recovery, and validation behavior.

## Failure Matrix

| Failure | Immediate Response | Recovery | Validation |
|---|---|---|---|
| Credential compromise | Revoke/rotate | Replace trusted credentials | Access review |
| Session compromise | Revoke sessions | Re-authenticate affected users | Session tests |
| Authorization bypass | Disable affected path | Patch policy | Denied-access tests |
| Cross-tenant exposure | Contain access | Repair boundary | Cross-tenant verification |
| Secret leakage | Rotate secret | Audit consumers | Secret scan |
| Dependency compromise | Isolate/remove | Rebuild trusted artifact | Dependency verification |
| Database compromise | Contain access | Restore trusted state | Integrity + authorization tests |
| AI tool abuse | Disable tool/workflow | Repair permission boundary | Tool authorization tests |
| Prompt-injection exploit | Contain affected workflow | Harden boundary | Adversarial AI tests |
| Network exposure | Restrict ingress/egress | Restore intended topology | Network scan |
| Log/audit compromise | Preserve evidence | Restore trusted logging | Audit integrity check |

## Containment Principle

Contain the smallest affected boundary that prevents continued harm.

Do not disable unrelated critical functionality without reason.

## Credential Failures

Rotate or revoke credentials before restoring dependent services when compromise is suspected.

## Authorization Failures

If a security boundary is uncertain, default to denying the sensitive operation until the policy is verified.

## Data Exposure

For suspected data exposure:

1. Stop further exposure.
2. Identify affected data.
3. Identify affected identities/tenants.
4. Preserve evidence.
5. Remediate.
6. Assess required response.

## AI Failures

AI-specific recovery should prioritize:

1. Disable unsafe capability.
2. Preserve evidence.
3. Review tool permissions.
4. Review retrieved/context data.
5. Patch deterministic controls.
6. Re-test adversarial behavior.
7. Re-enable gradually.

## Infrastructure Failure

Restore from trusted configurations and artifacts.

Do not assume the compromised runtime itself is trustworthy.

## Recovery Validation

Verify:

- Authentication
- Authorization
- Tenant isolation
- Secrets
- Network boundaries
- Data integrity
- Audit
- Monitoring
- Critical workflows

## Post-Incident

Record:

- Root cause
- Impact
- Missed control
- Detection quality
- Recovery quality
- Preventive action

## AI Context

AI coding agents must define failure behavior when implementing security-sensitive functionality and must not assume successful execution means safe execution.

# Next Document

**09-035 — Security AI Operating Rules**
