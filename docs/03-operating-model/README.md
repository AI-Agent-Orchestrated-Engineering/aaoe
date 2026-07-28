# AAOE Operating Model

- **Status:** Draft (v0.1)
- **Date:** 2026-07-28

## Purpose

The Operating Model describes how AAOE engineering work is organized: how
responsibilities are divided between the people and agents involved, and how
architecture becomes implementation. It is the entry point into a set of
detailed specifications; it does not itself define their mechanics.

This document does not restate the decisions already recorded in
[`docs/00-governance/decisions`](../00-governance/decisions/README.md), nor
does it duplicate the specifications it points to. It builds on the former
and summarizes the latter.

## Core Principles

- Work is organized around canonical knowledge, not around any single tool,
  channel, or publishing surface.
- Architecture is decided before implementation begins; implementation
  follows a defined work order rather than ad hoc instruction.
- AI-assisted work is a proposal until a human accepts it. Throughput comes
  from delegation, not from removing accountability.
- Structure should stay legible as the ecosystem grows: new work fits into an
  existing lifecycle instead of inventing a new process each time.

## Roles

AAOE engineering work is carried out by four roles: **Human Architect**,
**Implementation Agent**, **Human Reviewer**, and **Release Manager**. Their
responsibilities, authority, and interactions are fully defined in
[Roles & Responsibilities](roles-and-responsibilities.md).

## Engineering Lifecycle

AAOE engineering work moves through a defined sequence of stages, from
architectural intent to approved, merged knowledge:

```text
Architecture
        ↓
Work Order
        ↓
Implementation
        ↓
Implementation Report
        ↓
Architecture Review
        ↓
Approval
        ↓
Merge
        ↓
Next Work Order
```

The full lifecycle — its guiding principles, stage-by-stage description,
artifacts, and transition rules — is defined in the
[Engineering Lifecycle](engineering-lifecycle.md) specification.

The **Work Order** is the artifact that carries architectural intent into
implementation. Its canonical structure and the standard Implementation
Report it produces are defined in the
[Work Orders](work-orders.md) specification.

## Operating Model Specifications

This README is the entry point into the Operating Model. Detailed behavior
is defined in the following specifications:

- [Engineering Lifecycle](engineering-lifecycle.md) — the stages, artifacts,
  and transition rules that govern how work progresses.
- [Work Orders](work-orders.md) — the canonical interface between
  Architecture and Implementation.
- [Roles & Responsibilities](roles-and-responsibilities.md) — who
  participates in the lifecycle, and their responsibilities and authority.
- [Architecture Review](architecture-review.md) — how completed work is
  evaluated against approved architectural intent.
- [Release Management](release-management.md) — how approved work is
  integrated into AAOE's canonical knowledge.

## Future Specifications

This document establishes the Operating Model at v0.1: a map of AAOE's
engineering specifications, not a complete definition on its own. Additional
specifications may be introduced as AAOE evolves; this README will continue
to serve as their entry point.
