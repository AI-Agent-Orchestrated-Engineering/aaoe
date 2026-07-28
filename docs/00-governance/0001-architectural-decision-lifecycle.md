# Architectural Decision Lifecycle

## Specification Metadata

**Specification ID:** GV-0001

**Domain:** Governance

**Version:** 1.0

**Status:** Draft

---

## Purpose

Architectural Decisions exist to transform validated discoveries into
approved engineering direction. They are the point at which evidence
becomes authority: a decision that AAOE work is expected to follow going
forward.

An Architectural Decision is not the same as its record. The decision is
the act of evaluating evidence and approving a direction; an Architecture
Decision Record (ADR) is the persistent artifact that records an accepted
decision and its rationale. This specification governs the decision-making
process itself, not the record format.

## Principles

- Decisions are evidence-driven, grounded in validated discoveries.
- Decisions are traceable to the evidence and reasoning behind them.
- Decisions precede specifications; a specification formalizes what a
  decision has already approved.
- Decisions are governed, not made unilaterally.
- Decisions are explicitly recorded once accepted.
- Decisions preserve rationale, not only the outcome.

## Decision States

```text
Proposed
        ↓
Under Review
        ↓
Accepted
        ↓
Revised
        ↓
Superseded
        ↓
Archived
```

- **Proposed** — a decision is put forward, grounded in discoveries or
  other evidence.
- **Under Review** — the proposal is evaluated for evidence, consistency,
  and consequence.
- **Accepted** — the decision is approved and carries architectural
  authority from this point.
- **Revised** — an accepted decision is incrementally updated while
  retaining its identity and history.
- **Superseded** — a later decision replaces its authority.
- **Archived** — the decision is retained for historical reference only.

## Lifecycle

```text
Discovery
        ↓
Decision Proposal
        ↓
Review
        ↓
Accepted Decision
        ↓
ADR Published
        ↓
Specification
```

- **Discovery** — a validated observation, as defined by the Discovery
  Lifecycle, provides the evidence a decision responds to.
- **Decision Proposal** — a direction is proposed in response to that
  evidence.
- **Review** — the proposal is evaluated against the evidence and existing
  architecture.
- **Accepted Decision** — the proposal is approved. Acceptance is the
  point at which architectural authority is created.
- **ADR Published** — the accepted decision is recorded as an ADR,
  documenting that authority and its rationale for the future.
- **Specification** — a specification may then implement the authority the
  decision established, as defined by the Specification Lifecycle.

Acceptance creates architectural authority; publishing an ADR records that
authority; specifications implement it. Each step depends on the one
before it.

## Relationships

- **Discoveries** supply the evidence that decision proposals respond to.
- **ADRs** are the persistent record of accepted decisions and their
  rationale.
- **Specifications** derive their authority from accepted decisions and
  formalize it into canonical guidance.
- **Work Orders** are scoped in accordance with accepted decisions and the
  specifications that implement them.
- **Architecture Reviews** evaluate implementation against the
  architectural intent that accepted decisions established.

## Governance

- Every accepted decision is recorded.
- ADRs never replace specifications; a record of authority is not the same
  as the guidance that implements it.
- Specifications derive authority from accepted decisions, not the reverse.
- Superseded decisions remain part of engineering history rather than
  being deleted.

## Outputs

- Accepted decisions.
- ADRs.
- Candidate specifications.
- Architectural rationale.

## Future Evolution

Decision governance may evolve — for example, in how proposals are
reviewed or accepted — while preserving traceability, evidence, and
rationale as its foundation.
