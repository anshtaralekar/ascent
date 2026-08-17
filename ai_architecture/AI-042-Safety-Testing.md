---
title: Safety Testing
document_id: AI-042
volume: 06
version: 1.0.0
status: Draft
owner: AI Architecture Team
---

# Safety Testing

> "Safety claims require adversarial evidence."

## Purpose

Defines testing methods for discovering unsafe AI behavior before and after deployment.

## Philosophy

Safety testing should challenge systems under normal, ambiguous, adversarial, and failure conditions.

## Test Categories

Include:

- Policy tests
- Adversarial tests
- Prompt injection tests
- Tool abuse tests
- Privacy tests
- Data leakage tests
- Failure recovery tests

## Test Lifecycle

1. Define safety objective
2. Identify threats
3. Build test cases
4. Execute tests
5. Classify failures
6. Remediate
7. Re-test
8. Monitor production

## Adversarial Testing

Test resistance to:

- Instruction manipulation
- Malicious context
- Unauthorized actions
- Sensitive data requests
- Tool misuse
- Boundary-condition abuse

## Metrics

Measure:

- Violation rate
- Attack success rate
- False refusal rate
- Detection rate
- Recovery effectiveness

## Regression Testing

Maintain safety suites across:

- Model versions
- Prompt versions
- Tool versions
- Policy changes
- Agent updates

## Red Teaming

Use controlled adversarial exercises to identify unexpected behaviors and systemic weaknesses.

## Governance

Require:

- Documented test cases
- Severity classification
- Remediation ownership
- Release gates
- Audit records

## Anti-Patterns

Avoid:

- Testing only expected user behavior
- Removing difficult tests after failures
- Treating safety as binary
- Shipping after unresolved critical findings

## AI Context

AI coding agents should run safety and adversarial tests whenever changes can affect model behavior, autonomy, tools, data, or policy enforcement.

# Next Document

**AI-043 — Human Oversight**
