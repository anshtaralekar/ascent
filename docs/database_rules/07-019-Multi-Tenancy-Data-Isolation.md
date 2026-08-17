---
title: Multi-Tenancy & Data Isolation
document_id: 07-019
volume: 07
version: 1.0.0
status: Draft
owner: Data Architecture Team
---

# Multi-Tenancy & Data Isolation

## Purpose

Defines database architecture for isolating data belonging to different users, organizations, or tenants.

## Philosophy

Tenant isolation is a system-wide invariant, not a convention followed by individual frontend or API calls.

## Tenant Identity

Every tenant-scoped record must have an authoritative tenant relationship. Tenant identity must be derived from authenticated context rather than trusted from arbitrary client input.

## Isolation Models

Possible models include:

- Shared database and shared schema with tenant keys
- Shared database with isolated schemas
- Separate databases

The selected model must reflect scale, security, operational complexity, compliance, and cost.

## Shared Schema

Where tenant keys are used, all access paths must consistently scope queries by tenant. Database constraints and access-layer controls should reinforce the boundary.

## Authorization

Tenant filtering must occur server-side. Never rely on client-side filtering, hidden UI fields, user-provided tenant identifiers, or model-generated tenant assumptions.

## Cross-Tenant Operations

Cross-tenant access must be explicit and restricted to authorized administrative or system workflows.

## Indexing

Tenant-aware queries must be reflected in index design. Composite indexes may need tenant identity as part of the access pattern.

## AI Data Isolation

Tenant boundaries extend to embeddings, vector indexes, conversation memory, retrieval results, AI caches, evaluation data, and tool-generated records.

## Testing

Test cross-tenant reads and writes, enumeration attempts, missing tenant context, administrative exceptions, background jobs, caches, and AI retrieval.

## Monitoring

Detect unexpected cross-tenant access, missing tenant filters, authorization failures, and administrative overrides.

## Governance

Review isolation whenever new persistent entities, query paths, AI retrieval mechanisms, or administrative capabilities are introduced.

## Anti-Patterns

Avoid trusting tenant IDs from clients, relying solely on developer discipline, shared caches without tenant-aware keys, vector retrieval without tenant filters, and background jobs that lose tenant context.

## AI Context

AI coding agents must propagate tenant context through APIs, services, repositories, background jobs, caches, and AI retrieval systems.

# Next Document

**07-020 — Database Governance & Architecture Decision Records**
