# Volume 11 → Volume 13 Testing Handoff

## Purpose

Formally transfers the Testing & QA architecture into Volume 13, where it becomes part of the AI coding agent's implementation context.

## Handoff Status

**Volume 11: 45 / 45 complete.**

## Authoritative Dependencies

The AI implementation context must treat:

- Volume 07 as authoritative for database architecture
- Volume 08 as authoritative for API architecture
- Volume 09 as authoritative for security
- Volume 10 as authoritative for infrastructure
- Volume 11 as authoritative for testing and QA

Volume 13 coordinates these authorities without silently overriding them.

## Mandatory Testing Invariants

The AI agent must preserve:

1. Risk-based test depth
2. Appropriate test-layer boundaries
3. Deterministic testing where possible
4. Environment isolation
5. Controlled test data
6. Regression coverage for important defects
7. Security validation
8. Performance validation where required
9. Recovery validation where required
10. Accessibility and compatibility validation where required
11. AI behavioral evaluation
12. AI adversarial evaluation
13. Deterministic authorization around AI tools
14. Release quality gates
15. Production verification
16. Test ownership and maintainability

## Forbidden Testing Actions

The AI agent must not:

- Delete failing tests merely to achieve green CI
- Disable quality gates without authorization
- Point ordinary tests at production
- Use production credentials in tests
- Treat coverage as proof of correctness
- Allow AI output to replace deterministic authorization
- Hide flaky failures permanently
- Create unbounded performance or fuzz workloads
- Modify evaluation datasets solely to improve AI scores
- Declare production readiness from test existence alone

## Decision Rule

When deciding where to add a test:

1. Identify the behavior and risk.
2. Select the lowest reliable test layer.
3. Add higher-level validation only when necessary.
4. Reuse existing repository patterns.
5. Add regression coverage for meaningful defects.
6. Verify the test can fail when the behavior breaks.

## AI-Specific Rule

AI features require two complementary validation systems:

**Deterministic software testing**
for schemas, permissions, state, resource limits, side effects, and integration.

**AI evaluation**
for model-dependent behavior such as relevance, instruction adherence, grounding, tool selection, and safety behavior.

Neither system replaces the other.

## Release Rule

The AI coding agent must not claim a change is production-ready unless the applicable quality gates have passed and no unresolved blocking failure exists.

## Repository Rule

Volume 13 must map these principles onto the actual repository structure, tooling, CI system, and test framework.

It must not invent unsupported architecture.

## Final Principle

> **Tests are evidence, not decoration. The AI agent must write tests that can genuinely expose incorrect behavior.**

## Final Volume Status

**VOLUME 11 — TESTING & QA: COMPLETE**

**45 / 45 documents complete.**

The next implementation-facing destination is:

**VOLUME 13 — AI BUILD INSTRUCTIONS (`AI_CONTEXT.md`)**

# END OF VOLUME 11
