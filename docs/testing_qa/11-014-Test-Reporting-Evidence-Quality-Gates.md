# Test Reporting, Evidence & Quality Gates

## Purpose

Defines how test results become release evidence and how failures affect progression through the delivery pipeline.

## Evidence Principle

A test result is valuable when it is:

- Traceable
- Reproducible
- Relevant
- Understandable
- Associated with the tested artifact

## Required Metadata

Important test runs should identify:

- Source revision
- Artifact/version
- Environment
- Test suite/version
- Timestamp
- Result

## Result Categories

Distinguish:

- Passed
- Failed
- Skipped
- Blocked
- Flaky/investigating
- Not applicable

Do not silently convert failures into skips.

## Quality Gates

Gates should be based on risk and meaningful evidence.

Examples:

- Required unit suite passes
- Contract compatibility passes
- Critical security checks pass
- Critical E2E journeys pass
- Required performance thresholds pass

## Blocking Failures

A release should stop when a required blocking gate fails.

Emergency release procedures may override normal gates only through the approved emergency process.

## Non-Blocking Findings

Warnings may be tracked when they do not justify blocking release.

They must still have appropriate ownership.

## Evidence Retention

Retain test evidence according to operational and compliance requirements.

Avoid retaining sensitive test data unnecessarily.

## Coverage Reporting

Coverage can identify untested areas, but thresholds should not become substitutes for meaningful behavioral validation.

## Security Evidence

Security-related tests should retain sufficient evidence for investigation and audit where required.

## AI Evaluation Evidence

For material AI behavior changes, retain:

- Evaluation version
- Model/provider
- Evaluation results
- Failure categories
- Comparison against relevant baseline

## Release Traceability

A production release should be traceable to the validation evidence that allowed it to proceed.

## Quality Dashboard

A quality dashboard may aggregate:

- Test health
- Failure trends
- Flakiness
- Coverage
- Security findings
- Performance trends

Dashboards must not hide failing gates.

## Anti-Patterns

Avoid:

- Green dashboards that omit blocked tests
- Manual editing of test results
- Gates based only on coverage
- Untraceable test artifacts
- Treating flaky tests as permanent passes

# Next Document

**11-015 — Test Failure Triage & Debugging Standards**
