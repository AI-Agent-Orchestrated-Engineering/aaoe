# Architecture Review

- **Status:** Draft (v0.1)
- **Date:** 2026-07-28

## Purpose

Architecture Review is the stage of the
[Engineering Lifecycle](engineering-lifecycle.md) at which completed work is
evaluated before it can become part of AAOE's canonical knowledge. It
protects architectural integrity by validating that implementation
faithfully realizes approved architectural intent, while leaving the
Implementation Agent free to determine how that intent is carried out.

Architecture Review is not a code review, style review, or tool review.

## Principles

- Architecture is reviewed, not implementation style.
- Reviews evaluate outcomes against intent.
- Reviews are evidence-based, grounded in the artifacts produced.
- Architectural decisions already approved are respected, not relitigated.
- Human governance is authoritative.

## Inputs

- The approved [Work Order](work-orders.md) that scoped the work.
- The Implementation Report produced in response to it.
- The architectural intent the Work Order was derived from.
- The artifacts produced by implementation (e.g. the resulting Pull
  Request).

## Review Scope

Architecture Review evaluates:

- Scope compliance — whether implementation stayed within the Work Order's
  stated scope.
- Architectural fidelity — whether the result faithfully realizes the
  approved architectural intent.
- Deliverables — whether the required Implementation Report and artifacts
  were produced.
- Constraints — whether the Work Order's explicit constraints were
  respected.
- Specification compliance — whether the result is consistent with
  applicable AAOE specifications.

## Out of Scope

Architecture Review does not evaluate:

- Coding style
- AI prompts
- Personal preferences
- Tool choice
- IDE configuration

unless explicitly required by architecture.

## Review Outcomes

Architecture Review produces exactly one of the following outcomes.

### Approved

Implementation satisfies architectural intent. The Task may proceed to
Merge.

### Approved with Recommendations

Implementation satisfies architectural intent and is acceptable as-is.
Recommendations may improve future work but are not required before Merge.

### Revision Required

Implementation does not sufficiently satisfy approved architecture. A
revised implementation is required before approval can be granted.

## Outputs

- An Approval Decision (one of the outcomes above).
- Recommendations, when applicable.
- Revision Requests, when applicable.

## Governance

- Reviewers do not redefine architecture; disagreement with architectural
  intent is raised as a separate architectural decision, not resolved
  within a review.
- Reviewers evaluate against approved specifications, not personal
  judgment alone.
- New architecture requires a separate architectural decision; it cannot
  be introduced through a review outcome.
- Implementation Agents do not participate in approval decisions.

## Future Evolution

Review criteria may expand as AAOE evolves, while preserving these
principles: architecture over style, evidence over opinion, and human
governance over automated judgment.
