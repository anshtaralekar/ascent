---
title: Database Testing
document_id: 07-017
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Database Testing

## Purpose

Defines testing requirements for schemas, migrations, queries, transactions, integrity rules, performance, and recovery.

## Philosophy

Database testing must verify both correctness and operational behavior.

## Test Layers

Use:

- Unit tests for data-related logic
- Integration tests against the actual database technology
- Migration tests
- Transaction and concurrency tests
- Constraint tests
- Performance tests
- Recovery tests

## Schema Testing

Verify tables, columns, types, nullability, constraints, relationships, and indexes.

## Migration Testing

Test against empty schemas, representative existing data, large-data estimates where relevant, and compatible application versions.

## Query Testing

Verify correctness of filtering, sorting, pagination, authorization scope, and boundary conditions.

## Transaction Testing

Test commit, rollback, concurrent updates, deadlocks, retries, and idempotency.

## Integrity Testing

Explicitly test unique constraints, foreign keys, state invariants, invalid transitions, and concurrent writes.

## Performance Testing

Measure query latency, throughput, connection behavior, large-dataset behavior, and index effectiveness using realistic data distributions.

## Recovery Testing

Verify backup restoration, point-in-time recovery where applicable, replica recovery, application reconnection, and data integrity after restoration.

## Test Data

Use synthetic or appropriately sanitized data. Production data must not be copied into test environments without approved controls.

## Governance

Database changes are incomplete until required test evidence exists.

## Anti-Patterns

Avoid testing only ORM mocks, testing migrations only on empty databases, ignoring concurrency, using unrealistic datasets, and skipping recovery tests.

## AI Context

AI coding agents should generate database tests alongside schema and persistence changes and use real integration tests for behavior mocks cannot accurately represent.

# Next Document

**07-018 — Database Deployment & Release**
