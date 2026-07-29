# Specification-Driven Development

## Specification Metadata

**Specification ID:** STD-0002

**Domain:** Standards

**Version:** 1.0

**Status:** Draft

---

# Purpose

This Standard defines Specification-Driven Development (SDD) as the
standard engineering approach within AAOE. Engineering work shall be
driven by explicit Specifications before implementation begins.

---

# Standard

Engineering teams shall define Specifications before implementing
software.

Specifications become the authoritative engineering reference throughout
implementation.

Implementation shall conform to Specifications unless governed change is
approved.

---

# Principles

Specification-Driven Development shall:

- separate design from implementation
- establish shared understanding
- reduce ambiguity
- improve consistency
- improve AI collaboration
- improve human collaboration
- improve traceability

---

# Required Artifacts

Every implementation should have, where applicable:

- Functional Specification
- Technical Specification
- UX Specification
- Architecture Specification
- Acceptance Criteria

Artifacts should be proportionate to project complexity.

---

# Engineering Workflow

The preferred engineering sequence is:

```text
Requirements
        ↓
Specifications
        ↓
Architecture Review
        ↓
Implementation
        ↓
Validation
```

Implementation should not precede Specification except when performing
explicitly identified exploratory work.

---

# Traceability

Implementation should remain traceable to:

- Specifications
- Discoveries
- ADRs
- Case Studies

Specifications should identify the engineering problem they solve.

---

# Exceptions

Exploratory prototypes may temporarily precede Specifications.

When exploratory work produces valuable engineering knowledge,
Specifications should subsequently be created before production
implementation.

---

# Relationship to Discoveries

This Standard operationalizes
[DISC-0002 — Specification-Driven Development](../02-discoveries/0002-specification-driven-development.md).

The Discovery explains why this approach emerged. This Standard defines
how engineering teams apply it.

---

# Relationship to the Operating Model

The Operating Model applies this Standard through:

- Work Orders
- Architecture Reviews
- Implementation Reports

---

# Compliance

Engineering work conforms to this Standard when:

- Specifications precede implementation.
- Specifications remain the authoritative reference.
- Traceability is preserved.
- Exceptions are explicitly documented.

---

# Future Evolution

Future Standards may define:

- Specification Templates
- Specification Quality Criteria
- Domain-specific Specification Standards
