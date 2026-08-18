# AI Safety & Adversarial Evaluation

## Purpose
Defines how Ascend evaluates AI features against adversarial, manipulative, unsafe, and boundary-seeking inputs.

## Principle
AI systems must be tested against users and external content that do not cooperate with intended application behavior.

## Evaluation Areas
Test direct and indirect prompt injection, instruction conflicts, tool abuse, data-exfiltration attempts, cross-user or cross-tenant access, unsafe actions, resource exhaustion, obfuscation, and multi-turn manipulation.

## Trust Boundaries
Treat user input, retrieved documents, web content, tool output, external-provider output, and model-generated instructions as untrusted.

## Tool Authorization
Model persuasion must never broaden tool permissions. Authorization remains enforced by deterministic application controls.

## Retrieval Attacks
Test documents containing instructions intended to override the system. Retrieved content is data, not authority.

## Data Leakage
Evaluate attempts to obtain other users' data, hidden context, internal instructions, secrets, credentials, or restricted documents.

## Multi-Turn and Obfuscation
Test gradual manipulation, encoding, misspellings, role-play framing, translation, nested instructions, and indirect requests.

## Resource Abuse
Test attempts to trigger excessive tokens, tool calls, expensive providers, recursive workflows, or oversized retrieval.

## Evidence
Record scenario, expected boundary, actual behavior, severity, reproducibility, model/provider, and application configuration.

## Regression
Confirmed failures become part of the adversarial regression dataset.

## Anti-Patterns
Do not rely only on provider filters, obvious attacks, or a model-based evaluator as the sole authority for deterministic access control.

# Next Document
**11-032 — Prompt, Retrieval & Tool-Use Testing**
