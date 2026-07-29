# Work Orders

**Specification ID:** OM-0002

**Domain:** Operating Model

**Version:** 1.0

**Status:** Draft

**Last Updated:** 2026-07-28

## Purpose

A Work Order is the canonical interface between Architecture and
Implementation in the [AAOE engineering lifecycle](README.md#engineering-lifecycle).

It is the artifact through which architectural intent is handed to an
Implementation Agent: what the agent receives, what it is expected to
produce, the boundaries of its responsibility, how it reports its work, and
when it must stop. Standardizing this artifact lets architecture and
implementation stay decoupled while remaining traceable to one another.

## Principles

- One Work Order belongs to exactly one Task.
- One Work Order has one objective.
- Scope must be explicit.
- Constraints must be explicit.
- Architecture is never inferred; it is stated in the Work Order or in the
  canonical sources it references.
- Implementation stays within scope. Work outside the stated scope belongs
  to a future Work Order, not the current one.
- Every Work Order produces reviewable artifacts.
- Every Work Order has a clear stopping point.

## Standard Structure

A Work Order is expressed using the following canonical sections.

- **Release** — the release the Task belongs to, anchoring the work to a
  point in the roadmap.
- **Epic** — the higher-level initiative the Task serves, giving the work
  its broader purpose.
- **Task** — the specific unit of work the Work Order covers.
- **Objective** — the single, explicit outcome the Work Order exists to
  achieve.
- **Context** — the prior decisions, state, and constraints the
  Implementation Agent needs to act without inferring architecture.
- **Workflow** — the ordered phases the Implementation Agent must follow,
  when a Task requires more than direct implementation.
- **Scope** — precisely what is, and is not, included in the Work Order.
- **Constraints** — explicit boundaries on how the objective may be
  achieved.
- **Validation** — how the Implementation Agent, or a reviewer, can confirm
  the result meets the objective.
- **Git** — the version-control actions expected of the Implementation
  Agent, including whether a Pull Request is created and whether it may be
  merged.
- **Deliverables** — the exact report the Implementation Agent must return.
- **Stop Condition** — the point at which the Implementation Agent's
  responsibility ends and the Work Order is considered fulfilled.

## Implementation Report

Every Work Order is answered with a standard Implementation Report, so that
Architecture Review can evaluate results without re-deriving them from raw
output.

- **Summary** — a concise account of what was done and why.
- **Folder Tree** — the affected portion of the repository structure, for
  quick spatial orientation.
- **Files Created** — every new file introduced.
- **Files Modified** — every existing file changed.
- **Files Deleted** — every file removed.
- **Pull Request URL** — the reviewable artifact produced, when a Pull
  Request is part of the Work Order.
- **Notes** — relevant observations that do not fit elsewhere, including
  deviations or environment issues encountered.
- **Questions** — anything the Implementation Agent could not resolve
  within scope and must raise back to Architecture.

## Future Evolution

Work Orders are expected to evolve as AAOE matures. Additional sections,
refined structure, and tighter validation may be introduced by future
specifications. Changes should preserve backward compatibility with this
structure whenever practical, so that existing Work Orders remain
interpretable.
