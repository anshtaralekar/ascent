---
title: Application Security
document_id: 09-008
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Application Security

## Purpose

Defines secure application-development requirements for preventing vulnerabilities in business logic, input handling, dependencies, sessions, files, and runtime behavior.

## Philosophy

Application security belongs in design and implementation, not only in penetration testing.

## Input Is Untrusted

Treat all externally influenced data as untrusted, including:

- HTTP parameters
- JSON
- Files
- Headers
- URLs
- Webhook payloads
- Search queries
- AI-generated tool arguments
- Imported data

## Validation

Validate inputs according to the expected domain schema.

Validation should include:

- Type
- Length
- Range
- Format
- Allowed values
- Relationship constraints

## Output Encoding

Encode or safely render data according to its output context.

Never assume that validated input is automatically safe in every output context.

## Injection Prevention

Use safe abstractions for:

- SQL
- Shell commands
- HTML
- Templates
- Search/query systems
- External service requests

Do not construct executable queries from raw user input.

## File Security

File uploads must address:

- Size
- Type
- Content
- Storage location
- Authorization
- Malware/security scanning where required

## Session Security

Sessions must use secure lifecycle and storage controls.

Protect against:

- Session theft
- Fixation
- Unauthorized reuse
- Improper expiration

## Error Handling

Production errors must not expose:

- Stack traces
- Credentials
- Internal network details
- Database queries
- Sensitive resource information

## Dependency Security

Dependencies must be:

- Tracked
- Updated
- Assessed for known vulnerabilities
- Obtained from trusted sources

## Supply Chain

Build systems should verify dependency provenance and integrity where practical.

## Business Logic Security

Security vulnerabilities can exist even when inputs are technically valid.

Test for:

- Unauthorized state transitions
- Workflow bypass
- Race conditions
- Excessive privileges
- Duplicate actions

## AI Application Security

AI-generated content must not automatically execute privileged behavior.

Treat:

- Prompts
- Retrieved documents
- Tool arguments
- Model outputs

as untrusted unless independently validated.

## Secure Coding

Developers and AI coding agents should reuse approved security utilities rather than creating custom authentication, cryptography, or authorization logic.

## Security Testing

Use appropriate:

- Static analysis
- Dependency scanning
- Dynamic testing
- Integration tests
- Authorization tests
- Penetration testing where required

## Anti-Patterns

Never:

- Trust client-side validation.
- Execute raw user input.
- Return production stack traces.
- Add custom cryptography.
- Allow model output to bypass deterministic controls.

## AI Context

AI coding agents must follow secure coding patterns already established in the repository and must flag security-sensitive shortcuts instead of silently implementing them.

# Next Document

**09-009 — API Security Controls**
