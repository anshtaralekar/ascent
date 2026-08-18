# End-to-End Testing & Critical User Journeys

## Purpose

Defines how Ascend validates complete user-facing workflows across the application stack.

## E2E Principle

E2E tests should prove that critical journeys work through the same major boundaries used by real users.

## Journey Selection

Prioritize journeys by:

- User impact
- Business importance
- Failure cost
- Frequency
- Security sensitivity

## Typical Journey Coverage

Where applicable:

- Authentication
- Account onboarding
- Core product workflow
- Data creation/editing
- Search/retrieval
- Critical transactions
- AI-assisted workflow
- Permission-sensitive actions

## Test Structure

A critical journey should establish:

1. Known starting state
2. User identity and permissions
3. Required test data
4. User actions
5. Expected visible/system outcomes
6. Cleanup

## Assertions

Prefer business and user-visible outcomes over fragile implementation details.

## Authentication

Use dedicated test identities.

Never place real production credentials into E2E configuration.

## Multi-Tenant Journeys

Include cross-tenant access attempts where tenant isolation is security-critical.

## AI Journeys

AI E2E tests should validate deterministic application boundaries such as:

- Correct context construction
- Tool authorization
- Output validation
- Failure handling

Live model quality should be evaluated separately through the AI evaluation framework.

## External Dependencies

Use controlled environments or approved test doubles where external instability would make the journey unreliable.

## Browser Testing

Frontend E2E tests should cover supported browser/device combinations according to the product compatibility requirements.

## Flakiness

Investigate root causes such as:

- Race conditions
- Timing assumptions
- Shared state
- Unstable dependencies
- Poor cleanup

Do not solve flakiness by adding arbitrary delays.

## Test Isolation

Parallel journeys must not interfere with one another.

## Failure Diagnostics

E2E infrastructure should retain useful:

- Screenshots
- Console output
- Network information
- Logs
- Trace information

while respecting privacy and security rules.

## Release Gate

Critical E2E journeys should pass before releases that materially affect those journeys.

## Anti-Patterns

Avoid:

- Testing every branch through E2E
- Arbitrary sleeps
- Production credentials
- Shared mutable accounts
- Using E2E as the only testing layer

# Volume 11 Progress

**11-001 through 11-010 complete.**

# Next Document

**11-011 — Regression Testing Strategy**
