# Rollback, Roll-Forward & Recovery Strategy

## Purpose

Defines how Ascend responds when a deployment introduces unacceptable behavior.

## Principle

Recovery is a planned operational capability, not an emergency improvisation.

## Rollback

Rollback returns traffic or deployment state to a previously approved version.

Use when the previous version remains compatible with:

- Database schema
- Data state
- APIs
- Dependencies
- Configuration

## Roll-Forward

Roll-forward deploys a corrected version when reverting is unsafe or impossible.

This is often preferable after irreversible data migrations.

## Feature Disablement

Feature flags may provide a rapid way to disable faulty functionality without reverting the entire application.

## Decision Factors

Choose recovery based on:

- Failure severity
- Data compatibility
- Migration state
- User impact
- Security impact
- Recovery speed
- Availability

## Database Recovery

Never assume application rollback automatically rolls back database changes.

Database recovery must follow Volume 07 migration and recovery rules.

## AI Recovery

For AI changes, recovery may include:

- Previous model
- Previous prompt/configuration
- Tool disablement
- Feature flag
- Provider fallback where supported

## Automated Rollback

Automation may trigger recovery when objective conditions are met.

Automated recovery must have safeguards against repeated rollback loops.

## Verification

After recovery verify:

- Service health
- Critical workflows
- Data integrity
- Error rates
- Relevant security controls

## Evidence

Preserve deployment and recovery evidence for diagnosis.

## Post-Recovery

Material incidents require appropriate root-cause analysis and regression coverage according to Volumes 09 and 11.

## Anti-Patterns

Avoid automatic rollback without understanding database compatibility, deleting the failed artifact, repeatedly rolling back without diagnosis, and assuming a successful process restart means recovery is complete.

# Next Document

**12-010 — Deployment Observability & Release Monitoring**
