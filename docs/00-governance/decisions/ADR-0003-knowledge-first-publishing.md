# ADR-0003: Knowledge-First Publishing

- **Status:** Accepted
- **Date:** 2026-07-28
- **Deciders:** AAOE Maintainers

## Context

AAOE knowledge will be communicated through multiple channels, including the
website, articles, blog posts, presentations, and future books. Producing each
artifact independently risks inconsistent definitions, untraceable claims, and
duplicated maintenance effort.

## Decision

AAOE adopts a knowledge-first publishing model.

Canonical knowledge is authored and reviewed in the appropriate AAOE repository
before publication. Publication artifacts are derived from that knowledge or
explicitly linked to its canonical source.

The governing workflow is:

```text
Knowledge → Review → Approval → Publication
```

The website is a presentation and distribution channel. It does not replace the
repository as the owner of canonical knowledge.

## Consequences

- A change to an AAOE principle begins with its canonical source document.
- Published material can be traced to an approved standard, discovery, decision,
  case study, or other canonical source.
- Publication channels may simplify or adapt material for their audience, but
  must not silently redefine canonical knowledge.
- Maintaining one source reduces content drift and makes updates more reliable.
- The repository structure and review process become part of AAOE's publishing
  quality controls.

## Scope

This decision establishes the publishing model. It does not prescribe a website
technology, content-management system, or automated publishing tool.
