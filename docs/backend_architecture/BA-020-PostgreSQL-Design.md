---
title: PostgreSQL Design
document_id: BA-020
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# PostgreSQL Design

> "Schemas should remain consistent, normalized, and prepared for growth."

## Purpose

Defines the PostgreSQL schema design standards for Ascend.

---

## Philosophy

Design relational data for integrity, maintainability, and efficient querying while supporting future scalability.

---

## Schema Organization

Organize tables by business domain.

Separate operational tables from migration metadata and system administration objects.

---

## Naming Conventions

- snake_case
- Singular table names where appropriate
- Descriptive column names
- Consistent foreign key naming

---

## Primary Keys

Use UUIDs for primary identifiers.

Avoid exposing sequential identifiers externally.

---

## Relationships

Support:

- One-to-One
- One-to-Many
- Many-to-Many

Enforce referential integrity with foreign keys.

---

## Constraints

Use:

- Primary Keys
- Foreign Keys
- Unique Constraints
- Check Constraints
- NOT NULL where appropriate

---

## Audit Columns

Every major table should include:

- created_at
- updated_at
- deleted_at (soft delete where applicable)
- created_by
- updated_by

---

## Multi-Tenancy

Associate tenant-owned data with a tenant identifier and enforce isolation consistently.

---

## Scalability

Design for:

- Index-friendly schemas
- Future partitioning
- Read replicas
- Efficient joins

---

## Anti-Patterns

Avoid:

- Unbounded JSON columns
- Missing constraints
- Duplicate data
- Excessive denormalization

---

## AI Context

AI coding agents should generate PostgreSQL schemas using these standards before implementing Prisma models or migrations.

---

# Next Document

**BA-021 — Prisma ORM**
