# Frontend & UI Testing Standards

## Purpose

Defines how Ascend frontend behavior, interaction, state, and accessibility-related behavior are validated.

## Scope

Frontend testing may include:

- Component tests
- Interaction tests
- Visual validation
- Accessibility testing
- Browser compatibility
- End-to-end journeys

## Rendering

Validate meaningful UI states:

- Initial
- Loading
- Success
- Empty
- Error
- Permission denied
- Offline/degraded where applicable

## User Interaction

Test behavior through user-level interactions rather than implementation internals.

Examples:

- Clicking
- Typing
- Selecting
- Submitting
- Navigating
- Keyboard interaction

## State

Validate important transitions such as:

```text
Idle → Loading → Success
Idle → Loading → Error
Authenticated → Expired
Editable → Saving → Saved
```

## API Integration

Frontend tests should verify correct handling of API contracts without duplicating backend tests unnecessarily.

## Accessibility

Validate relevant:

- Keyboard access
- Focus behavior
- Labels
- Semantic roles
- Error messaging
- Contrast where automated tooling supports it

Detailed accessibility requirements remain governed by the product design/accessibility architecture.

## Visual Testing

Use visual regression testing where visual consistency is important.

Visual snapshots must avoid unnecessary sensitivity to irrelevant rendering differences.

## Browser Coverage

Test supported browser/device combinations according to product requirements.

## Responsive Behavior

Validate critical layouts at supported viewport sizes.

## AI Interfaces

Test:

- Loading behavior
- Streaming states where applicable
- Partial output
- Tool/action confirmation
- Error recovery
- Long-output handling
- Unsafe or rejected actions

Never allow a UI test to bypass backend authorization merely because the UI hides a control.

## Anti-Patterns

Avoid brittle selectors, arbitrary delays, implementation-only assertions, and treating visual snapshots as a substitute for functional tests.

# Next Document

**11-028 — Accessibility Testing & Validation**
