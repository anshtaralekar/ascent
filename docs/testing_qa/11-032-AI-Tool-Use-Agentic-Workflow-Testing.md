# AI Tool-Use & Agentic Workflow Testing

## Purpose
Defines validation of AI systems capable of invoking tools, APIs, retrieval systems, workflows, or side-effecting capabilities.

## Principle
Agentic testing must validate both decision quality and deterministic control boundaries.

## Tool Selection
Evaluate correct tool selection, unnecessary tool avoidance, unavailable-tool handling, and prevention of invented capabilities.

## Arguments
Validate required fields, types, allowed values, resource identifiers, size limits, and dangerous combinations. Application code validates arguments independently of the model.

## Authorization
Test allowed actions, denied actions, cross-tenant attempts, privilege escalation, stale authorization, and revoked access.

## Side Effects
For mutations, test confirmation requirements, idempotency, duplicate invocation, partial failure, retries, and audit trails.

## Multi-Step Workflows
Evaluate planning, sequencing, state progression, failure recovery, loop termination, and context preservation.

## Bounds
Limit iterations, tool calls, runtime, tokens, and cost.

## Tool Failure
Test timeout, invalid response, permission denial, rate limits, partial success, and dependency outage.

## Untrusted Output
Tool results are untrusted data and must not automatically become instructions.

## Destructive Tools
Use deterministic controls, authorization, and safe simulations or sandboxes where real execution is inappropriate.

## Anti-Patterns
Avoid model-only authorization, unlimited loops, trusted-by-default tool output, and production side effects in ordinary CI.

# Next Document
**11-033 — Retrieval-Augmented Generation Testing**
