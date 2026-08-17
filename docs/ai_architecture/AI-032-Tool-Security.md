---
title: Tool Security
document_id: AI-032
volume: 06
version: 1.0.0
status: Draft
owner: AI Architecture Team
---

# Tool Security

> "A tool with power must also have boundaries."

## Purpose

Defines security controls for tools that expose data, services, APIs, files, or external side effects to AI agents.

## Philosophy

Tools must operate under least privilege, explicit authorization, strong validation, and complete auditability.

## Security Lifecycle

1. Authenticate caller
2. Authorize capability
3. Validate arguments
4. Enforce policy
5. Execute within limits
6. Validate result
7. Audit action

## Access Control

Support:

- Identity-based authorization
- Role-based permissions
- Capability-scoped access
- Tenant isolation
- Least privilege

## Input Security

Protect against:

- Malformed arguments
- Injection attacks
- Path traversal
- Unauthorized targets
- Resource exhaustion

## Side-Effect Controls

Require additional safeguards for:

- Sending communications
- Modifying data
- Financial actions
- External system changes
- Destructive operations

## Secret Protection

Never expose secrets unnecessarily to models, prompts, logs, or tool outputs.

## Monitoring

Track:

- Authorization failures
- Suspicious invocations
- Sensitive operations
- Policy violations
- Security incidents

## Governance

Require:

- Security reviews
- Tool ownership
- Audit trails
- Permission versioning
- Incident response procedures

## Anti-Patterns

Avoid:

- Root-level tool access
- Shared credentials
- Unrestricted external requests
- Logging sensitive arguments

## AI Context

AI coding agents should treat every tool as an explicit security boundary and apply least privilege before execution.

# Next Document

**AI-033 — Tool Evaluation**
