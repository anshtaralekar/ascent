---
title: Security Data Classification & Handling Standard
document_id: 09-026
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Security Data Classification & Handling Standard

## Purpose

Defines how Ascend data is classified and how handling requirements change according to sensitivity.

## Principle

Data classification determines the minimum controls required for storage, processing, transmission, logging, export, and deletion.

## Classification Levels

The product should use an explicit classification taxonomy. Unless a later governing standard defines a different taxonomy, use:

### Public

Information intentionally available to the public.

### Internal

Information intended for authorized users and ordinary internal operation.

### Confidential

Business or operational information whose unauthorized disclosure could cause meaningful harm.

### Sensitive

Information requiring stronger access, protection, retention, and monitoring controls.

### Highly Restricted

Information whose compromise could create severe security, privacy, financial, or operational impact.

## Handling Rules

Higher classifications require progressively stronger controls for:

- Access
- Encryption
- Logging
- Export
- Retention
- External sharing
- Backup
- AI processing

## Data Discovery

Before introducing a new data field or storage location, determine its classification.

Do not classify data only after implementation.

## API Handling

APIs should expose only fields required by the consumer.

Sensitive fields must have explicit authorization requirements.

## Database Handling

Follow Volume 07 data ownership, access, encryption, backup, and retention rules.

## Logging

Highly restricted and sensitive data should not appear in logs unless explicitly required and appropriately protected.

## Analytics

Use minimized or appropriately transformed data where possible.

## AI Handling

Before placing classified information into an AI context, determine:

- Whether the model is authorized to receive it
- Whether the provider is approved
- Whether retention is acceptable
- Whether the data can appear in generated output
- Whether retrieval permissions are preserved

## Export

Exports of sensitive data require explicit authorization and appropriate auditability.

## Development Data

Do not use production sensitive data in development or testing unless explicitly approved and protected.

Prefer synthetic or appropriately de-identified data.

## Retention

Classification should influence retention decisions.

Higher sensitivity generally requires greater justification for long-term retention.

## Deletion

Deletion requirements must propagate to derived systems such as:

- Search
- Caches
- Analytics
- AI memory
- Object storage

## Misclassification

If data is discovered to have been under-classified:

1. Restrict exposure.
2. Correct classification.
3. Review existing access.
4. Assess whether prior exposure occurred.
5. Apply required remediation.

## AI Context

AI coding agents must determine the classification of new sensitive data before selecting storage, logging, API exposure, retrieval, or AI-processing patterns.

# Next Document

**09-027 — Security Identity Lifecycle & Privileged Access**
