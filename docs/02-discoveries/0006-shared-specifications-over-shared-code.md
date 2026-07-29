# Shared Specifications Over Shared Code

## Specification Metadata

**Specification ID:** DISC-0006

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Observation

During the SolOh ERP Modernization, specialized AI agents rarely depended
on each other's implementation. Shared specifications coordinated
implementation more effectively than shared source code. Independent
implementations remained consistent when specifications were stable.
Implementation divergence decreased as specifications matured.
Architectural consistency emerged from common specifications rather than
from shared implementation history.

## Context

These observations occurred during the SolOh ERP Modernization, across
specialized AI agents working on the Authentication vertical slice and
elsewhere, coordinated through Work Orders and specification-first
engineering. [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)
is the primary evidence source for this Discovery.

## Evidence

- Multiple agents implemented different repository areas from the same
  specification.
- Code reviews increasingly verified compliance with specifications rather
  than implementation similarity to other agents' work.
- Repository documentation reduced the need to inspect existing code
  before implementing new work.
- API Contracts and UX Specifications coordinated implementation across
  repositories.
- Engineering discussions increasingly referenced specifications instead
  of source files.

## Discovery

Shared engineering specifications provide a more scalable coordination
mechanism than shared implementation code. Implementation consistency
correlates more strongly with specification alignment than with
implementation familiarity.

## Why It Matters

This observation appears generally applicable beyond SolOh:

- **Scalability** — a specification can coordinate any number of agents
  at once, while shared implementation history does not scale the same
  way.
- **Parallel engineering** — agents implementing different parts of a
  system from the same specification did not need to wait on or inspect
  each other's work.
- **Specialization** — agents could specialize around distinct
  responsibilities without needing a common implementation background.
- **Traceability** — implementation can be checked against a specification
  directly, rather than against another implementation's history.
- **Organizational knowledge** — specifications persist and remain
  referenceable after the implementation that first used them.
- **Onboarding** — a new agent or contributor could coordinate through the
  same specifications without first learning existing code.
- **Implementation independence** — different implementations of the same
  specification remained consistent with one another without sharing code.

## Consequences

- Teams coordinate through shared engineering knowledge.
- Code becomes an implementation outcome rather than the primary source of
  coordination.
- Parallel implementation becomes more practical.
- AI agents specialize without requiring shared implementation history.
- Repository documentation becomes a first-class collaboration mechanism.

## Related Evidence

Case Studies

- [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)

## Related Specifications

This Discovery is referenced by, and later generalized into, the
following AAOE specifications:

- [Work Orders](../03-operating-model/0002-work-orders.md)
- [Engineering Lifecycle](../03-operating-model/0001-engineering-lifecycle.md)
- [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md)
- [Specification Lifecycle](../01-standards/0001-specification-lifecycle.md)

It is also closely related to
[Context Engineering](0005-context-engineering.md), and may inform a
future Context Engineering Specification, not yet published in this
repository.

## Future Evolution

Future Case Studies may validate, refine, or challenge this Discovery.
Engineering Discoveries evolve through accumulated evidence, not through
revision of this record's original observation.
