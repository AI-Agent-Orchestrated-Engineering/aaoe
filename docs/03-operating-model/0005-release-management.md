# Release Management

**Specification ID:** OM-0005

**Domain:** Operating Model

**Version:** 1.0

**Status:** Draft

**Last Updated:** 2026-07-28

## Purpose

Release Management governs how approved engineering work becomes part of
AAOE's canonical knowledge. It protects the integrity of that knowledge
while allowing engineering work to evolve incrementally, one approved Task
at a time.

Release Management governs knowledge integration, not version control
systems. It defines what must be true before work becomes canonical, not
which repository tooling carries that integration out.

## Principles

- Only approved work becomes canonical.
- Canonical knowledge is traceable to the decision that approved it.
- Integration preserves history rather than overwriting it.
- Releases are reproducible from that preserved history.
- Governance precedes publication.
- Repository tooling is an implementation detail.

## Inputs

- An approved [Architecture Review](0004-architecture-review.md) outcome.
- An approved integration artifact (e.g. a Pull Request or equivalent).
- The specifications the approved work is expected to be consistent with.
- The existing canonical release state the work builds on.

## Responsibilities

- Integrate approved work into the canonical release state.
- Preserve release integrity throughout integration.
- Maintain traceability between canonical knowledge and its approval.
- Ensure canonical documentation remains internally consistent after
  integration.
- Prepare the canonical state that the next engineering iteration will
  build on.

## Release Criteria

Before work becomes canonical, the following must hold:

- Architecture Review has been completed.
- Approval has been granted.
- Required artifacts, including the Implementation Report, are present.
- Traceability between the change and its approval is preserved.
- Canonical documentation remains consistent after integration.

## Outputs

- Updated canonical knowledge.
- A new canonical release state.
- A traceable release history.

## Governance

- Release Management does not redefine architecture.
- Release Management does not reinterpret review decisions; it integrates
  what Architecture Review has already approved.
- Only approved work may be integrated.
- Integration preserves engineering history rather than collapsing or
  discarding it.
- Canonical knowledge is the authoritative reference once integrated.

## Relationship to the Engineering Lifecycle

Release Management follows Approval and precedes the next Work Order in the
[Engineering Lifecycle](0001-engineering-lifecycle.md). It is the governance
activity that turns an approved result into the new canonical baseline,
which the next Task then builds on.

## Relationship to Repository Tooling

Git, pull requests, merge commits, release branches, or future
technologies are implementation mechanisms that may carry out integration.
AAOE specifies the governance that integration must satisfy, not the
tooling that performs it.

## Future Evolution

Release Management may support additional publication or distribution
mechanisms as AAOE evolves, while preserving these governance principles:
only approved work becomes canonical, integration is traceable, and
releases remain reproducible.
