# Engineering Knowledge Reference Architecture

## Specification Metadata

**Specification ID:** ARCH-0003

**Domain:** Reference Architectures

**Version:** 1.0

**Status:** Draft

---

## Purpose

This specification describes how engineering knowledge exists within AAOE:
how it is created, governed, organized, evolved, and consumed. Engineering
knowledge is a governed engineering asset, not passive documentation — it
is produced, evaluated, and connected under the same governance that
applies to any other engineering artifact.

This is a logical architecture. It does not define repositories,
databases, search engines, documentation tools, or implementation
technologies.

## Architectural Principles

This architecture reuses principles already established elsewhere in
AAOE:

- Knowledge continuously evolves.
- Evidence precedes authority.
- Governance preserves knowledge.
- Traceability preserves context.
- Specifications define canonical guidance.

## Knowledge Types

- **Observations** — notable occurrences encountered during engineering
  work, the raw material knowledge begins from.
- **Discoveries** — observations captured as evidence-based, traceable
  records, as defined by the Discovery Lifecycle.
- **Architectural Decisions** — evaluated discoveries that have been
  approved as engineering direction, as defined by the Architectural
  Decision Lifecycle.
- **Specifications** — accepted decisions formalized into canonical
  guidance, as defined by the Specification Lifecycle.
- **Work Orders** — the scoped delegation of approved architecture into
  implementation.
- **Implementation Reports** — the standard record of what a Work Order
  produced.
- **Architecture Reviews** — the evaluation of an Implementation Report
  against architectural intent.
- **Releases** — the integration of approved work into canonical state, as
  defined by Release Management.
- **Reference Architectures** — reusable architectural patterns built on
  accepted specifications.
- **Case Studies** — evidence from applied AAOE work.
- **Guides** — practical adoption and contribution guidance.
- **Glossary** — shared terminology used consistently across all of the
  above.

## Knowledge Lifecycle

```text
Observation
        ↓
Discovery
        ↓
Decision
        ↓
Specification
        ↓
Implementation
        ↓
Validated Knowledge
```

Knowledge gains authority incrementally: an Observation carries no
authority on its own; a Discovery carries evidence; a Decision carries
approved direction; a Specification carries canonical guidance; and
Implementation, once reviewed and released, becomes Validated Knowledge
that can inform the next Observation. Each step is a governance boundary,
not an automatic progression — advancing requires the approval each
respective specification defines.

## Canonical Knowledge

Knowledge is canonical when it is:

- **Approved** — accepted through the governance defined for its type.
- **Governed** — subject to the rules of its owning specification.
- **Traceable** — connected to the evidence and authority that produced
  it, per the Traceability Model.
- **Versioned** — identifiable at a specific state, per the Specification
  Lifecycle.
- **Preserved** — retained through revision and supersession rather than
  overwritten.

## Knowledge Relationships

Every knowledge artifact references the artifact that justifies it —
Discoveries reference Observations, Decisions reference Discoveries,
Specifications reference Decisions, and so on, as defined by the
Traceability Model. Engineering knowledge therefore forms a connected
graph, not a collection of isolated documents: any artifact can be
understood by following its relationships back to what produced it.

## Knowledge Consumers

- **Human Architects** consume knowledge to ground new architectural
  intent in what is already approved.
- **Human Reviewers** consume knowledge to evaluate implementation against
  architectural intent.
- **Release Managers** consume knowledge to confirm integration criteria
  are met.
- **AI Agents** consume knowledge as the context delegated to them through
  a Work Order.
- **Future Engineering Tools** may consume knowledge to support work not
  yet anticipated by this architecture, without changing what canonical
  knowledge is.

## Knowledge Producers

- **Human Architects** produce architectural intent and Work Orders.
- **AI Agents** produce implementation output and Implementation Reports.
- **Reviews** produce approval decisions.
- **Releases** produce the canonical state that results from integration.

Producing knowledge does not imply authority over it. An artifact gains
authority only through the governance defined for its type, not through
the act of having produced it.

## Knowledge Governance

Knowledge is protected from uncontrolled evolution by the same governance
already established for each knowledge type: Discovery Governance,
Decision Governance, Specification Governance, Implementation Governance,
and Release Governance, as defined by the AAOE Meta-Model. This
architecture introduces no additional governance mechanism; it describes
how those existing mechanisms apply to knowledge as an asset.

## Extensibility

New knowledge types may be introduced as AAOE's domains grow, provided
each new type identifies its upstream authority and the governance that
applies to it, preserving the architectural consistency this specification
describes.

## Future Evolution

Engineering knowledge is expected to grow in volume and connection over
time. This growth must not break existing traceability or governance:
new knowledge extends the graph without severing the relationships that
already exist within it.
