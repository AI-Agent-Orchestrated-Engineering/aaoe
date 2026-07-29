# Discovery Lifecycle

## Specification Metadata

**Specification ID:** DISC-0001

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Purpose

Engineering discoveries exist so that observations made during real work
can become reusable organizational knowledge rather than being lost once
the task that produced them is done. A Discovery is the first formal
representation of newly acquired engineering knowledge: it precedes
architectural decisions, specifications, and implementation.

A Discovery is not yet architecture and not yet a standard. It is an
observation, captured and preserved so it can later be evaluated,
validated, and — if warranted — formalized.

## Principles

- Discoveries originate from evidence, not speculation.
- Discoveries describe observations before prescribing solutions.
- Multiple discoveries may lead to one architectural decision.
- Discoveries remain traceable to the work that produced them.
- Discoveries preserve engineering learning, whether or not they are
  ultimately formalized.

## Discovery Sources

Discoveries may originate from:

- Practical implementation
- Experiments
- Production incidents
- Architecture reviews
- User feedback
- Performance investigations
- Research

## Discovery Lifecycle

```text
Observation
        ↓
Discovery
        ↓
Validation
        ↓
Architectural Decision
        ↓
Specification
```

- **Observation** — something notable is encountered during engineering
  work, from any of the sources above.
- **Discovery** — the observation is captured as a Discovery: recorded,
  evidence-based, and traceable to its source.
- **Validation** — the Discovery is examined for reproducibility and
  general applicability beyond the situation that produced it.
- **Architectural Decision** — a validated Discovery may lead to an
  architectural decision that evaluates and responds to it.
- **Specification** — an accepted architectural decision may in turn be
  formalized into a specification.

## Discovery Criteria

A Discovery should:

- Be evidence-based.
- Be reproducible.
- Be generally applicable.
- Be independent of tooling whenever possible.

## Outputs

- Candidate architectural decisions.
- Candidate specifications.
- Engineering insights.
- Organizational learning.

## Governance

- Discoveries are not automatically architecture.
- Discoveries do not change specifications directly.
- Architectural decisions evaluate discoveries; a Discovery does not carry
  authority on its own.
- Specifications formalize approved discoveries, not raw observations.

## Future Evolution

Discovery management may evolve — for example, in how discoveries are
recorded, validated, or connected to downstream decisions — while
preserving evidence-first engineering as its foundation.
