# Scalability & Capacity Testing

## Purpose

Defines how Ascend determines whether infrastructure and application capacity scales with increasing workload.

## Principle

Scaling should be measured rather than assumed.

## Scaling Dimensions

Test relevant dimensions such as:

- Concurrent users
- Requests per second
- Data volume
- Queue depth
- Worker count
- Database size
- AI requests
- Tenant count

## Horizontal Scaling

Validate that adding instances produces expected capacity gains without introducing coordination or dependency bottlenecks.

## Vertical Scaling

Determine whether additional CPU/memory produces meaningful performance improvements.

## Autoscaling

Validate:

- Scale-up trigger
- Scale-up speed
- Maximum capacity
- Scale-down behavior
- Stabilization
- Recovery after burst

Volume 10 remains authoritative for infrastructure scaling architecture.

## Bottleneck Analysis

Identify limiting resources rather than assuming application compute is the bottleneck.

Potential bottlenecks include:

- Database
- Connection pools
- Queue
- Network
- External provider
- Storage
- AI provider quota

## Multi-Tenant Capacity

Where applicable, test whether one tenant can consume disproportionate shared resources.

## AI Capacity

Test token throughput, concurrency, provider quotas, queueing, and cost ceilings.

## Capacity Thresholds

Document meaningful thresholds for:

- Latency
- Error rate
- Resource utilization
- Queue age
- Storage
- Provider quota

## Failure at Capacity

Verify intentional behavior when maximum capacity is reached:

- Queue
- Rate limit
- Reject safely
- Degrade optional features

## Cost

Capacity tests should account for infrastructure and external-provider cost.

## Anti-Patterns

Avoid testing only a single instance, assuming linear scaling, ignoring database limits, or allowing capacity tests to create unbounded provider spend.

# Next Document

**11-023 — Reliability & Resilience Testing**
