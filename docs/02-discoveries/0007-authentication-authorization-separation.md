# Authentication and Authorization Separation

## Specification Metadata

**Specification ID:** DISC-0007

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Observation

During the SolOh ERP Modernization, authentication became simpler when
limited to identity verification. Authorization evolved independently
after authentication completed. Permission logic no longer complicated
authentication workflows. Identity and permission concerns changed for
different reasons and at different times. API boundaries became clearer
after separating these responsibilities.

## Context

These observations occurred during the SolOh ERP Modernization, in the
API Contracts and Authentication Specifications produced for the
Authentication vertical slice. [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)
is the primary evidence source for this Discovery.

## Evidence

- Authentication APIs became smaller once scoped to identity verification
  alone.
- Authorization evolved independently of authentication once separated.
- Permission changes no longer required authentication redesign.
- Identity verification became easier to test in isolation.
- Security responsibilities became easier to trace to a specific concern.

## Discovery

Identity verification and permission evaluation represent distinct
engineering concerns. Treating authentication and authorization as
independent capabilities produced simpler interfaces and reduced
architectural coupling.

## Why It Matters

This observation appears generally applicable beyond SolOh:

- **Separation of concerns** — identity verification and permission
  evaluation change for different reasons and can be reasoned about
  independently.
- **Maintainability** — a change to one concern did not require revisiting
  the other.
- **Security traceability** — a given security responsibility could be
  traced to a single, clearly scoped capability.
- **API stability** — authentication interfaces stabilized independently
  of how authorization evolved.
- **Independent evolution** — authorization policy could change without
  authentication being affected, and vice versa.
- **Testing** — identity verification could be tested in isolation from
  permission logic.

## Consequences

- Authentication APIs stabilize independently.
- Authorization policies evolve separately.
- Security responsibilities become more explicit.
- Permission models become reusable.
- Identity verification becomes easier to validate.

## Related Evidence

Case Studies

- [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)

## Related Specifications

This Discovery is referenced by, and later generalized into, the
following AAOE specifications:

- [Engineering Lifecycle](../03-operating-model/0001-engineering-lifecycle.md)
- [Work Orders](../03-operating-model/0002-work-orders.md)

It also motivated Authentication Specifications and API Contracts produced
during SolOh; neither is yet published as a general AAOE specification in
this repository.

## Future Evolution

Future Case Studies may validate, refine, or challenge this Discovery.
Engineering Discoveries evolve through accumulated evidence, not through
revision of this record's original observation.
