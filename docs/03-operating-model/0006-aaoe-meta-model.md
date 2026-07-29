# AAOE Meta-Model

## Specification Metadata

**Specification ID:** OM-0006

**Domain:** Operating Model

**Version:** 1.0

**Status:** Draft

---

## Purpose

The AAOE Meta-Model is an architectural view of the methodology, not
another lifecycle. It introduces no new engineering concepts. Instead, it
consolidates the specifications AAOE has already established into a single
model that explains how AAOE operates end-to-end: how its domains relate,
which concepts each governs, and how engineering evidence flows from
observation to organizational knowledge.

It is the architectural blueprint of the methodology — the map that shows
how the previously independent specifications form one coherent system.

## Core Domains

AAOE organizes its knowledge into domains, as established by the
repository taxonomy:

- **Governance** — the specifications and records that govern how AAOE's
  engineering knowledge is decided, recorded, and evolved.
- **Operating Model** — how AAOE engineering work is organized: the
  lifecycle, its artifacts, its roles, and how work is reviewed and
  released.
- **Standards** — the catalogue of accepted specifications, including how
  specifications themselves are governed.
- **Discoveries** — validated and emerging engineering observations that
  precede architecture and specification.
- **Reference Architectures** — reusable architectural patterns and models
  drawn from accepted specifications.
- **Case Studies** — evidence from applied AAOE work.
- **Guides** — practical adoption and contribution guidance.
- **Glossary** — shared terminology used consistently across domains.

## Governed Concepts

AAOE's specifications govern a small set of recurring engineering concepts:

- **Engineering Work** — governed by the Engineering Lifecycle, Work
  Orders, Roles & Responsibilities, and Architecture Review specifications.
- **Discovery** — governed by the Discovery Lifecycle specification.
- **Architectural Decision** — governed by the Architectural Decision
  Lifecycle specification.
- **Specification** — governed by the Specification Lifecycle
  specification.
- **Traceability** — governed by the Traceability Model specification.
- **Release** — governed by the Release Management specification.

## Engineering Knowledge Graph

```text
Observation
        ↓
Discovery
        ↓
Architectural Decision
        ↓
Specification
        ↓
Work Order
        ↓
Implementation
        ↓
Implementation Report
        ↓
Architecture Review
        ↓
Release
        ↓
Organizational Knowledge
```

- **Observation → Discovery** — something notable is captured as a
  Discovery, as defined by the Discovery Lifecycle.
- **Discovery → Architectural Decision** — a validated Discovery informs a
  proposed Decision, as defined by the Architectural Decision Lifecycle.
- **Architectural Decision → Specification** — an accepted Decision is
  formalized into a Specification, as defined by the Specification
  Lifecycle.
- **Specification → Work Order** — a Specification, together with the
  architecture built on it, scopes a Work Order, as defined by the Work
  Orders specification.
- **Work Order → Implementation** — the Work Order is executed within its
  stated scope, as defined by the Engineering Lifecycle.
- **Implementation → Implementation Report** — the result is reported in
  the Work Order's standard format.
- **Implementation Report → Architecture Review** — the report is
  evaluated against architectural intent, as defined by the Architecture
  Review specification.
- **Architecture Review → Release** — an approved review allows the work
  to be integrated, as defined by Release Management.
- **Release → Organizational Knowledge** — integrated work becomes part of
  AAOE's canonical knowledge, available to inform future Observations.

This graph is the Traceability Model's chain, expanded to make the
Implementation stage explicit and to close the loop from Release back into
the knowledge that future work draws on.

## Governance Layers

Each stage of the knowledge graph has a corresponding governance layer,
defined by its respective specification:

- **Discovery Governance** — defined by the Discovery Lifecycle: discoveries
  carry no authority on their own and do not change specifications
  directly.
- **Decision Governance** — defined by the Architectural Decision
  Lifecycle: every accepted decision is recorded, and ADRs never replace
  specifications.
- **Specification Governance** — defined by the Specification Lifecycle:
  specifications evolve through governance, never unilateral edits.
- **Implementation Governance** — defined by Work Orders, Roles &
  Responsibilities, and Architecture Review: implementation stays within
  scope, and Implementation Agents never approve their own work.
- **Release Governance** — defined by Release Management: only approved
  work becomes canonical, and integration preserves history.

## Architectural Views

AAOE can be read from four viewpoints. Each describes the same system from
a different perspective; none introduces a separate methodology.

### Process View

Focuses on engineering execution: the Engineering Lifecycle's stages, the
Work Order as the interface between Architecture and Implementation, and
the roles that carry each stage out.

### Knowledge View

Focuses on how engineering knowledge evolves: Discoveries becoming
Architectural Decisions, and Decisions becoming Specifications.

### Governance View

Focuses on authority and decision-making: who may approve what, and the
Governance Layers that apply at each stage of the knowledge graph.

### Traceability View

Focuses on engineering lineage: the evidence chain defined by the
Traceability Model, connecting any artifact back to what justified it.

## Relationships Between Specifications

- The **Engineering Lifecycle** (OM-0001) is the process every Work Order
  follows; **Work Orders** (OM-0002) is the artifact that carries
  architectural intent into that process.
- **Roles & Responsibilities** (OM-0003) defines who acts at each stage of
  the Engineering Lifecycle.
- **Architecture Review** (OM-0004) and **Release Management** (OM-0005)
  define the lifecycle's final stages: evaluation and integration.
- The **Discovery Lifecycle** (DISC-0001) supplies the evidence that the
  **Architectural Decision Lifecycle** (GV-0001) evaluates.
- The **Architectural Decision Lifecycle** (GV-0001) produces the authority
  that the **Specification Lifecycle** (STD-0001) formalizes.
- The **Traceability Model** (GV-0002) describes the relationships that
  connect all of the above into one evidence chain.

This Meta-Model does not restate any of these specifications; it shows how
they compose.

## Design Principles

The following principles have already been established across AAOE's
specifications and hold consistently across the whole system:

- Evidence precedes authority.
- Authority precedes specification.
- Specification precedes implementation.
- Every governed artifact is traceable.
- Governance preserves engineering knowledge.
- Knowledge continuously evolves.

## Future Evolution

The Meta-Model is expected to evolve as new AAOE domains and specifications
are introduced, while preserving the architectural consistency it
describes: one system, read from multiple views, governed by one set of
principles.
