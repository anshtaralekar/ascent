---
title: Schema Design
document_id: 07-003
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Schema Design

> "The schema is the executable shape of the data model."

## Purpose

Defines the rules for translating Ascend's logical data model into concrete relational schemas.

## Philosophy

Schemas should be explicit, strongly constrained, readable, migration-friendly, and optimized for the actual domain rather than convenience during initial development.

## Schema Structure

Each table should have:

- Clear name
- Defined purpose
- Primary key
- Required constraints
- Explicit column types
- Appropriate nullability
- Relationship definitions
- Ownership metadata where applicable

## Naming

Use consistent naming for:

- Tables
- Columns
- Primary keys
- Foreign keys
- Indexes
- Constraints
- Join tables
- Enumerated values

Names should communicate domain meaning rather than implementation shortcuts.

## Data Types

Choose the narrowest practical type that correctly represents the domain.

Consider:

- Precision
- Range
- Nullability
- Sorting
- Comparison behavior
- Database portability

Do not use strings as a universal replacement for typed data.

## Nullability

A nullable field should have a defined semantic meaning.

Avoid nullable columns when absence and an explicit value can be represented more clearly through domain state.

## Primary Keys

Primary keys must:

- Be unique
- Be stable
- Have predictable indexing behavior
- Avoid encoding mutable business information

## Foreign Keys

Use foreign keys to enforce relationships where appropriate.

Every foreign key should define intended deletion and update behavior.

## Constraints

Use database constraints for invariants that must remain true regardless of application behavior.

Support:

- NOT NULL
- UNIQUE
- CHECK
- FOREIGN KEY
- PRIMARY KEY

Application validation should complement, not replace, database integrity constraints.

## Enumerations and States

Use explicit representations for domain states.

State values should be:

- Documented
- Version-controlled
- Validated
- Compatible with application logic

## JSON and Flexible Fields

Use JSON or semi-structured fields when the domain genuinely requires variable structure.

Do not use JSON to avoid designing a relational model for predictable structured data.

## Audit Metadata

Where required, include:

- Created timestamp
- Updated timestamp
- Actor identifier
- Source or origin metadata

Only include audit fields that support a defined operational or compliance requirement.

## Migration Compatibility

Schema changes must consider:

- Existing records
- Existing application versions
- Backward compatibility
- Migration duration
- Rollback or forward-fix strategy

Prefer additive changes before destructive changes in distributed deployments.

## Performance

Schema design should account for:

- Expected row volume
- Query patterns
- Relationship cardinality
- Write frequency
- Index requirements

## Governance

Schema changes require:

- Migration files
- Review
- Test coverage
- Compatibility assessment
- Production rollout strategy

## Anti-Patterns

Avoid:

- Unconstrained free-form columns
- Implicit relationships
- Inconsistent types for the same concept
- Destructive migrations without transition strategy
- Application-only integrity rules

## AI Context

AI coding agents should generate schemas from approved domain models and must include constraints, relationships, migrations, and compatibility considerations rather than producing tables in isolation.

# Next Document

**07-004 — Indexing & Query Design**
