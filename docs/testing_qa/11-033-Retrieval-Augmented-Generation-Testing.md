# Retrieval-Augmented Generation Testing

## Purpose
Defines validation of retrieval-augmented generation across retrieval, context construction, generation, grounding, and access control.

## Principle
RAG quality depends on retrieving the right information while preventing the wrong information from entering context.

## Retrieval Evaluation
Measure relevance, recall, precision, ranking quality, required-context retrieval, and resistance to irrelevant context where appropriate.

## Dataset
Include factual, multi-document, ambiguous, no-answer, similar-but-wrong, permission-sensitive, and adversarial-document cases.

## Access Control
Authorization must be enforced before restricted content enters model context. Test ownership, roles, tenant boundaries, revoked access, and restricted collections.

## Context Construction
Validate selected documents, metadata, context size, deduplication, ordering, and safe formatting.

## Grounding
Where grounding is required, generated answers should be supported by retrieved evidence.

## No-Answer Behavior
When evidence is insufficient, the system should not fabricate certainty.

## Prompt Injection
Retrieved documents are untrusted input. Test malicious instructions embedded in content.

## Index Changes
Changes to chunking, embeddings, ranking, metadata filters, or retrieval algorithms require regression evaluation.

## Failure Cases
Test unavailable retrieval, empty retrieval, partial retrieval, corrupt metadata, and index lag.

## Cost & Latency
Track retrieval/generation latency and resource consumption.

## Anti-Patterns
Avoid evaluating generation without retrieval quality, retrieving unauthorized data then filtering later, or assuming retrieved text is trustworthy.

# Next Document
**11-034 — Cross-Browser, Device & Compatibility Testing**
