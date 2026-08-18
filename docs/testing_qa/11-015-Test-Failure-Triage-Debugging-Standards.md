# Test Failure Triage & Debugging Standards

## Purpose

Defines how test failures are investigated, classified, corrected, and prevented from becoming recurring noise.

## Principle

Every unexpected failure requires a classification before it is dismissed.

## Failure Categories

Classify failures as:

- Product defect
- Test defect
- Environment defect
- Dependency/provider failure
- Data/fixture defect
- Timing/concurrency issue
- Infrastructure failure
- Flaky/unresolved

## Triage Sequence

1. Reproduce the failure.
2. Inspect the first meaningful error.
3. Compare with recent changes.
4. Check environment and dependency health.
5. Determine whether the test or product is wrong.
6. Apply the smallest correct fix.
7. Re-run the relevant validation.
8. Run appropriate regression coverage.

## Evidence

Collect only evidence necessary for diagnosis.

Useful sources include:

- Test output
- Application logs
- Stack traces
- Network traces
- Screenshots
- Database state
- Deployment metadata

## Flaky Tests

A flaky test is one whose result changes without a relevant system change.

Investigate:

- Race conditions
- Shared state
- Timing assumptions
- External dependency instability
- Resource exhaustion
- Test-order dependence

## Quarantine

Temporary quarantine may be used when a test blocks delivery and requires deeper investigation.

Quarantine must have:

- Owner
- Reason
- Tracking issue
- Review/removal plan

Quarantine is not deletion.

## Product Defects

When a test exposes a real defect, retain or add regression coverage at the appropriate layer.

## Test Defects

Fix tests that make incorrect assumptions or validate the wrong behavior.

## Environment Defects

Repair the environment or automation rather than weakening assertions to accommodate broken infrastructure.

## AI Test Failures

Distinguish:

- Application integration failure
- Tool authorization failure
- Retrieval failure
- Provider failure
- Model-quality failure
- Evaluation-data issue

Do not automatically label every AI failure as a model problem.

## Security Failures

Security test failures should be treated according to Volume 09 severity and incident processes where applicable.

## Failure Communication

Reports should state:

- What failed
- Where
- Why it matters
- Current classification
- Owner
- Next action

## Root Cause

For recurring failures, identify systemic causes rather than repeatedly patching symptoms.

## Anti-Patterns

Avoid:

- Blind retries
- Deleting failing tests
- Marking failures as flaky without evidence
- Changing assertions merely to make CI pass
- Blaming AI/model behavior without inspecting the surrounding system

# Volume 11 Progress

**11-001 through 11-015 complete.**

# Next Document

**11-016 — Test Coverage & Measurement Standards**
