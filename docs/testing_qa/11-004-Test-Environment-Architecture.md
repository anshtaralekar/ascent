# Test Environment Architecture

## Purpose
Defines environments used for automated and manual validation.

## Environment Principle
Test environments must provide sufficient realism without exposing production systems or data.

## Categories
Local, ephemeral, shared integration, dedicated QA, and staging environments may be used according to the repository architecture.

## Isolation
Test environments must not unintentionally share production databases, secrets, credentials, queues, or administrative identities.

## Ephemeral Environments
Use when they improve isolation, reproducibility, parallel testing, or review workflows.

## Shared Environments
Tests must account for shared-state interference.

## Test Data
Prefer generated or synthetic data that is reproducible and resettable.

## Database State
Define creation, seeding, reset, migration, and cleanup behavior.

## External Providers
Use sandbox providers, controlled mocks, contract tests, or approved test credentials according to the behavior being validated.

## AI Providers
Control provider/model, credentials, usage limits, cost, and test data. Ordinary CI must not accidentally trigger expensive production AI workflows.

## Production Protection
Automated tests must have technical safeguards against targeting production, such as separate credentials, explicit environment selection, and production access denial.

## AI Context
AI coding agents must identify the target test environment before running tests that modify persistent state.

# Next Document
**11-005 — Test Data & Fixture Management**
