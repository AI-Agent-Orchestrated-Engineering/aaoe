# Context Engineering

## Specification Metadata

**Specification ID:** DISC-0005

**Domain:** Discoveries

**Version:** 1.0

**Status:** Draft

---

## Observation

During the SolOh ERP Modernization and the evolution of AAOE itself,
better organized engineering context consistently produced higher-quality
AI implementation. AI agents required progressively fewer prompt
instructions as repository knowledge matured. Shared terminology reduced
ambiguity across specialized AI agents. Stable specifications reduced
prompt complexity. Repository organization influenced engineering quality.

## Context

These observations occurred throughout the SolOh ERP Modernization and the
resulting evolution of the AAOE repository itself, across specialized AI
agents, Work Orders, the growing Discovery Catalog, and specification-first
engineering more broadly. [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)
is the primary evidence source for this Discovery.

## Evidence

- Prompts became shorter while implementation quality improved.
- AI agents increasingly relied on repository artifacts instead of prompt
  instructions.
- Shared specifications reduced repeated explanations across Work Orders.
- Architectural consistency improved as documentation expanded.
- Repository structure became part of the engineering process itself.

## Discovery

Engineering context functions as reusable infrastructure for AI-assisted
software engineering. The quality of that context correlates more
strongly with engineering outcomes than prompt sophistication alone.

## Why It Matters

This observation appears generally applicable beyond SolOh:

- **Scalability** — context accumulated once can be drawn on by many
  subsequent Work Orders, rather than being rebuilt each time.
- **Repeatability** — implementation quality became less dependent on how
  any individual prompt was phrased.
- **Specialization** — specialized agents could rely on shared context
  instead of needing identical prompt histories.
- **Organizational knowledge** — context, once recorded, persists beyond
  the task that produced it.
- **Onboarding** — new contributors, human or agent, could draw on the
  same accumulated context rather than starting from nothing.
- **Consistency** — shared terminology and specifications reduced
  divergence between independently executed Work Orders.
- **Traceability** — context artifacts such as specifications, ADRs, and
  Discovery records connect implementation back to the reasoning behind
  it.

## Consequences

- Engineering knowledge becomes a reusable asset.
- Prompts become lightweight execution mechanisms.
- Repository organization becomes part of engineering infrastructure.
- AI agents collaborate through shared context instead of shared prompt
  history.
- Organizations accumulate engineering capability through documented
  context.

## Related Evidence

Case Studies

- [CS-0001 — SolOh ERP Modernization](../05-case-studies/0001-soloh-erp-modernization.md)

## Related Specifications

This Discovery is referenced by, and later generalized into, the
following AAOE specifications:

- [Work Orders](../03-operating-model/0002-work-orders.md)
- [Engineering Lifecycle](../03-operating-model/0001-engineering-lifecycle.md)
- [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md)
- [Discovery Lifecycle](0001-discovery-lifecycle.md)

It may also motivate a future Context Engineering Specification, not yet
published in this repository.

## Future Evolution

Future projects may validate, refine, or challenge this Discovery.
Engineering Discoveries evolve through accumulated evidence, not through
revision of this record's original observation.
