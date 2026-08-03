---
title: Role-Based Access Control
document_id: BA-017
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Role-Based Access Control (RBAC)

> "Permissions should follow responsibility, not convenience."

## Purpose

Defines the Role-Based Access Control architecture for Ascend.

---

## Philosophy

Authorization determines what an authenticated identity is allowed to do. Access should follow the principle of least privilege.

---

## Core Concepts

- Users
- Roles
- Permissions
- Resources
- Policies

---

## Built-in Roles

Support roles such as:

- Super Administrator
- Administrator
- Workspace Owner
- Manager
- Member
- Guest
- Service Account

---

## Permission Model

Permissions should be:

- Explicit
- Granular
- Auditable
- Composable

---

## Evaluation Flow

1. Authenticate identity
2. Resolve assigned roles
3. Load permissions
4. Evaluate resource ownership
5. Apply policies
6. Grant or deny access

---

## Resource Ownership

Resource owners may receive additional permissions beyond inherited role permissions where appropriate.

---

## Administration

Support:

- Role assignment
- Role revocation
- Temporary roles
- Delegated administration

---

## Security

- Enforce least privilege
- Deny by default
- Audit permission changes
- Validate every protected request

---

## Anti-Patterns

Avoid:

- Hardcoded role checks
- Permission duplication
- Implicit privileges
- Client-side authorization

---

## AI Context

AI coding agents should perform authorization through centralized RBAC middleware and shared permission services.

---

# Next Document

**BA-018 — Permission Engine**
