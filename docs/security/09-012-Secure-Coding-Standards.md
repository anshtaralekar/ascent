---
title: Secure Coding Standards
document_id: 09-012
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Secure Coding Standards

## Purpose

Defines implementation-level practices that reduce common application vulnerabilities.

## General Rule

Prefer established, reviewed project utilities and framework protections over custom security mechanisms.

## Input Validation

Validate all externally influenced input at the server boundary.

Use allowlists where the domain permits them.

## Database Access

Use parameterized queries, approved repositories, and safe ORM/query-builder patterns.

Never concatenate untrusted input into executable database queries.

## Command Execution

Avoid shell execution when an API or library can perform the required operation.

If command execution is unavoidable:

- Restrict executable
- Validate arguments
- Avoid shell interpretation
- Apply least privilege
- Audit sensitive operations

## Output Handling

Use context-appropriate encoding and safe rendering.

Do not assume escaped input is safe in a different output context.

## Authentication

Use the project's approved authentication mechanisms.

Do not manually parse or validate security tokens when an approved library exists.

## Authorization

Perform authorization at the resource/action boundary.

Do not infer permission from UI visibility.

## File Handling

Treat filenames, MIME types, paths, and file content as untrusted.

Prevent:

- Path traversal
- Unauthorized file access
- Arbitrary overwrite
- Excessive file sizes

## URL Handling

User-controlled URLs require SSRF-aware validation.

Restrict:

- Protocols
- Destinations
- Redirect behavior
- Internal network access

## Serialization

Validate structured data before deserialization where unsafe formats could permit code execution or unexpected object construction.

## Error Handling

Return safe, stable errors.

Log enough information for diagnosis without exposing secrets or sensitive data.

## Logging

Never log:

- Passwords
- Authentication tokens
- Private keys
- Secret headers
- Sensitive payloads by default

## Randomness

Use cryptographically secure randomness for security-sensitive tokens, identifiers, and secrets.

## Cryptography

Use approved cryptographic libraries and established primitives.

Never invent algorithms.

## Concurrency

Security-sensitive state changes should account for race conditions and atomicity.

## AI-Generated Code

AI-generated code must undergo the same security review and automated checks as manually written code.

## Anti-Patterns

Never:

- Trust client validation
- Build SQL with string concatenation
- Execute arbitrary shell commands
- Store passwords in plaintext
- Generate custom cryptography
- Assume model output is trusted

## AI Context

AI coding agents must use secure coding patterns already present in the repository and should stop or flag uncertainty when a security-sensitive implementation is ambiguous.

# Next Document

**09-013 — Dependency & Supply-Chain Security**
