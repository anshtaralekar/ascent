# Component Testing Standards

## Purpose

Defines standards for testing meaningful application components while keeping unrelated infrastructure outside the test boundary.

## Component Definition

A component may be:

- Service module
- Backend domain component
- Frontend feature module
- Worker
- Adapter
- Processing pipeline

The exact boundary follows the architecture.

## Goal

Component tests should validate how a component behaves as a unit of functionality, not every internal function independently.

## Dependencies

Use realistic test doubles for external dependencies when the component's own behavior is the focus.

Important external behavior should also be covered by integration tests.

## Inputs

Test:

- Valid inputs
- Invalid inputs
- Boundary values
- Missing fields
- Unexpected states
- Authorization-sensitive inputs

## Outputs

Verify externally meaningful:

- Results
- State changes
- Errors
- Events
- Side effects

## State

Tests should explicitly establish required state rather than relying on previous tests.

## Frontend Components

Where applicable validate:

- Rendering
- User interaction
- Loading states
- Error states
- Empty states
- Accessibility-relevant behavior

Avoid tests tightly coupled to incidental DOM structure.

## Backend Components

Validate:

- Business behavior
- Validation
- Error mapping
- Dependency interaction
- Transaction boundaries where appropriate

## AI Components

For AI-enabled components, test deterministic boundaries around:

- Input construction
- Output parsing
- Tool authorization
- Failure handling
- Retry behavior
- Provider adapter behavior

Do not rely on one live model response to prove deterministic application logic.

## Isolation

Component tests should not depend on test execution order.

## Anti-Patterns

Avoid:

- Testing the entire application as a component
- Mocking every internal function
- Snapshotting unstable AI output as the only assertion
- Reusing mutable state between tests

# Next Document

**11-008 — Integration Testing Standards**
