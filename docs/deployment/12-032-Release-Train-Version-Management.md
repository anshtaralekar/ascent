# Release Train & Version Management

## Purpose

Defines how Ascend organizes releases, versions, release candidates, and production promotion.

## Principle

Version identity should communicate what is being released and preserve traceability.

## Versioning

Use the project's approved versioning strategy consistently.

Version identifiers should map clearly to source and artifacts.

## Release Candidate

A release candidate is a specific artifact/configuration combination undergoing final validation.

Do not silently change it after validation.

## Release Train

Where multiple changes are released together, define:

- Included changes
- Excluded changes
- Dependencies
- Validation state
- Release owner

## Independent Releases

Where architecture permits, independently deployable components may follow separate release schedules.

Their compatibility contracts remain mandatory.

## Hotfixes

Hotfixes should have:

- Narrow scope
- Clear justification
- Appropriate validation
- Traceable artifact
- Recovery plan

## AI Versions

Material AI changes may require versioning of:

- Model
- Prompt/configuration
- Evaluation dataset
- Tool definitions
- Retrieval configuration

## Version Compatibility

Maintain compatibility information for:

- APIs
- Database schema
- Events/messages
- Frontend/backend
- Worker versions

## Release Notes

Material releases should document user-visible or operationally relevant changes.

## Retention

Maintain enough historical release information to support rollback, incident analysis, and compliance requirements.

## Anti-Patterns

Avoid mutable release identifiers, rebuilding release candidates after approval, undocumented hotfixes, and versioning code without versioning material AI configuration.

# Next Document

**12-033 — Deployment Dependency & Compatibility Management**
