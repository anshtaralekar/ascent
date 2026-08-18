# Mutation Testing & Test Effectiveness

## Purpose
Defines methods for determining whether tests can detect meaningful defects.

## Principle
High coverage does not guarantee strong assertions. Mutation testing introduces controlled changes and checks whether tests detect them.

## Suitable Scope
Prioritize business-critical logic, authorization, validation, financial calculations, data transformations, and complex decisions.

## Mutation Types
Examples include changing comparisons, removing conditions, altering return values, modifying arithmetic, or removing validation.

## Interpretation
Mutation score is a diagnostic measure, not a vanity target. Equivalent mutants that do not change observable behavior should not be treated as test weakness.

## Test Gaps
Surviving meaningful mutations should trigger investigation into missing tests, weak assertions, or incorrect test scope.

## AI
Mutation testing is especially useful for AI-generated tests because it can reveal tests that merely reproduce implementation.

## Performance
Use targeted or scheduled mutation runs when full mutation analysis is too expensive.

## Anti-Patterns
Do not optimize blindly for a mutation percentage or treat every surviving mutant as a production defect.

# Next Document
**11-018 — Property-Based & Generative Testing**
