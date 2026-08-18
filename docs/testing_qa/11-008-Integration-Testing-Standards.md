# Integration Testing Standards

## Purpose

Defines how Ascend validates interactions between real application components and important infrastructure dependencies.

## Scope

Integration testing may cover:

- Database
- Cache
- Queue
- Object storage
- Authentication
- External service adapters
- Internal service boundaries

## Principle

Use real integration points when the interaction itself is the risk.

## Database Integration

Where appropriate validate:

- Queries
- Constraints
- Transactions
- Migrations
- Index behavior
- Serialization
- Connection handling

Database tests must remain consistent with Volume 07.

## API Integration

Validate request/response behavior against the contracts in Volume 08.

## Messaging Integration

Test:

- Publishing
- Consumption
- Serialization
- Retry behavior
- Idempotency
- Dead-letter behavior

## Authentication Integration

Validate actual authentication flows where practical, including invalid and expired credentials.

## External Providers

Use sandbox providers or controlled provider environments when testing real provider behavior.

## AI Providers

Where live AI integration is required, control:

- Model/provider
- Credentials
- Usage
- Cost
- Input data
- Output handling

Do not make ordinary deterministic CI dependent on an uncontrolled external model.

## Isolation

Each integration test must control the state it creates.

## Cleanup

Use transactional rollback, isolated resources, disposable environments, or explicit cleanup according to the dependency.

## Failure Testing

Validate:

- Timeout
- Connection failure
- Invalid response
- Rate limit
- Partial dependency failure

## Reliability

Integration tests should detect compatibility and operational assumptions that unit tests cannot see.

## Anti-Patterns

Avoid:

- Integration tests that silently hit production
- Shared state without cleanup
- Live provider dependencies for every PR
- Treating mocks as proof of integration compatibility

# Next Document

**11-009 — Contract Testing Standards**
