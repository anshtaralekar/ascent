---
title: Data Lifecycle & Retention
document_id: 07-013
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Lifecycle & Retention

> "Data should have a lifecycle, not an indefinite lease on storage."

## Purpose

Defines how Ascend data is created, used, retained, archived, transformed, and eventually deleted.

## Philosophy

Every persistent data class should have an intentional lifecycle based on product value, operational requirements, security, privacy, and applicable retention obligations.

## Lifecycle

A typical lifecycle is:

**Create → Active → Historical → Archive → Delete**

Not every data class requires every stage.

## Data Classification

For each data class define:

- Purpose
- Owner
- Sensitivity
- Retention requirement
- Storage location
- Archive policy
- Deletion policy

## Retention

Retention periods should be based on actual requirements rather than indefinite preservation.

Different data classes may require different retention periods.

## Archival

Archive data when:

- It remains historically valuable
- Active query performance would benefit
- Regulatory or business requirements require preservation

Archived data should remain discoverable according to its access policy.

## Deletion

Deletion must account for all representations:

- Primary records
- Replicas
- Caches
- Search indexes
- Vector stores
- Derived records
- Exported copies
- Backups where applicable

## Soft Delete

Use soft deletion only when there is a defined need for recovery, history, authorization, or compliance.

Soft-deleted data must not accidentally remain visible to ordinary application queries.

## AI Data Lifecycle

AI-specific data may include:

- Conversations
- Memory
- Embeddings
- Retrieval indexes
- Feedback
- Evaluation records
- Generated artifacts

Each must have an explicit retention and deletion strategy.

## Data Minimization

Store only what is necessary for:

- Product functionality
- Security
- Operations
- Analytics
- Approved AI capabilities

Avoid retaining information merely because storage is inexpensive.

## Lifecycle Automation

Automate lifecycle actions where safe:

- Archival
- Expiration
- Purging
- Index cleanup
- Cache invalidation

Automation must be observable and recoverable where deletion is consequential.

## Monitoring

Track:

- Storage growth
- Retention compliance
- Archive volume
- Deletion success
- Failed lifecycle jobs
- Data classes without defined retention

## Governance

Every major data class should have:

- Data owner
- Retention policy
- Deletion mechanism
- Review cadence

## Anti-Patterns

Avoid:

- Infinite retention by default
- Deleting only the primary record
- Hidden copies in derived systems
- Unbounded AI conversation storage
- Lifecycle jobs without monitoring

## AI Context

AI coding agents should define lifecycle behavior whenever they introduce a new persistent entity or derived data store and must account for all copies and representations of that data.

# Next Document

**07-014 — Audit & Data Lineage**
