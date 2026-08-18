---
title: Infrastructure Secrets Rotation & Certificate Lifecycle
document_id: 10-029
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Secrets Rotation & Certificate Lifecycle

## Purpose

Defines the operational lifecycle for infrastructure credentials, certificates, keys, and other cryptographic material.

## Lifecycle

Every credential should follow:

```text
Provision
→ Distribute
→ Use
→ Monitor
→ Rotate
→ Revoke
→ Retire
```

## Ownership

Every important credential or certificate should have an identifiable owner and purpose.

## Rotation

Rotation should be planned before expiration.

Where practical, support overlapping validity so consumers can transition safely.

## Emergency Rotation

When compromise is suspected:

1. Revoke or restrict the affected credential.
2. Issue replacement credentials.
3. Update consumers.
4. Validate operation.
5. Investigate exposure.
6. Retire compromised material.

## Certificates

Certificate lifecycle must include:

- Issuance
- Secure private-key handling
- Deployment
- Expiration monitoring
- Renewal
- Revocation where required

## Private Keys

Private keys must never be committed to source control or embedded in public artifacts.

## Service Credentials

Service credentials should be scoped to a specific workload or capability.

## CI/CD Credentials

Pipeline credentials should be separate from runtime credentials.

## Cloud Credentials

Prefer workload identity/federation over long-lived static cloud credentials where supported by the platform.

## AI Provider Credentials

AI provider keys must remain outside model context.

The application or infrastructure layer should perform authenticated provider calls.

## Rotation Compatibility

Consumers should tolerate credential transitions without unnecessary downtime.

## Monitoring

Monitor:

- Expiration dates
- Rotation failures
- Unexpected credential use
- Revoked credential attempts

## Documentation

Record:

- Credential purpose
- Owner
- Rotation process
- Dependencies
- Emergency procedure

Do not document secret values.

## Anti-Patterns

Never:

- Hard-code credentials
- Store private keys in repositories
- Share one credential across unrelated systems
- Wait until expiration before planning rotation
- Give AI models raw provider credentials

## AI Context

AI coding agents must use references to secret interfaces and certificate configuration, never real secret values.

# Next Document

**10-030 — Infrastructure Operational Runbooks & Automation**
