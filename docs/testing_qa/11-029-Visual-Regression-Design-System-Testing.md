# Visual Regression & Design-System Testing

## Purpose

Defines how Ascend protects visual consistency while allowing intentional design evolution.

## Principle

Visual tests should detect meaningful unintended changes without becoming brittle noise.

## Scope

Use visual validation for:

- Design-system primitives
- Critical layouts
- Navigation
- Forms
- Important responsive states
- High-value user journeys

## Baselines

Visual baselines must be associated with:

- Component/version
- Browser/runtime
- Viewport
- Relevant theme/configuration

## Review

Visual differences must be classified as:

- Intended change
- Unintended regression
- Environment/rendering variation
- Test artifact

## Design System

Changes to shared components should evaluate downstream visual impact.

## Responsive Testing

Where supported, validate representative viewport sizes.

## Typography

Visual tests should account for controlled font availability. Missing or inconsistent fonts can create misleading differences.

## Dynamic Content

Avoid unstable data in visual snapshots.

Use deterministic fixtures for:

- Dates
- User names
- Generated content
- Images
- AI responses

## AI Interfaces

Do not use unconstrained live model output as the sole visual baseline.

Use controlled representative outputs.

## Accessibility

Visual validation complements, but does not replace, accessibility testing.

## Thresholds

Use appropriate tolerance for rendering variation.

Do not increase tolerance until real regressions disappear merely to make CI green.

## Baseline Updates

Baseline updates should be attributable to an intentional change.

## Anti-Patterns

Avoid snapshotting the entire application for every small change, unstable dynamic data, excessive tolerance, and approving visual differences without review.

# Next Document

**11-030 — AI Evaluation & Model Quality Testing**
