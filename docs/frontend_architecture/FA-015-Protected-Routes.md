---
title: Protected Routes
document_id: FA-015
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Protected Routes

> "Every route should expose only what the user is permitted to access."

## Purpose

Defines the authentication and authorization strategy for route protection across Ascend.

---

## Philosophy

Authentication verifies identity.

Authorization determines access.

Both must be enforced consistently at the server boundary.

---

## Route Categories

- Public Routes
- Auth Routes
- Protected Routes
- Admin Routes
- System Routes

---

## Protection Strategy

Prefer server-side protection using middleware and server rendering.

Client-side guards should improve UX but never replace server validation.

---

## Authentication

Protected routes require:

- Valid session
- Active account
- Successful token validation

Expired sessions should redirect to authentication.

---

## Authorization

Support:

- Role-Based Access Control (RBAC)
- Permission-based checks
- Feature flags
- Organization membership

---

## Redirect Rules

Unauthenticated users:

→ Login

Authenticated without permission:

→ 403 / Access Denied

Unknown routes:

→ 404

---

## Session Handling

Support:

- Session refresh
- Secure cookies
- Automatic expiration
- Logout from all devices

---

## Security

Never trust client-side authorization alone.

Validate permissions for every protected request.

---

## Anti-Patterns

Avoid:

- Hardcoded roles
- Client-only security
- Duplicate permission logic
- Exposed privileged routes

---

## AI Context

AI coding agents should protect new routes by default and implement authorization checks at the appropriate server boundary.

---

# Next Document

**FA-016 — Dynamic Routes**
