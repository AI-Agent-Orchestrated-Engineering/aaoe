# Design Systems Before Screens

## Specification Metadata

**Specification ID:** DISC-0004

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Observation

During the SolOh ERP Modernization, defining reusable components before
screens reduced UI inconsistency. Screen design accelerated once component
behavior had stabilized. Accessibility requirements became easier to apply
consistently. Design discussions shifted from individual screens toward
reusable patterns. UI implementation became more predictable because
screens assembled existing components instead of inventing new ones.

## Context

These observations occurred during the SolOh ERP Modernization, in the
UX Specification, Design System creation, and component catalog work that
preceded screen implementation on the Authentication vertical slice.
[CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)
is the evidence source for this Discovery.

## Evidence

- Components were reused across multiple screens.
- Changes to component behavior propagated consistently to every screen
  that used them.
- Accessibility improvements benefited every consuming screen at once.
- Developers implemented screens faster once the component library
  stabilized.
- UX reviews focused on workflows instead of visual inconsistencies.

## Discovery

Reusable interface components provide a more stable engineering foundation
than individual screen designs. Establishing the Design System before
individual screens improves consistency, reuse, and implementation
predictability.

## Why It Matters

This observation appears generally applicable beyond SolOh:

- **Consistency** — interfaces built from the same components look and
  behave uniformly, rather than diverging screen by screen.
- **Accessibility** — a fix or improvement applied to a component reaches
  every screen that consumes it.
- **Reuse** — screens are assembled from existing components rather than
  reinventing UI for each new context.
- **Maintainability** — a change to shared component behavior propagates
  consistently instead of requiring repeated, screen-by-screen updates.
- **Implementation predictability** — screen implementation effort became
  more consistent once it relied on a stabilized component library.
- **Shared engineering language** — design and implementation
  conversations referenced the same named components and patterns.

## Consequences

- Screens become compositions of reusable components.
- Accessibility improvements scale across the application.
- Design reviews increasingly evaluate interaction patterns rather than
  individual UI elements.
- Implementation effort shifts from repeated UI construction toward
  reusable component evolution.
- Engineering teams collaborate through a shared visual vocabulary.

## Related Evidence

Case Studies

- [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)

## Related Specifications

This Discovery is referenced by, and later generalized into, the
following AAOE specifications:

- [Engineering Lifecycle](../03-operating-model/0001-engineering-lifecycle.md)
- [Work Orders](../03-operating-model/0002-work-orders.md)
- [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md)

It also motivated a Design System Specification, not yet published in this
repository.

## Future Evolution

Future Case Studies may validate, refine, or challenge this Discovery.
Engineering Discoveries evolve through additional evidence, not through
revision of this record's original observation.
