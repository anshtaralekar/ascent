---
title: Database Security & Privacy
document_id: 07-010
volume: 07
version: 1.0.0
status: Draft
owner: Security & Data Architecture Team
---

# Database Security & Privacy

> "The database contains the system's durable memory, so its security must assume persistent consequences."

## Purpose

Defines security and privacy controls for Ascend databases, data stores, backups, replicas, caches, and derived persistence systems.

## Philosophy

Database security must use defense in depth and least privilege, with privacy controls applied throughout the complete data lifecycle.

## Access Control

Use:

- Dedicated service identities
- Least-privilege roles
- Environment-specific credentials
- Administrative separation
- Short-lived credentials where practical

Applications should not share broad administrative database accounts.

## Network Security

Restrict database connectivity through:

- Private networks where appropriate
- Firewall rules
- Allowlists
- Service-level access controls
- Encrypted connections

Databases should not be unnecessarily exposed to public networks.

## Encryption

Protect sensitive data:

- In transit
- At rest
- In backups

Encryption-key management must be separated from ordinary application data access.

## Data Classification

Classify data according to sensitivity and required handling.

Classification should influence:

- Access
- Encryption
- Retention
- Logging
- Backup
- Export

## Row and Tenant Isolation

Where multi-tenancy exists, enforce tenant boundaries consistently at the data-access layer and, where appropriate, with database-level controls.

Never rely solely on a client-provided tenant identifier.

## Sensitive Fields

Protect sensitive fields through appropriate combinations of:

- Encryption
- Tokenization
- Restricted access
- Masking
- Redaction

Do not place sensitive values into ordinary logs or debugging output.

## Backups

Backups must be:

- Encrypted
- Access-controlled
- Monitored
- Tested for restoration
- Retained according to policy

A backup that cannot be restored is not a reliable backup.

## Auditing

Audit privileged and sensitive operations including:

- Administrative access
- Permission changes
- Schema changes
- Sensitive-data access
- Data exports
- Backup operations

## Data Retention

Define retention and deletion requirements for each relevant data class.

Deletion must account for:

- Primary records
- Replicas
- Caches
- Search indexes
- Vector stores
- Backups
- Derived data

## AI-Specific Privacy

AI memory, embeddings, retrieval indexes, and conversation-derived data may contain sensitive information and must inherit appropriate access and retention policies.

Do not assume that transforming data into embeddings removes its sensitivity.

## Monitoring

Detect:

- Unauthorized access
- Unusual query patterns
- Privilege escalation
- Large exports
- Failed authentication
- Suspicious administrative operations

## Governance

Require:

- Access reviews
- Credential rotation
- Security testing
- Backup restoration testing
- Data classification
- Incident procedures

## Anti-Patterns

Avoid:

- Publicly exposed databases without compelling justification
- Shared administrator credentials
- Secrets in source code
- Sensitive data in logs
- Uncontrolled production database access
- Assuming anonymization is automatic

## AI Context

AI coding agents must treat database access as privileged infrastructure, enforce least privilege, preserve tenant boundaries, and ensure sensitive data is not accidentally exposed through application code, logs, caches, backups, or AI context.

# Next Document

**07-011 — Backup, Recovery & Disaster Resilience**
