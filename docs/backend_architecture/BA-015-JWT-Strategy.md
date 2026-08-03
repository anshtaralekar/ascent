---
title: JWT Strategy
document_id: BA-015
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# JWT Strategy

> "Tokens should be short-lived, verifiable, and easy to rotate."

## Purpose

Defines the JSON Web Token (JWT) strategy for authentication and service communication in Ascend.

---

## Philosophy

Use short-lived access tokens with securely managed refresh tokens to balance security and usability.

---

## Token Types

- Access Token
- Refresh Token
- Service Token
- AI Service Token

Each token serves a distinct purpose.

---

## Access Tokens

- Short-lived
- Signed
- Stateless
- Contain only essential claims

Never store sensitive information inside token payloads.

---

## Refresh Tokens

Support:

- Rotation
- Revocation
- Device association
- Secure server-side validation

---

## Claims

Standard claims include:

- Subject
- Issuer
- Audience
- Issued At
- Expiration
- JWT ID

Application-specific claims should remain minimal.

---

## Signing

Use modern asymmetric signing algorithms.

Support secure key rotation without invalidating active sessions unnecessarily.

---

## Validation

Validate:

- Signature
- Expiration
- Audience
- Issuer
- Revocation status

Reject malformed or expired tokens immediately.

---

## Security

Implement:

- HTTPS only
- Secure cookies where applicable
- Token replay protection
- Least-privilege claims

---

## Anti-Patterns

Avoid:

- Long-lived access tokens
- Secrets inside payloads
- Weak signing algorithms
- Client-side token generation

---

## AI Context

AI coding agents should implement JWT handling through centralized authentication middleware and shared token utilities.

---

# Next Document

**BA-016 — OAuth Providers**
