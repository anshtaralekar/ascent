---
title: Infrastructure Security Hardening & Policy
document_id: 10-021
volume: 10
version: 1.0.0
status: Draft
owner: Infrastructure & DevOps Architecture Team
---

# Infrastructure Security Hardening & Policy

## Purpose

Defines baseline security requirements for infrastructure, runtimes, operating systems, containers, networks, and operational tooling.

## Principle

Infrastructure should expose the smallest practical attack surface and begin from secure defaults.

## Baseline Hardening

Production infrastructure should:

- Disable unnecessary services
- Remove unnecessary packages
- Restrict network exposure
- Enforce least privilege
- Use supported software versions
- Enable appropriate security monitoring
- Protect administrative interfaces

## Operating Systems

Where operating systems are used directly, maintain:

- Supported versions
- Security patches
- Minimal installed components
- Controlled administrative access
- Secure configuration baselines

## Containers

Apply 10-004 requirements including:

- Non-root execution where practical
- Reduced capabilities
- Minimal images
- Resource limits
- Secret isolation

## Network Hardening

Apply:

- Explicit ingress rules
- Controlled egress
- Private data services
- Restricted administrative access
- Environment segmentation

## Cloud Resources

Cloud resources should use:

- Least-privileged IAM
- Encryption
- Secure defaults
- Logging
- Policy controls

## Administrative Access

Administrative access should be:

- Individually attributable
- Strongly authenticated
- Restricted
- Audited

## Configuration Hardening

Security-sensitive configuration must not silently fall back to permissive values.

## Patch Management

Patch according to risk and exploitability.

Critical vulnerabilities require expedited remediation.

## Vulnerability Management

Track vulnerabilities across:

- Hosts
- Containers
- Dependencies
- Infrastructure providers
- IaC modules
- Build tooling

## Secrets

Follow 10-007 and Volume 09. Never embed production credentials into infrastructure artifacts.

## AI Infrastructure

AI workloads should be treated as untrusted compute where appropriate.

Do not grant AI workloads infrastructure administrator privileges merely for convenience.

## Security Validation

Hardening should be verified through automated policy checks, vulnerability scans, configuration assessment, and targeted manual review.

## Anti-Patterns

Avoid:

- Default administrator access
- Public management ports
- Unpatched production hosts
- Unnecessary privileged containers
- Broad cloud permissions
- Security controls disabled to simplify deployment

## AI Context

AI coding agents must inspect existing hardening baselines before modifying infrastructure and must not weaken them without an explicit architectural decision.

# Next Document

**10-022 — Infrastructure Compliance & Policy-as-Code**
