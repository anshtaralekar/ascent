# Test Maintenance & Lifecycle Management

## Purpose

Defines how tests remain accurate, efficient, and relevant as Ascend evolves.

## Principle

Tests are software and require maintenance.

## Lifecycle

```text
Create
→ Validate
→ Run
→ Monitor
→ Maintain
→ Refactor
→ Retire
```

## Maintenance Triggers

Review tests when:

- Product behavior changes
- APIs change
- Database schemas change
- UI changes
- Infrastructure changes
- Dependencies are upgraded
- AI models/providers change

## Test Refactoring

Refactor tests when:

- They duplicate coverage
- They are excessively slow
- They are difficult to diagnose
- They rely on obsolete architecture
- Their assertions no longer represent business behavior

## Test Retirement

A test may be retired when:

- The behavior no longer exists
- The requirement was intentionally removed
- A better validation layer replaces it

Important retirement decisions should be documented.

## Fixture Maintenance

Remove obsolete fixtures and keep shared data minimal.

## AI Evaluation Maintenance

When models, prompts, retrieval systems, or tools change:

- Re-run relevant baselines
- Review historical failures
- Add new failure cases
- Remove obsolete cases only with justification

## Dependency Changes

After major test-framework or browser changes, review compatibility and test stability.

## Runtime Cost

Track expensive test suites.

Optimize without reducing meaningful coverage.

## Test Performance

Slow tests should be classified by reason:

- Necessary environment startup
- Real integration cost
- Poor test isolation
- Inefficient fixtures
- Excessive E2E usage

## Documentation

Tests should make their purpose discoverable through names, organization, and documentation where needed.

## Anti-Patterns

Avoid keeping obsolete tests forever, deleting regression cases without reason, accepting permanent slowness, or silently changing AI evaluation datasets to improve results.

# Next Document

**11-040 — Testing Toolchain & CI Integration Specification**
