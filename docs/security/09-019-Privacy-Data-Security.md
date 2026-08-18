---
title: Privacy & Data Security
document_id: 09-019
volume: 09
version: 1.0.0
status: Draft
owner: Security & Privacy Architecture Team
---

# Privacy & Data Security

## Purpose

Defines security principles for collecting, processing, storing, sharing, retaining, and deleting data that may identify or affect individuals or organizations.

## Philosophy

The safest sensitive data is data the system does not unnecessarily collect or retain.

## Data Classification

Classify information according to project-approved categories such as:

- Public
- Internal
- Confidential
- Sensitive
- Highly restricted

The actual classification taxonomy must be defined by the product's governing requirements.

## Data Minimization

Collect only what is required for:

- Product functionality
- Security
- Legal/operational requirements
- Explicitly approved analytics

## Purpose Limitation

Do not reuse sensitive data for unrelated purposes merely because it is technically available.

## Access

Sensitive data must be accessible only to identities and workflows with a legitimate requirement.

## Tenant Isolation

Tenant boundaries apply to:

- Primary data
- Search
- Caches
- Files
- Logs
- Analytics
- AI retrieval
- Derived data

## Retention

Every sensitive data category should have an intentional lifecycle.

Avoid indefinite retention by default.

## Deletion

Deletion must consider:

- Primary records
- Backups
- Derived stores
- Search indexes
- Caches
- AI memory
- External providers

The actual deletion guarantee must match the architecture and applicable requirements.

## Export

Sensitive exports require authorization and appropriate controls.

Large exports should be bounded, auditable, and protected.

## AI Data Protection

Before sending sensitive information to an AI provider or model, determine:

- What data is required
- Who receives it
- How it is protected
- How long it is retained
- Whether it is used for another purpose

## Logging

Avoid putting unnecessary personal or confidential data into logs.

## Analytics

Analytics pipelines should use minimized and appropriately protected data.

## Privacy by Design

Privacy requirements should influence architecture before implementation rather than being added after data collection is established.

## Security vs Privacy

Security controls protect data from unauthorized access.

Privacy controls also address whether the data should be collected, used, retained, or shared in the first place.

Both are required.

## Incident Handling

Data-security incidents must be assessed for:

- Scope
- Data categories
- Affected parties
- Exposure duration
- Required response

## Anti-Patterns

Avoid:

- Collecting data because it may be useful later
- Storing sensitive data in logs
- Returning unnecessary fields from APIs
- Using production personal data in development
- Sending sensitive context to external AI providers without an approved boundary

## AI Context

AI coding agents must minimize sensitive data exposure and must inspect data-classification and privacy rules before introducing storage, logging, analytics, retrieval, or external AI processing.

# Next Document

**09-020 — Security Governance & Policy Enforcement**
