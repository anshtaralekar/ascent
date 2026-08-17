---
title: Data Domain Boundaries
document_id: 07-032
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Data Domain Boundaries

## Purpose

Defines how Ascend separates data into coherent ownership domains so that persistence remains understandable and services do not create uncontrolled coupling.

## Philosophy

A data domain should represent a meaningful business boundary with clear ownership, lifecycle, access rules, and change authority.

## Domain Ownership

Each major data domain should identify:

- Business owner
- Technical owner
- Authoritative store
- Consuming services
- Security classification
- Retention policy

## Domain Examples

Depending on the final product model, domains may include:

- Identity
- Users
- Organizations or tenants
- Product configuration
- Content
- Conversations
- AI memory
- Knowledge
- Jobs
- Billing
- Audit
- Evaluation

These names are architectural examples and must be aligned with the actual approved product model.

## Boundary Rules

A domain should own its data and expose controlled interfaces to other domains.

Avoid direct cross-domain table manipulation by unrelated services.

## Cross-Domain Queries

Cross-domain reporting or workflows should use:

- Explicit service interfaces
- Read models
- Approved views
- Events
- Analytics projections

Choose based on consistency and performance requirements.

## Foreign Keys Across Domains

Cross-domain foreign keys may be appropriate when strict database-level integrity is essential, but they increase coupling and should be intentional.

## Domain Events

Use events when a domain needs to communicate state changes without exposing internal persistence structures.

Events should describe meaningful domain facts rather than raw table mutations.

## AI Data Domains

AI memory, knowledge, and retrieval artifacts should have explicit relationships to their source domains.

The AI layer must not become an uncontrolled duplicate of every product dataset.

## Tenant Boundaries

Tenant ownership must remain consistent across domains.

Cross-domain workflows must preserve tenant context.

## Lifecycle

Domain data should share a coherent lifecycle policy covering creation, modification, archival, and deletion.

## Governance

New persistent domains require architectural review when they introduce:

- New ownership boundaries
- New sensitive data
- New persistence technologies
- New cross-domain dependencies

## Anti-Patterns

Avoid:

- Shared "miscellaneous" tables
- Services writing directly into another domain's tables
- Circular ownership
- Unclear source of truth
- Cross-domain joins used as the default integration mechanism

## AI Context

AI coding agents must identify the owning domain before creating a persistent entity and should use the domain's existing data-access and integration patterns.

# Next Document

**07-033 — Database Security Threat Model**
