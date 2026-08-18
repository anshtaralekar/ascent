# Production Verification & Synthetic Monitoring

## Purpose

Defines how Ascend validates critical production behavior continuously without relying only on internal telemetry.

## Principle

Production verification should confirm that real user-facing capabilities remain available after deployment and during normal operation.

## Synthetic Monitoring

Synthetic checks simulate controlled user or API behavior against production.

Typical checks include:

- DNS/TLS
- Authentication
- Critical API
- Core user journey
- Health/readiness
- Critical AI workflow where appropriate

## Safety

Production synthetic checks must be:

- Low risk
- Explicitly scoped
- Non-destructive where possible
- Protected from real-user data exposure
- Rate-limited

## Test Accounts

Use dedicated synthetic identities and data.

Never use ordinary users' accounts for synthetic monitoring.

## Frequency

Frequency should reflect business criticality and acceptable monitoring cost.

## AI Monitoring

Where AI is business-critical, verify deterministic boundaries such as:

- Provider connectivity
- Authentication
- Tool availability
- Output schema
- Latency
- Error handling

Do not require subjective model quality for every production probe unless explicitly designed as a quality monitor.

## Alerts

Synthetic failures should identify:

- Check
- Region/environment
- Failure
- Duration
- Likely impact
- Ownership

## Correlation

Correlate synthetic failures with:

- Deployments
- Infrastructure changes
- Provider incidents
- Application telemetry

## Recovery Verification

After remediation, verify the affected journey rather than merely checking that a process restarted.

## Anti-Patterns

Avoid destructive synthetic tests, production credentials, overly frequent expensive AI checks, and treating synthetic success as proof that every user journey works.

# Next Document

**11-037 — Release Acceptance & Quality Gate Architecture**
