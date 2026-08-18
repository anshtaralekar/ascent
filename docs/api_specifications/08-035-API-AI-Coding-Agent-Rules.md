---
title: API AI Coding-Agent Rules
document_id: 08-035
volume: 08
version: 1.0.0
status: Draft
owner: API Architecture Team
---

# API AI Coding-Agent Rules

> "An API is a contract first and an implementation second."

## Purpose

Defines mandatory behavior for AI coding agents creating, modifying, reviewing, or debugging Ascend API functionality.

## Rule 1: Inspect Before Implementing

Before changing an API, inspect:

- Existing endpoints
- API schemas
- Authentication
- Authorization
- Services
- Database access
- Integrations
- Events/jobs
- Tests
- Documentation
- ADRs

## Rule 2: Define the Contract

Determine:

- Input
- Output
- Errors
- Authentication
- Authorization
- Pagination
- Rate limits
- Idempotency
- Sync/async behavior

Do not begin implementation from an ambiguous endpoint description.

## Rule 3: Respect Layer Boundaries

Handlers/controllers should not become business-logic containers.

Use the approved flow:

**Transport → Service → Data/Integration**

## Rule 4: Authorization Is Server-Side

Never trust client-provided:

- Tenant IDs
- User IDs
- Roles
- Permissions
- Ownership claims

Derive or verify them from trusted context.

## Rule 5: Model Output Is Untrusted

AI-generated tool arguments, structured outputs, URLs, identifiers, and commands must undergo normal validation and authorization.

## Rule 6: Protect Data

Do not:

- Return entire database entities
- Log sensitive request bodies
- Expose secrets
- Leak internal errors
- Cross tenant boundaries

## Rule 7: Bound Resources

Every new endpoint should consider:

- Request size
- Response size
- Query limits
- Timeouts
- Rate limits
- Concurrency
- Batch size

## Rule 8: Define Retry Behavior

For every state-changing operation determine:

- Is it idempotent?
- Can the request be duplicated?
- What happens after timeout?
- What external side effects may already have occurred?

## Rule 9: Use Approved Async Patterns

Long-running operations should use the established job/queue architecture rather than indefinite HTTP requests.

## Rule 10: Treat External Systems as Untrusted Dependencies

Define:

- Timeout
- Retry
- Error mapping
- Circuit/degradation behavior
- Data sharing

## Rule 11: Preserve API Compatibility

Prefer additive changes.

Do not remove or reinterpret existing fields without an approved migration/versioning strategy.

## Rule 12: Test Security

At minimum, test relevant:

- Authentication
- Authorization
- Tenant isolation
- Validation
- Rate limits
- Injection
- Retry/idempotency
- Sensitive-data exposure

## Rule 13: Test Real Boundaries

Do not rely exclusively on mocked unit tests.

Use contract and integration tests for important API behavior.

## Rule 14: Document the Contract

Update the authoritative API specification and developer documentation whenever behavior changes.

## Rule 15: Add Observability

New endpoints should expose appropriate:

- Metrics
- Correlation
- Error categories
- Dependency telemetry
- Audit events for important actions

## Rule 16: AI Tool Safety

When creating an AI tool:

- Define exact capability
- Define input schema
- Define output schema
- Define permissions
- Define side effects
- Define idempotency
- Define audit behavior

Never create unrestricted tools when a narrow tool can satisfy the workflow.

## Rule 17: No Unauthorized Architecture

Do not introduce a new gateway, API paradigm, messaging system, authentication mechanism, or provider without architectural justification.

## Required Self-Review

Before completing an API task, verify:

- [ ] Contract defined
- [ ] Authentication defined
- [ ] Authorization enforced
- [ ] Tenant scope enforced
- [ ] Validation implemented
- [ ] Error contract implemented
- [ ] Rate/resource limits considered
- [ ] Idempotency/retry behavior defined
- [ ] Database/integration behavior safe
- [ ] Tests added
- [ ] Documentation updated
- [ ] Observability added
- [ ] Deployment compatibility assessed
- [ ] AI/tool permissions reviewed where applicable

## Forbidden Patterns

The agent must not:

- Put business logic directly into controllers without justification
- Trust client authorization fields
- Expose raw SQL/database errors
- Create unrestricted query endpoints
- Allow arbitrary URL fetching
- Give AI agents unrestricted database access
- Skip API contract updates
- Add infinite retries
- Create unbounded collections
- Log secrets or sensitive payloads
- Introduce undocumented breaking changes

## Conflict Resolution

If the requested implementation conflicts with an existing architecture rule:

1. Identify the conflict.
2. Explain the affected boundary.
3. Check relevant ADRs/specifications.
4. Do not silently bypass the rule.
5. Escalate or document the approved deviation.

## Volume 13 Bridge

These rules must be propagated into Volume 13 `AI_CONTEXT.md`, especially:

- Chapter 3: Tech Stack
- Chapter 5: Frontend Rules
- Chapter 6: Backend Rules
- Chapter 8: API Rules
- Chapter 9: AI Integration Rules
- Chapter 10: Coding Standards
- Chapter 11: Naming Standards
- Chapter 13: State Management Rules
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

**The AI coding agent is an implementation executor operating inside an approved API architecture. It may propose improvements, but it must not silently redefine the API architecture.**

# Volume 08 Status

**08-001 through 08-035 complete.**
