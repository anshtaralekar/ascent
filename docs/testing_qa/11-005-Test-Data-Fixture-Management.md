# Test Data & Fixture Management

## Purpose
Defines management of test data, fixtures, factories, seeds, performance datasets, security payloads, and AI evaluation datasets.

## Principle
Test data is part of the test architecture. Poor data creates false confidence and hidden coverage gaps.

## Categories
Unit data, component fixtures, integration seeds, E2E scenarios, performance datasets, security payloads, and AI evaluation datasets.

## Synthetic Data
Prefer synthetic data for general testing. Never include real credentials or unnecessary personal data.

## Factories
Use factories for controlled variation. Important fields should be explicit rather than hidden behind magical defaults.

## Fixtures
Keep stable reusable fixtures small and understandable.

## Edge Cases
Cover empty, boundary, invalid, duplicate, Unicode, timezone, concurrency, and permission-sensitive cases where relevant.

## Multi-Tenant Systems
Include multiple tenants and explicitly test isolation.

## Authorization Data
Represent authorized, unauthorized, partial-permission, ownership, and cross-tenant scenarios.

## AI Evaluation Data
Include normal, ambiguous, adversarial, tool-use, retrieval, failure, and safety-boundary cases. Version evaluation datasets so changes can be compared.

## Determinism
Control random seeds when reproducibility matters.

## Performance Data
Use realistic scale and distributions, not only tiny development fixtures.

## AI-Generated Fixtures
Review generated data for validity, edge-case coverage, privacy, security relevance, and reproducibility.

## Anti-Patterns
Never copy production databases into ordinary CI, embed credentials in fixtures, use one universal fixture for every test, or build AI evaluation sets containing only easy examples.

# Volume 11 Progress
**11-001 through 11-005 complete.**

# Next Document
**11-006 — Unit Testing Standards**
