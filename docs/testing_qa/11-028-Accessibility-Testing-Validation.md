# Accessibility Testing & Validation

## Purpose

Defines how Ascend validates that supported product experiences remain usable by people with diverse accessibility needs.

## Principle

Accessibility is a quality requirement, not a cosmetic enhancement.

## Testing Layers

Use a combination of:

- Automated accessibility checks
- Keyboard testing
- Screen-reader-oriented validation
- Manual interaction review
- Browser/device validation

## Automated Checks

Automate detectable issues such as:

- Missing labels
- Invalid semantics
- Duplicate identifiers
- Certain contrast failures
- Invalid ARIA usage

Automated tools cannot detect every accessibility problem.

## Keyboard

Critical workflows must be usable without requiring a mouse where the interaction model supports keyboard operation.

Validate:

- Focus order
- Focus visibility
- Keyboard activation
- Dialog focus
- Escape behavior
- Focus restoration

## Forms

Validate:

- Labels
- Instructions
- Required states
- Error association
- Error recovery

## Dynamic Content

Important changes should be communicated appropriately to assistive technologies.

## Loading and Errors

Accessible states must exist for:

- Loading
- Success
- Failure
- Empty results
- Disabled controls

## Media

Where applicable, provide appropriate alternatives, captions, or accessible controls.

## AI Interfaces

AI responses and AI-generated UI content should remain usable with supported assistive technologies.

Dynamic streaming output must not trap focus or create unusable navigation.

## Testing Data

Include realistic long text, short text, errors, localization variations, and empty states.

## Regression

Accessibility checks should run continuously for critical frontend areas.

## Manual Review

Human accessibility review remains necessary for issues automation cannot reliably detect.

## Anti-Patterns

Avoid treating an automated accessibility score as complete compliance, removing semantics merely to silence a tool, or testing only the ideal UI state.

# Next Document

**11-029 — Visual Regression & Design-System Testing**
