# Database & Migration Testing

## Purpose

Defines how Ascend validates database behavior, schema changes, migrations, integrity, and compatibility.

## Authority

Volume 07 remains authoritative for database architecture and rules.

## Migration Principle

A database migration is a production change and must be tested as such.

## Migration Validation

Test:

- Fresh installation
- Upgrade from supported previous versions
- Data transformation
- Constraints
- Indexes
- Defaults
- Backward compatibility
- Roll-forward behavior

## Data Integrity

Verify:

- Required relationships
- Uniqueness
- Referential integrity
- Domain constraints
- Expected row counts
- Critical invariants

## Application Compatibility

During staged deployment, ensure old and new application versions behave safely with the transitional schema.

## Destructive Changes

Dropping columns, tables, indexes, or data requires explicit validation and recovery planning.

Prefer staged migrations where practical.

## Performance

Test migration duration, locking, resource consumption, and impact on application traffic.

## Large Datasets

A migration that works on a tiny development database may fail at production scale.

Use representative datasets for high-risk migrations.

## Rollback

Determine whether rollback is safe.

For irreversible data transformations, use forward recovery rather than pretending a rollback exists.

## Backup

Verify an appropriate recovery point exists before high-risk migrations.

## CI

Migration validation should be automated where practical.

## AI-Generated Migrations

AI-generated migrations require especially careful review because generated SQL can be syntactically valid while being operationally unsafe.

## Anti-Patterns

Avoid testing migrations only on empty databases, destructive changes without recovery planning, and treating successful SQL execution as proof of data correctness.

# Volume 11 Progress

**11-001 through 11-025 complete.**

# Next Document

**11-026 — API & Integration Validation**
