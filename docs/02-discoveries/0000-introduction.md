# Discoveries

## Specification Metadata

**Specification ID:** DISC-0000

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Purpose

Discoveries exist so that engineering observations are preserved before
they become architecture or standards. Without a place to capture them,
observations made during real work are easily lost once the task that
produced them ends — and the same engineering knowledge tends to be
rediscovered, at cost, by the next team that encounters it.

## What Is a Discovery?

A Discovery is evidence-based engineering knowledge captured from
practical work: an observation, recorded with the evidence behind it, so
it can later be evaluated and, if warranted, formalized.

A Discovery is:

- **not** an Architectural Decision — it carries no authority on its own.
- **not** a Specification — it does not define canonical guidance.
- **not** an implementation artifact — it is knowledge about engineering
  work, not the work's output.

## Why Discoveries Matter

Organizations repeatedly rediscover the same engineering knowledge, because
observations made during one initiative are rarely captured in a form the
next initiative can reuse. AAOE preserves those observations as Discoveries
so they become reusable organizational assets, available to inform future
architecture rather than being relearned each time.

## Relationship to Other Domains

- **Case Studies** — provide the evidence Discoveries are drawn from, and
  the domain to which validated Discoveries eventually trace back once
  applied in practice.
- **Architectural Decisions** — evaluate Discoveries and, if warranted,
  approve a direction in response to them.
- **Specifications** — formalize the authority an Architectural Decision
  created, not the Discovery directly.
- **Reference Architectures** — draw on accepted Specifications to describe
  reusable architectural patterns.
- **Operating Model** — defines the lifecycle and artifacts, including the
  Work Order, through which a Discovery's downstream Architectural
  Decisions and Specifications are eventually implemented.

## Discovery Journey

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
        ↓
Reference Architecture
        ↓
Case Study
```

Case Studies also generate new observations, so this journey is iterative
rather than linear: applying a Specification or Reference Architecture in
practice produces the next generation of observations, which may in turn
become new Discoveries.

## Governance

Discoveries carry no authority by themselves. They are evidence, not
approval. Authority comes only after validation through AAOE governance —
an Architectural Decision that evaluates the Discovery and, if accepted,
grants it standing.

## Relationship with Discovery Lifecycle

This Introduction describes the purpose of the Discoveries domain: why it
exists, what a Discovery is, and how it relates to the rest of AAOE. The
[Discovery Lifecycle](0001-discovery-lifecycle.md) specification defines
the lifecycle governing individual Discovery records — their sources,
states, and criteria. This document does not duplicate that lifecycle; it
introduces the domain the lifecycle governs.

## Future Evolution

This domain is expected to expand as engineering knowledge is validated
through future AAOE projects, including the individual Discovery records
that formalize the observations already summarized in existing Case
Studies.
