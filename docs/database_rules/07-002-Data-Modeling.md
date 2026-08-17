---
title: Data Modeling
document_id: 07-002
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Modeling

> "Good data models make the domain visible in the structure of the system."

## Purpose

Defines how Ascend's real-world concepts, business entities, relationships, and lifecycle states are represented as persistent data.

## Philosophy

Models should represent the domain clearly, minimize unnecessary duplication, preserve integrity, and remain flexible enough to evolve without creating ambiguous ownership.

## Modeling Layers

Use three conceptual layers:

1. Domain model
2. Logical data model
3. Physical database model

The domain model describes business concepts. The logical model defines entities and relationships. The physical model defines tables, columns, indexes, constraints, and database-specific implementation.

## Entity Design

Every persistent entity should define:

- Stable identifier
- Business meaning
- Ownership
- Lifecycle
- Required attributes
- Optional attributes
- Relationships
- Creation metadata
- Update metadata where applicable

## Identifiers

Prefer stable, non-semantic identifiers for primary keys unless a domain requirement explicitly requires otherwise.

Identifiers should not encode mutable business meaning.

## Relationships

Represent relationships explicitly:

- One-to-one
- One-to-many
- Many-to-many
- Hierarchical relationships

Many-to-many relationships should normally use an explicit association entity when additional attributes or lifecycle information are required.

## Normalization

Normalize transactional data sufficiently to:

- Reduce update anomalies
- Preserve consistency
- Clarify ownership
- Avoid unnecessary duplication

Controlled denormalization may be introduced when supported by measured workload requirements.

## Lifecycle Modeling

Entities with meaningful state transitions should define explicit states rather than relying on loosely interpreted flags.

State transitions should be compatible with application-level business rules.

## Temporal Data

Where history matters, define:

- Created timestamp
- Updated timestamp
- Effective periods where required
- Deletion/archive semantics

Do not add timestamps mechanically when they have no meaningful operational purpose.

## Soft Deletion

Use soft deletion only when the product requires:

- Recovery
- Historical visibility
- Regulatory retention
- Referential preservation

Otherwise, prefer explicit lifecycle or archival strategies.

## Data Ownership

Every field should have a clear conceptual owner.

Avoid storing the same business fact in multiple entities unless the duplication is explicitly derived and maintained.

## Derived Data

Derived fields should document:

- Source fields
- Calculation rules
- Refresh strategy
- Consistency expectations

## Multi-Tenant Data

If Ascend supports multiple tenants, tenant ownership must be represented consistently and enforced throughout the data-access layer.

## Data Classification

Classify sensitive information according to the security model before determining:

- Storage
- Encryption
- Retention
- Access
- Logging behavior

## Governance

Data models require review when changes affect:

- Core entities
- Relationships
- Identity
- Permissions
- Billing
- Audit history
- AI memory or knowledge

## Anti-Patterns

Avoid:

- Generic "data" tables with unclear semantics
- Business meaning hidden inside column names
- Duplicate sources of truth
- Excessive JSON blobs for structured relational data
- Flags that represent undocumented state machines

## AI Context

AI coding agents should begin database work from the domain model, explicitly identify entity ownership and relationships, and only then generate physical schemas.

# Next Document

**07-003 — Schema Design**
