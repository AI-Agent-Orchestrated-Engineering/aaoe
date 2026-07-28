# AAOE Operating Model

- **Status:** Draft (v0.1)
- **Date:** 2026-07-28

## Purpose

The Operating Model describes how AAOE engineering work is organized: how
responsibilities are divided between the people and agents involved, and how
architecture becomes implementation. It gives future specifications a shared
frame of reference so that detailed workflows, roles, and governance rules
can be defined consistently rather than improvised per task.

This document does not restate the decisions already recorded in
[`docs/00-governance/decisions`](../00-governance/decisions/README.md). It
builds on them.

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

AAOE work is organized around three high-level roles. Their detailed
responsibilities, interfaces, and boundaries are left to future
specifications.

- **Chief Architect** — sets direction, defines work orders, and reviews
  implementation against architectural intent.
- **Implementation Agent** — carries out a work order and produces a
  reviewable result.
- **Human Orchestrator** — coordinates the flow of work between architecture
  and implementation, and holds final approval authority.

## Engineering Lifecycle

At a high level, AAOE engineering work moves through the following stages:

```text
Architecture
  ↓
Work Order
  ↓
Implementation
  ↓
Architecture Review
  ↓
Approval
  ↓
Next Work Order
```

Each stage produces an artifact the next stage can act on, and each cycle
feeds the next work order rather than terminating the lifecycle.

## Future Specifications

This document establishes the Operating Model at v0.1: an introduction, not a
complete definition. Detailed roles, workflows, review criteria, and
governance mechanics will be defined by future specifications that build on
this foundation.
