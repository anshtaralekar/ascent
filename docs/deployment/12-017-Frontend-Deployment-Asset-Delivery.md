# Frontend Deployment & Asset Delivery

## Purpose

Defines how Ascend frontend applications and static assets are built, versioned, delivered, cached, and verified.

## Principle

Frontend deployment must preserve asset integrity and compatibility between client and backend versions.

## Build

Frontend builds must be reproducible and traceable to source and dependency state.

## Asset Identity

Generated assets should use versioned or content-addressed identifiers where appropriate.

## Caching

Caching strategy must account for:

- HTML
- JavaScript
- CSS
- Images
- Fonts
- API responses where applicable

Immutable assets may receive long cache lifetimes.

Entry documents should be invalidated safely when they reference new assets.

## CDN

Where a CDN is used, deployment must account for:

- Propagation
- Cache invalidation
- TLS
- Compression
- Origin availability

## Backend Compatibility

A newly deployed frontend may temporarily coexist with an older backend.

API compatibility must therefore follow Volume 08.

## Rollback

Rollback must account for cached assets and clients that may retain previous versions.

## Environment Configuration

Public frontend configuration must contain only values safe for client exposure.

Secrets must never be embedded in client bundles.

## AI Interfaces

Frontend deployment must preserve compatibility with:

- Streaming
- Long-running responses
- Tool confirmation flows
- Error states
- Feature flags

## Verification

After deployment verify:

- Main application loads
- Assets resolve
- Authentication works
- Critical routes work
- API communication succeeds
- AI interfaces function where applicable

## Security

Verify that source maps, debug bundles, and deployment artifacts follow the approved exposure policy.

## Anti-Patterns

Avoid embedding secrets in frontend configuration, uncontrolled cache invalidation, deploying frontend and incompatible API changes together, and relying only on successful HTML delivery as proof of deployment health.

# Next Document

**12-018 — Worker, Queue & Background Job Deployment**
