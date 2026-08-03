---
title: Backend Project Organization
document_id: BA-004
version: 1.0.0
status: Draft
owner: Backend Architecture Team
---

# Backend Project Organization

> "Consistency inside every service reduces complexity across the platform."

## Purpose

Defines the internal folder structure and architectural layers used by every backend service.

---

## Philosophy

Each service follows the same layered architecture, making code predictable, maintainable, and easy to extend.

---

## Standard Structure

```text
src/
├── controllers/
├── routes/
├── services/
├── repositories/
├── domain/
├── dto/
├── validators/
├── middleware/
├── config/
├── utils/
└── tests/
```

---

## Layer Responsibilities

- Controllers: Handle HTTP requests
- Routes: Define endpoints
- Services: Business logic
- Repositories: Data access
- Domain: Core business models
- DTOs: Request/response contracts
- Validators: Input validation
- Middleware: Cross-cutting concerns

---

## Dependency Flow

Routes → Controllers → Services → Repositories → Database

Dependencies should flow inward and never bypass layers.

---

## Configuration

Centralize:

- Environment loading
- Feature flags
- Service configuration
- Shared constants

---

## Testing

Mirror the production structure.

Provide unit, integration, and end-to-end tests.

---

## Performance

- Minimize cross-layer calls
- Keep controllers thin
- Reuse shared utilities
- Avoid duplicate logic

---

## Anti-Patterns

Avoid:

- Fat controllers
- Database queries in routes
- Circular dependencies
- Shared mutable globals

---

## AI Context

AI coding agents should place new code in the appropriate architectural layer and preserve the established dependency flow.

---

# Next Document

**BA-005 — Request Lifecycle**
