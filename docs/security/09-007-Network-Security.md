---
title: Network Security
document_id: 09-007
volume: 09
version: 1.0.0
status: Draft
owner: Security Architecture Team
---

# Network Security

## Purpose

Defines the network-security principles protecting APIs, services, databases, workers, administrative systems, and external integrations.

## Philosophy

Network location is not a substitute for identity or authorization.

A component being inside a private network does not automatically make it trusted.

## Network Segmentation

Separate systems according to risk and responsibility where practical.

Potential zones include:

- Public edge
- Application services
- Databases
- Background workers
- Administrative systems
- Build/deployment infrastructure

## Public Exposure

Only components that must receive public traffic should be publicly reachable.

Databases and internal service infrastructure should not be exposed directly to the public internet.

## Ingress

Inbound traffic should pass through approved edge controls.

Controls may include:

- TLS
- WAF
- Rate limiting
- Request filtering
- Authentication integration
- DDoS protection

## Egress

Outbound traffic should be controlled where practical.

This is particularly important for:

- User-controlled URLs
- External integrations
- AI tools
- File processors
- Webhooks
- Server-side fetch operations

## SSRF Protection

Applications that retrieve remote resources must restrict destinations and protocols according to the threat model.

Do not allow arbitrary user-controlled network access from trusted infrastructure.

## Service-to-Service Traffic

Internal services should authenticate one another and use encrypted communication where required.

## Database Network Access

Databases should accept connections only from approved application components and administrative paths.

## Administrative Access

Production administrative interfaces require stronger controls and should not be broadly exposed.

## DNS and Hostname Handling

User-controlled hostnames must not automatically become trusted destinations.

Validate resolved destinations where SSRF or network-boundary bypass is possible.

## AI Network Boundary

AI tools must not automatically receive unrestricted network access.

Any tool capable of fetching URLs, calling services, or interacting with external systems must have explicit scope and authorization.

## Network Monitoring

Monitor:

- Unexpected inbound traffic
- Unexpected outbound traffic
- Connection failures
- Port exposure
- Suspicious destinations
- Network anomalies

## Availability

Network controls must account for availability and avoid creating single points of failure without an appropriate recovery plan.

## Anti-Patterns

Avoid:

- Public databases
- Universal internal network trust
- Unrestricted server-side HTTP requests
- Unrestricted AI network access
- Shared administrative access paths

## AI Context

AI coding agents must inspect existing network boundaries before adding integrations, webhooks, remote fetches, workers, or new exposed services.

# Next Document

**09-008 — Application Security**
