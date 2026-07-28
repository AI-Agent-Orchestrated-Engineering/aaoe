# UX Before API

## Specification Metadata

**Specification ID:** DISC-0003

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Observation

During the SolOh ERP Modernization, API design became simpler after UX
specifications were completed. User journeys clarified the business
operations a feature needed to support, and screen behavior naturally
revealed API boundaries. Database contracts became a consequence of API
contracts rather than their starting point. Designing APIs first often
introduced assumptions that later conflicted with the desired user
experience.

## Context

These observations occurred during the SolOh ERP Modernization, in the
work on UX Specifications and Design System artifacts that preceded the
Authentication vertical slice. [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)
is the evidence source for this Discovery.

## Evidence

- UX specifications consistently reduced the amount of API redesign
  needed later.
- Screen behavior identified business operations that were otherwise
  missing from early API drafts.
- API contracts became clearer once interaction design had stabilized.
- Backend implementation required fewer revisions after UX approval.
- Database contracts aligned more naturally with business intent when they
  followed, rather than preceded, API design.

## Discovery

The user experience defines the business interactions a system must
support. Designing the user experience before APIs produces interfaces
that more accurately reflect business intent.

## Why It Matters

This observation appears generally applicable beyond SolOh:

- **Business alignment** — interfaces designed after user interaction is
  understood reflect what the business actually needs, rather than
  assumptions made ahead of that understanding.
- **Interface stability** — API contracts drafted after UX has stabilized
  changed less often during implementation.
- **Traceability** — API boundaries can be traced back to specific user
  journeys, rather than to assumptions made independently of them.
- **Reduced rework** — fewer conflicts emerged between the interface and
  the experience it was meant to support.
- **Architectural clarity** — the sequence in which contracts were
  designed correlated with how well those contracts held up during
  implementation.

## Consequences

- APIs emerge from validated user interactions rather than preceding them.
- Business intent becomes explicit earlier in the design process.
- API contracts stabilize sooner.
- Downstream implementation requires fewer revisions.
- Database contracts become implementation consequences rather than
  design drivers.

## Related Evidence

Case Studies

- [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)

## Related Specifications

This Discovery is referenced by, and later generalized into, the
following AAOE specifications:

- [Engineering Lifecycle](../03-operating-model/0001-engineering-lifecycle.md)
- [Work Orders](../03-operating-model/0002-work-orders.md)
- [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md)

It also motivated the AAOE Feature Delivery Lifecycle (AFDL), a
specification not yet published in this repository.

## Future Evolution

Future Case Studies may validate, refine, or challenge this Discovery.
Engineering Discoveries evolve through additional evidence, not through
revision of this record's original observation.
