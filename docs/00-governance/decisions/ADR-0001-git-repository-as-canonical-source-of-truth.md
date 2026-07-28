# ADR-0001: Git Repository as the Canonical Source of Truth

- **Status:** Accepted
- **Date:** 2026-07-28
- **Deciders:** AAOE Maintainers

## Context

AAOE knowledge will be expressed through standards, discoveries, architecture
decision records, case studies, templates, guides, and publication artifacts.
Without a declared source of truth, the same knowledge can diverge across a
website, blog posts, presentations, and external platforms.

## Decision

The AAOE Git repositories are the canonical source of truth for AAOE knowledge.

Canonical knowledge is created, reviewed, approved, and versioned in the
appropriate AAOE repository before it is published elsewhere. The `aaoe`
repository is the ecosystem's canonical entry point. Domain repositories, such
as `aaoe-specifications`, own canonical knowledge within their defined domain.

The website, blog posts, articles, whitepapers, presentations, books, and other
publication artifacts are derived from, or explicitly traceable to, canonical
repository content.

## Consequences

- Git history provides an auditable record of AAOE knowledge and decisions.
- Contributors review proposed knowledge changes through the repository
  workflow before publication.
- Publishing channels do not become independent sources of truth.
- Content owners must identify the canonical repository and source document for
  each published artifact.
- The approach keeps AAOE portable across publishing platforms.
