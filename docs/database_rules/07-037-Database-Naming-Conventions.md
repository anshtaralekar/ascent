---
title: Database Naming & Convention Standards
document_id: 07-037
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Naming & Convention Standards

## Purpose

Defines consistent naming and structural conventions for Ascend databases so schemas remain readable, searchable, and maintainable.

## Philosophy

Names are part of the architecture. They should communicate domain meaning without forcing developers to inspect implementation details.

## Tables

Table names should:

- Represent domain concepts
- Follow one consistent casing convention
- Avoid unexplained abbreviations
- Avoid implementation-specific names

## Columns

Column names should:

- Be semantically precise
- Use consistent timestamp terminology
- Distinguish identifiers from human-readable values
- Avoid ambiguous names such as `data`, `value`, or `type` when a domain-specific name exists

## Identifiers

Use consistent conventions for:

- Primary keys
- Foreign keys
- External identifiers
- Tenant identifiers
- Version identifiers

## Timestamps

Use consistent semantics for:

- Creation time
- Update time
- Deletion/archive time
- Effective time

Timestamp meaning must be documented when it is not obvious.

## Boolean Fields

Boolean names should clearly communicate state, such as:

- `is_active`
- `has_access`

Avoid double-negative semantics.

## Indexes

Index names should communicate:

- Table
- Indexed fields
- Purpose where useful

## Constraints

Constraint names should be deterministic and recognizable for operational debugging and migration management.

## Enums and States

Use consistent state naming and avoid mixing synonyms for the same domain state.

## Metadata

Standard metadata fields should be used consistently where the architecture requires them.

## AI Data

Embedding, vector, memory, and retrieval metadata must follow the same naming discipline as transactional data.

## Governance

Naming conventions apply to:

- Schemas
- Tables
- Columns
- Indexes
- Constraints
- Migrations
- Data-access methods

## Anti-Patterns

Avoid:

- Random casing
- Cryptic abbreviations
- Different names for the same concept
- Generic column names
- Naming based on temporary implementation details

## AI Context

AI coding agents must inspect existing naming conventions before generating schema or migration code and must follow repository conventions instead of inventing local alternatives.

# Next Document

**07-038 — Database Configuration & Environment Management**
