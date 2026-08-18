# Health Checks, Readiness & Deployment Verification

## Purpose

Defines how Ascend determines whether a deployed service is alive, ready, and safe to receive traffic.

## Principle

A running process is not necessarily a healthy service.

## Liveness

Liveness checks should determine whether the process is functioning sufficiently to remain running.

They must be lightweight and avoid unnecessary dependency chains.

## Readiness

Readiness determines whether the instance should receive traffic.

It may consider required dependencies such as:

- Database connectivity
- Required configuration
- Essential internal services

## Startup

Startup checks should allow applications enough time to initialize without causing premature restarts.

## Dependency Checks

Do not make every optional dependency a mandatory readiness condition.

Optional degradation should remain possible where architecture permits it.

## Deployment Verification

After deployment verify:

- Expected version
- Health
- Readiness
- Critical endpoint
- Authentication
- Database connectivity
- Queue/worker behavior where applicable
- Synthetic critical journey

## Smoke Tests

Volume 11 defines testing requirements. Deployment verification consumes those tests or compatible production-safe checks.

## AI Services

Where AI is critical, verify:

- Provider connectivity
- Required credentials
- Model availability
- Tool registration
- Output contract
- Resource limits

## Health Endpoint Security

Health endpoints must not expose:

- Secrets
- Internal credentials
- Sensitive configuration
- Excessive infrastructure details

## Failure

If readiness or critical verification fails, the rollout must stop or invoke the approved recovery mechanism.

## Anti-Patterns

Avoid health checks that always return success, deep dependency chains in liveness checks, exposing sensitive diagnostics, and declaring deployment successful before verification.

# Next Document

**12-008 — Zero-Downtime & Availability-Aware Deployment**
