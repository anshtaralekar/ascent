# Scheduled Jobs & Cron Deployment

## Purpose

Defines how scheduled tasks are deployed and operated safely.

## Principle

A scheduled task must execute predictably without creating duplicate or missed work during deployment transitions.

## Schedule Definition

Schedules must be version-controlled where supported and clearly identify:

- Frequency
- Timezone
- Job
- Ownership
- Expected duration

## Timezone

Scheduled behavior must use an explicit timezone policy.

Do not rely on the host machine's local timezone.

## Deployment Overlap

During rolling deployment, prevent unintended duplicate scheduled execution.

## Distributed Scheduling

Where multiple instances may execute the scheduler, use the architecture's approved coordination or locking mechanism.

## Idempotency

Scheduled jobs should be idempotent where repeated execution is possible.

## Failure Handling

Define behavior for:

- Job timeout
- Partial completion
- Retry
- Missed schedule
- Overlapping execution
- Dependency outage

## Backfill

If a schedule is missed, determine whether the job should:

- Skip
- Execute once
- Replay missed intervals
- Require manual recovery

## AI Scheduled Jobs

AI jobs must have explicit limits for:

- Model calls
- Tokens
- Runtime
- Cost
- Tool operations

A scheduler must not create an uncontrolled AI spending loop.

## Observability

Monitor:

- Last successful run
- Duration
- Failure count
- Next scheduled execution
- Output/backlog where applicable

## Deployment Verification

After deployment verify that the schedule exists, is enabled as intended, and has the correct target/version.

## Anti-Patterns

Avoid host-local timezone assumptions, duplicate schedulers, unbounded AI retries, and schedules with no ownership.

# Next Document

**12-020 — CDN, DNS, TLS & Edge Deployment**
