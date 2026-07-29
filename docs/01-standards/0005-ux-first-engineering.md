# UX-First Engineering

## Specification Metadata

**Specification ID:** STD-0005

**Domain:** Standards

**Version:** 1.0

**Status:** Draft

---

# Purpose

This Standard defines UX-First Engineering as the preferred engineering
approach for developing user-facing systems.

Engineering decisions should begin with validated user interactions before
implementation interfaces are designed.

---

# Standard

Engineering teams shall define the intended user experience before
designing APIs, services, or implementation details whenever practical.

User experience becomes the authoritative reference for subsequent
technical design.

Technical implementation shall support the intended user experience.

---

# Principles

UX-First Engineering shall:

- prioritize user outcomes
- reduce implementation rework
- improve engineering alignment
- improve collaboration between design and engineering
- improve implementation consistency
- improve AI-assisted implementation
- preserve traceability from user intent to implementation

---

# Required Artifacts

User-facing engineering should have, where applicable:

- UX Specification
- User Flows
- Wireframes or Mockups
- Interaction Specifications
- Acceptance Criteria

Artifacts should be proportionate to project complexity.

---

# Engineering Workflow

The preferred engineering sequence is:

```text
User Needs
        ↓
UX Specification
        ↓
Architecture Review
        ↓
API & Technical Design
        ↓
Implementation
        ↓
Validation
```

Implementation details should derive from validated UX.

---

# Traceability

User-facing implementations should remain traceable to:

- UX Specifications
- Functional Specifications
- Discoveries
- Standards
- Architecture Decisions

Implementation should preserve user intent.

---

# Exceptions

Systems without direct user interaction may not require UX artifacts.

Infrastructure, integration, and platform components may begin with
technical specifications when no user experience exists.

---

# Relationship to Discoveries

This Standard operationalizes
[DISC-0003 — UX Before API](../02-discoveries/0003-ux-before-api.md).

The Discovery explains why this approach emerged. This Standard defines
how engineering teams apply it.

---

# Relationship to the Operating Model

The Operating Model applies this Standard through:

- UX Specifications
- Work Orders
- Architecture Reviews
- Technical Specifications
- Implementation Reports

---

# Compliance

Engineering work conforms to this Standard when:

- UX is defined before technical implementation.
- Technical design supports the intended user experience.
- Traceability from UX to implementation is preserved.
- Exceptions are explicitly documented.

---

# Future Evolution

Future Standards may define:

- UX Specification Templates
- Interaction Modeling
- UX Validation Practices
- AI-Assisted UX Engineering
- Cross-Platform UX Governance
