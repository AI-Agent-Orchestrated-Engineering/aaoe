# ADR-0002: Hybrid Repository Strategy

- **Status:** Accepted
- **Date:** 2026-07-28
- **Deciders:** AAOE Maintainers

## Context

AAOE is an engineering ecosystem with multiple knowledge domains and, over
time, may include website delivery, templates, examples, case studies, and
software projects. Keeping every domain in one repository would eventually
make ownership, release cadence, and navigation difficult. Creating many
repositories before each has an independent purpose would add unnecessary
coordination overhead.

AAOE already has two repositories: `aaoe` and `aaoe-specifications`.

## Decision

AAOE adopts a hybrid repository strategy.

The GitHub organization is the AAOE ecosystem. The `aaoe` repository is its
canonical entry point: it owns ecosystem governance, navigation, cross-domain
guidance, and the public orientation of AAOE.

Repositories are created or separated only when a domain has an independent
responsibility, ownership boundary, or lifecycle. The `aaoe-specifications`
repository is the canonical library for AAOE standards and specifications.

Future domains—such as website delivery, reusable templates, and public
examples—may become independent repositories when their lifecycle warrants
that separation. They are not created merely because a new content type exists.

## Consequences

- Contributors have one clear starting point in `aaoe`.
- Standards remain focused and independently versionable in
  `aaoe-specifications`.
- New repositories require a documented responsibility and lifecycle rationale.
- Cross-repository links and navigation become part of the ecosystem's
  governance responsibility.
- AAOE avoids both a premature proliferation of repositories and an oversized
  monorepository.

## Scope

This decision defines the repository strategy only. It does not create future
repositories or prescribe their internal structures.
