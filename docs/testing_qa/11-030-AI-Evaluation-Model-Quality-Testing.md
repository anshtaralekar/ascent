# AI Evaluation & Model Quality Testing

## Purpose

Defines how Ascend validates AI behavior where traditional deterministic software tests are insufficient.

## Principle

AI quality must be evaluated against explicit behavioral criteria and representative datasets rather than judged from a handful of successful examples.

## Evaluation Dimensions

Depending on the feature, evaluate:

- Correctness
- Relevance
- Instruction adherence
- Grounding
- Consistency
- Tool selection
- Tool argument correctness
- Safety
- Refusal behavior
- Latency
- Cost

## Evaluation Dataset

Maintain representative datasets containing:

- Normal requests
- Edge cases
- Ambiguous requests
- Adversarial prompts
- Prompt-injection attempts
- Retrieval cases
- Tool-use cases
- Failure scenarios
- Safety-sensitive cases

## Dataset Versioning

Evaluation datasets must be versioned.

A model or prompt change should be evaluated against an appropriate baseline.

## Deterministic Assertions

Where possible, test deterministic boundaries separately:

- Schema validity
- Authorization
- Tool permissions
- Required fields
- Output parsing
- Resource limits

Do not ask an LLM judge to validate a security permission that code can validate deterministically.

## Model Evaluation

Evaluate model/provider changes for both improvements and regressions.

A change that improves one metric while materially damaging safety, correctness, cost, or reliability may not be acceptable.

## Human Evaluation

Human review may be required for nuanced qualities such as:

- Helpfulness
- Tone
- Factual usefulness
- Complex reasoning quality

Human evaluation criteria must be explicit enough to reduce arbitrary scoring.

## Automated Evaluation

Automated evaluators may use:

- Exact-match checks
- Structured assertions
- Reference comparisons
- Rubric-based evaluation
- Model-based judges

Model-based judges are themselves imperfect and should not be treated as unquestionable ground truth.

## Retrieval Evaluation

Where RAG is used, evaluate:

- Retrieval relevance
- Recall of required context
- Groundedness
- Citation/source alignment where applicable
- Irrelevant-context resistance

## Tool Evaluation

Validate:

- Correct tool selection
- Correct arguments
- Authorization
- Failure handling
- Side-effect boundaries

## Safety Evaluation

Include:

- Direct harmful requests
- Indirect instructions
- Prompt injection
- Sensitive data requests
- Cross-tenant data attempts
- Tool abuse
- Resource exhaustion

## Regression

Maintain historical failure cases as regression evaluations.

## Cost and Latency

Track evaluation changes in:

- Token consumption
- Provider cost
- Response latency
- Tool-call count

## Release Gate

Material AI behavior changes should satisfy defined quality, security, latency, and cost thresholds before release.

## Anti-Patterns

Avoid:

- Evaluating AI on only happy-path prompts
- Treating one model response as proof of correctness
- Letting model output decide authorization
- Using a model judge as the sole safety gate
- Ignoring cost and latency regressions

# Volume 11 Progress

**11-001 through 11-030 complete.**

# Next Document

**11-031 — AI Safety & Adversarial Evaluation**
