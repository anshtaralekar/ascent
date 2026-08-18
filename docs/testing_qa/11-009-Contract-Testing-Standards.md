# Contract Testing Standards

## Purpose

Defines how Ascend verifies compatibility between independently implemented system boundaries.

## Contract Principle

A contract test verifies what a consumer and provider must agree upon, rather than testing either implementation internally.

## Contract Scope

Contracts may exist between:

- Frontend and backend
- Service and service
- Application and external provider adapter
- Worker and queue publisher
- Internal SDK and API

## API Contracts

Validate:

- HTTP method
- Path
- Parameters
- Headers
- Request schema
- Response schema
- Error behavior
- Required fields
- Compatibility rules

Volume 08 remains authoritative for API definitions.

## Consumer Expectations

Consumers should define the behavior they actually rely on.

Avoid contracts containing irrelevant implementation details.

## Provider Verification

Providers must verify that they satisfy agreed contracts before release.

## Backward Compatibility

Changes should preserve existing consumers where the API/versioning strategy requires compatibility.

## Breaking Changes

Breaking changes require:

- Explicit identification
- Consumer impact analysis
- Migration strategy
- Appropriate versioning or coordinated rollout

## Event Contracts

For asynchronous messages validate:

- Schema
- Required fields
- Encoding
- Version
- Semantics
- Compatibility

## External Providers

Provider adapters should isolate external contract differences from the rest of the application.

## Contract Versioning

Contract versions must be traceable to the implementation they describe.

## Failure Contracts

Where applicable test documented error responses and failure semantics.

## AI Interfaces

AI tool interfaces should be treated as contracts too.

Validate:

- Tool name
- Input schema
- Authorization requirements
- Output schema
- Failure behavior

The model must not be treated as the authority for tool permissions.

## Anti-Patterns

Avoid:

- Contracts that duplicate every implementation detail
- Breaking changes without migration planning
- Assuming a provider's documentation guarantees your adapter works
- Treating natural-language AI output as a stable API without validation

# Next Document

**11-010 — End-to-End Testing & Critical User Journeys**
