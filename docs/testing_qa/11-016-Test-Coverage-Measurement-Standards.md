# Test Coverage & Measurement Standards

## Purpose
Defines how Ascend measures test coverage without allowing metrics to replace engineering judgment.

## Principles
Coverage measures exercised code, not correctness. Prioritize behavior with high user impact, security impact, complexity, change frequency, or failure cost.

## Coverage Types
Where useful, measure line, branch, function, statement, requirement, API/contract, and critical-journey coverage.

## Thresholds
Coverage thresholds may be used as signals or gates where justified, but must not encourage meaningless tests.

## Traceability
Important requirements should have corresponding validation evidence.

## Exclusions
Coverage exclusions must be justified. Do not exclude difficult code merely because it is inconvenient to test.

## AI
AI-generated code must not be merged merely because coverage increased. Tests must actually challenge the new behavior.

AI evaluation should cover normal, edge, adversarial, tool-use, retrieval, failure, and safety cases.

## Metrics
Useful metrics include defect escape rate, regression rate, test failure frequency, flakiness, diagnosis time, and critical-path coverage.

## Anti-Patterns
Avoid coverage-only release gates, unjustified exclusions, and tests written only to increase percentages.

# Next Document
**11-017 — Mutation Testing & Test Effectiveness**
