# Test Levels & Validation Boundaries

## Purpose
Defines the responsibility of each validation layer and prevents gaps or unnecessary duplication.

## Static Validation
Formatting, linting, typing, schema validation, IaC validation, dependency analysis, and security policy checks.

## Unit Boundary
Isolated deterministic logic with controlled dependencies.

## Component Boundary
Observable behavior within a meaningful application component.

## Integration Boundary
Real interactions between system components, such as application/database, service/authentication, worker/storage, and application/queue.

## Contract Boundary
Compatibility between API or service consumers and providers.

## E2E Boundary
Complete user-visible workflows across the actual application stack.

## Infrastructure Boundary
IaC, policy, deployment, environment configuration, runtime health, and scaling. These inherit Volume 10.

## Security Boundary
Authentication, authorization, tenant isolation, validation, secrets, and security-sensitive configuration. Volume 09 remains authoritative.

## Database Boundary
Constraints, migrations, transactions, queries, and integrity defined by Volume 07.

## API Boundary
Contracts defined by Volume 08.

## AI Boundary
AI evaluation covers output quality, instruction adherence, tool selection, retrieval relevance, and safety behavior where deterministic tests are insufficient.

## Boundary Rule
Use the lowest test level capable of reliably answering the question. Move upward only when lower-level validation cannot establish the required behavior.

# Next Document
**11-004 — Test Environment Architecture**
