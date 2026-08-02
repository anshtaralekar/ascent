---
title: Technology Stack
document_id: FA-002
version: 1.0.0
status: Draft
owner: Frontend Architecture Team
---

# Technology Stack

> "Choose technologies for longevity, not novelty."

## Purpose

Defines the approved frontend technology stack for Ascend.

## Core Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 15 |
| UI | React 19 |
| Language | TypeScript |
| Styling | Tailwind CSS v4 |
| Components | shadcn/ui |
| Icons | Lucide |
| Animation | Framer Motion |
| Forms | React Hook Form + Zod |
| Global State | Zustand |
| Server State | TanStack Query |
| Tables | TanStack Table |
| Charts | Recharts |
| AI | Vercel AI SDK |
| Testing | Vitest + Playwright |
| Documentation | Storybook |
| Package Manager | pnpm |
| Monorepo | Turborepo |

## Selection Principles

- Type-safe
- Well maintained
- Production proven
- Strong ecosystem
- Excellent documentation
- AI-friendly APIs

## Dependency Policy

New dependencies must:
- Solve a unique problem
- Have active maintenance
- Avoid overlap
- Pass security review
- Minimize bundle impact

## Versioning

- Pin major versions
- Review updates regularly
- Test before upgrades

## AI Context

AI-generated code should only use approved technologies unless architecture owners explicitly approve alternatives.

# Next Document

**FA-003 — Monorepo Structure**
