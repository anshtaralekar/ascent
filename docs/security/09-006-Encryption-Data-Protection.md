---
title: Encryption & Data Protection
document_id: 09-006
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Encryption & Data Protection

## Purpose

Defines how sensitive data is protected during transmission, storage, processing, backup, and controlled sharing.

## Philosophy

Encryption reduces the impact of unauthorized access, but it does not replace authentication, authorization, tenant isolation, secure key management, or data minimization.

## Data in Transit

Sensitive communication must use approved encrypted transport.

This applies to:

- Client → API
- Service → service
- Service → database where applicable
- Service → external provider
- Worker → queue/storage
- Administrative connections

Unencrypted transport must not be used for production-sensitive traffic unless an explicitly documented exception exists.

## Data at Rest

Sensitive persistent data should use approved encryption mechanisms provided by the storage platform or security architecture.

Consider:

- Databases
- Object storage
- Backups
- Logs
- Search indexes
- Vector stores
- Queues
- Temporary storage

## Key Management

Encryption keys must be managed separately from encrypted data where the architecture requires it.

Key management must define:

- Ownership
- Access
- Rotation
- Revocation
- Recovery
- Auditability

## Application-Level Encryption

Use application-level encryption only where the threat model or data classification justifies it.

Avoid implementing custom cryptography.

Use established, reviewed cryptographic libraries and primitives.

## Password Protection

Passwords must use an approved password-hashing mechanism designed for password storage.

Encryption must not be used as a substitute for password hashing.

## Token Protection

Authentication and recovery tokens must be protected according to their sensitivity and lifecycle.

## Backups

Backups must receive protection appropriate to the source data.

A secure production database with unprotected backups is not a secure data architecture.

## AI Data

Sensitive AI inputs, conversation data, retrieval content, and generated artifacts must follow the same data-protection requirements as other application data.

Do not assume AI data is harmless because it is processed by a model.

## External Providers

Before transmitting protected data to a third party, verify:

- Required protection
- Provider trust boundary
- Purpose
- Retention
- Access controls

## Data Minimization

Encryption does not justify retaining data that the product does not need.

## Anti-Patterns

Never:

- Implement custom encryption algorithms.
- Store encryption keys beside protected data without justification.
- Disable TLS to simplify debugging in production.
- Assume encrypted storage removes the need for authorization.
- Leave backups outside the protection model.

## AI Context

AI coding agents must use approved cryptographic mechanisms and key-management systems and must never invent custom encryption schemes.

# Next Document

**09-007 — Network Security**
