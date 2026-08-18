# Unit Testing Standards

## Purpose

Defines standards for fast, deterministic tests of isolated application logic.

## Scope

Use unit tests for pure business rules, transformations, validators, parsers, calculations, and other logic whose correctness can be established without the full application stack.

## Principles

- Test observable behavior.
- Keep tests isolated.
- Keep execution fast.
- Make failures diagnostic.
- Avoid unnecessary framework coupling.
- Prefer explicit test inputs and expected outcomes.

## Arrange, Act, Assert

Prefer a clear structure:

1. Arrange test state.
2. Act on the system under test.
3. Assert observable results.

## Dependencies

Mock or stub dependencies when the purpose of the test is isolated logic.

Do not mock a dependency merely because doing so is easier if the real integration is the behavior being tested.

## Edge Cases

Where relevant, cover:

- Empty input
- Boundary values
- Invalid input
- Null/missing values
- Duplicate values
- Permission-sensitive conditions
- Failure paths

## Determinism

Avoid tests dependent on:

- Wall-clock timing
- Randomness
- Network access
- Shared mutable state
- Developer machine configuration

Control these dependencies explicitly.

## Assertions

Assertions should verify meaningful behavior rather than implementation details.

## Error Testing

Test expected error type, code, state, or observable outcome where appropriate.

## Naming

Test names should communicate:

- Scenario
- Expected behavior

## Coverage

Coverage gaps should guide investigation, not become a target achieved through meaningless assertions.

## AI-Generated Unit Tests

AI-generated tests must be checked for whether they would actually fail when the intended behavior is broken.

## Anti-Patterns

Avoid:

- Testing private implementation details without reason
- Huge unit tests
- Hidden global state
- Random unseeded test data
- Assertions that merely restate the implementation

# Next Document

**11-007 — Component Testing Standards**
