# Localization, Time & Internationalization Testing

## Purpose
Defines validation for locale, timezone, dates, numbers, currency, Unicode, and internationalization-sensitive behavior.

## Principle
Software must not silently assume one language, timezone, character set, or formatting convention.

## Unicode
Test Latin and non-Latin scripts, accented characters, emoji, combining characters, and right-to-left text where supported.

## Text Length
Validate short text, long translations, long names, and long AI-generated responses.

## Dates & Times
Test timezone conversion, day/month/year boundaries, leap years, daylight-saving transitions where applicable, UTC/storage conventions, and local display.

## Locale Formatting
Where relevant validate numbers, decimal separators, thousands separators, currency, dates, and time formats.

## Sorting & Search
Test locale-sensitive behavior where product requirements depend on it.

## Database
Verify supported Unicode survives storage, retrieval, search, serialization, and export.

## APIs
Use unambiguous date/time representations according to Volume 08.

## AI
Test multilingual prompts, mixed-language input, Unicode tool arguments, and localization-sensitive output formatting where supported.

## Determinism
Freeze or control time when deterministic testing is required. Unit tests must not depend on a developer machine's timezone.

## Translation
Where localization exists, test missing keys, fallback behavior, interpolation, and layout impact.

## Anti-Patterns
Avoid hard-coded local-time assumptions, ASCII-only fixtures, fixed text widths, ambiguous dates, and locale-dependent tests.

# Volume 11 Progress
**11-001 through 11-035 complete.**

# Next Document
**11-036 — Production Verification & Synthetic Monitoring**
