# Engineering Lifecycle

**Specification ID:** OM-0001

**Domain:** Operating Model

**Version:** 1.0

**Status:** Draft

**Last Updated:** 2026-07-28

## Purpose

AAOE defines an engineering lifecycle so that architectural intent reaches
implementation, and implementation returns to approved knowledge, through a
repeatable path rather than an ad hoc one. The lifecycle gives every
engineering task the same shape: a predictable sequence from intent to
approval that can be followed, reviewed, and improved over time.

This specification expands the lifecycle introduced in the
[Operating Model](README.md#engineering-lifecycle) into its canonical
stages, artifacts, and transition rules. It relies on the
[Work Order](0002-work-orders.md) as the artifact that carries architectural
intent into implementation, without redefining it here.

## Guiding Principles

- Architecture precedes implementation.
- Every implementation begins from approved knowledge.
- Work progresses through explicit stages; no stage is skipped or assumed.
- Each stage produces reviewable artifacts.
- Approval is required before work advances to the next stage.
- Canonical knowledge evolves incrementally, one Task at a time.
- Human governance is maintained throughout the lifecycle.

## Lifecycle Overview

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

- **Architecture** — architectural intent is established or extended,
  grounded in existing approved knowledge.
- **Work Order** — that intent is expressed as a Work Order, scoping a
  single Task for implementation.
- **Implementation** — the Work Order is carried out within its stated
  scope and constraints.
- **Implementation Report** — the result is reported in the Work Order's
  standard format, giving reviewers a consistent artifact to evaluate.
- **Architecture Review** — the reported result is evaluated against the
  originating architectural intent.
- **Approval** — a human reviewer accepts the result, or sends it back for
  revision.
- **Merge** — approved work is integrated into the release branch, becoming
  part of the canonical state.
- **Next Work Order** — the lifecycle repeats, with the next Task starting
  from this newly approved state.

## Lifecycle Artifacts

- **Architecture** — the intent and direction a Task must serve; the source
  from which a Work Order is derived.
- **Task** — the discrete unit of work the lifecycle moves through one
  cycle at a time.
- **Work Order** — the canonical interface handing a Task to
  implementation, as defined in the Work Order specification.
- **Implementation Report** — the standard record of what was done,
  produced at the close of implementation.
- **Pull Request** — the reviewable proposal to integrate implementation
  output into the release branch.
- **Approved Merge** — the point at which proposed work becomes accepted
  canonical knowledge.

## Transition Rules

- A Work Order may only be created from approved architecture.
- An Implementation Agent may only execute an approved Work Order.
- Architecture Review evaluates artifacts produced by implementation, not
  implementation metadata or process.
- A Task is complete only after its Pull Request has been approved and
  merged into the release branch.
- Every new Task begins from the latest approved release state.

## Future Evolution

Additional lifecycle stages, artifacts, or transition rules may be
introduced as AAOE evolves. Such changes are expected to preserve the
fundamental governance principles established here: architecture before
implementation, explicit stages, reviewable artifacts, and human approval.
