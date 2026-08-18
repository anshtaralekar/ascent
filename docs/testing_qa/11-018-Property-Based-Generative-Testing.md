# Property-Based & Generative Testing

## Purpose
Defines invariant-based testing across broad generated input spaces.

## Principle
Example tests prove selected cases. Property-based tests check whether important invariants remain true across many cases.

## Suitable Domains
Use for parsers, serialization, validation, transformations, mathematical logic, search/filter behavior, and state transitions.

## Properties
Examples:
- Serialization followed by deserialization preserves required information.
- Sorting preserves all elements.
- Invalid structures are rejected.
- Authorization never grants access outside the allowed scope.

## Generators
Include normal, boundary, empty, large, invalid, and structured combinations.

## Reproducibility
Record seeds or equivalent reproduction information when deterministic replay matters.

## Security
Generated inputs can explore Unicode, malformed structures, nested data, and unusual encodings, complementing Volume 09.

## AI
Generative testing may probe prompt variations, ambiguous instructions, tool arguments, and retrieval queries. Tests remain bounded and reviewed.

## Limits
Bound runtime, input size, case count, and resource consumption.

## Anti-Patterns
Avoid non-reproducible randomness, trivial generators, and unbounded generation.

# Next Document
**11-019 — Fuzz Testing & Robustness Validation**
