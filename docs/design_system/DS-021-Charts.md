---
title: Charts
document_id: DS-021
version: 1.0.0
status: Draft
owner: Design System Team
---

# Charts

> "Good charts reveal progress at a glance."

## Purpose

Defines reusable data visualization components for Ascend.

## Philosophy

Charts should communicate trends, progress, comparisons, and insights with minimal cognitive load.

---

## Supported Charts

- Line Chart
- Area Chart
- Bar Chart
- Stacked Bar Chart
- Pie Chart
- Donut Chart
- Progress Ring
- Heatmap
- Radar Chart
- Timeline Chart
- Sparkline

---

## Usage

Used for:

- Habit tracking
- Goal progress
- XP progression
- Productivity analytics
- Focus sessions
- Health metrics
- AI insights

---

## Anatomy

- Chart Area
- Axes
- Legend
- Labels
- Tooltip
- Grid
- Empty State

---

## States

- Loading
- Empty
- Error
- Interactive
- Filtered
- Expanded

---

## Interaction

Support:

- Hover tooltips
- Zoom
- Filtering
- Legend toggle
- Keyboard navigation
- Export

---

## Accessibility

- High contrast
- Patterns in addition to color
- Screen reader summaries
- Keyboard support

---

## Tokens

Uses Color, Typography, Spacing, Motion and Elevation tokens.

---

## Engineering Notes

Implement reusable chart wrappers with consistent APIs and theme support.

---

## AI Context

AI insights should render through approved chart components.

---

Next Document: DS-022 — Empty States
