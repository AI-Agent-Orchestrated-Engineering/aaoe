# SolOh ERP Modernization

## Specification Metadata

**Specification ID:** CS-0001

**Domain:** Case Studies

**Classification:** Reference Implementation

**Version:** 1.0

**Status:** Draft

---

## Purpose

SolOh ERP Modernization is AAOE's first Case Study, and it is classified as
a Reference Implementation because AAOE did not exist before this project
and was not designed in the abstract. SolOh was the laboratory in which the
engineering operating model that became AAOE was exercised, tested, and
generalized. Its discoveries provide the factual basis for much of the
Governance, Operating Model, and Reference Architecture domains already
published in this repository.

This document is not a project history, implementation guide, or tutorial.
It presents architectural evidence: the engineering challenges SolOh
surfaced, the observations and discoveries that followed, the decisions
made in response, and the AAOE specifications those decisions eventually
became.

## Project Overview

SolOh ERP Modernization set out to modernize a legacy ERP system using an
AI-first engineering approach, while simultaneously validating a new
engineering operating model — the model that eventually became AAOE. The
modernization was never intended to be merely a technology upgrade; it
became the opportunity to redesign how software engineering work is
organized when AI agents participate as specialized contributors under
human governance.

The initial scope favored establishing a repeatable modernization approach
over rewriting the ERP at once. Early efforts spanned authentication
modernization, Design System creation, functional and UX specifications,
API and database contracts, backend and frontend modernization, AI-assisted
implementation, and architecture governance. Authentication became the
first complete vertical slice used to validate the engineering process
end to end.

## Architectural Context

The existing ERP presented modernization challenges that are common to
long-lived systems but were sharpened by introducing AI agents into the
engineering process:

- Multiple legacy databases supported similar business capabilities.
- UI, API, and database evolution were tightly coupled.
- Authentication was intertwined with authorization.
- Infrastructure concerns leaked into business contracts.
- Implementation began with limited specification.
- AI tools produced inconsistent results when requirements were incomplete.

Rather than continuing to specify while implementing, the project gradually
shifted toward specification-first engineering. That shift became one of
AAOE's defining principles: architecture precedes implementation, and
implementation follows a defined work order rather than ad hoc instruction.

## AAOE Application

The evidence below is organized around the chain that produced it, not
around a chronology of project events:

```text
Engineering Challenge
        ↓
Observation
        ↓
Discovery
        ↓
Architectural Decision
        ↓
AAOE Specification
        ↓
Application in SolOh
        ↓
Engineering Outcome
```

### Specifications over prompts

- **Challenge** — limited specification before implementation, and AI
  tools producing inconsistent results when requirements were incomplete.
- **Discovery** — Specification-Driven Development consistently
  outperformed prompt-driven development; specifications outlive prompts
  and become reusable organizational knowledge; shared specifications
  scale better than shared source code.
- **Decision** — adopt Specification-Driven Development as the primary
  engineering workflow, and introduce a feature delivery lifecycle moving
  from business intent through specifications before implementation;
  treat specifications, not prompts, as the canonical engineering asset.
- **AAOE Specification** — this decision generalized into the
  [Specification Lifecycle](../01-standards/0001-specification-lifecycle.md)
  and the requirement, carried through [Work Orders](../03-operating-model/0002-work-orders.md),
  that architecture is never inferred by implementation.
- **Application in SolOh** — specifications were produced and reviewed
  before implementation Work Orders were issued to AI agents.
- **Outcome** — implementation quality became repeatable rather than
  dependent on how a given prompt happened to be phrased.

### UX and Design Systems before implementation

- **Challenge** — tight coupling between UI, API, and database evolution.
- **Discovery** — UX should precede API design; Design Systems should
  exist before screen implementation; fully validated reusable components
  reduce downstream implementation effort; design reviews performed before
  code reviews shift quality earlier in the lifecycle.
- **Decision** — design UX before defining APIs, and build and validate
  the Design System before implementing application screens.
- **AAOE Specification** — this ordering is consistent with the Engineering
  Lifecycle's principle that architecture precedes implementation, and with
  [Architecture Review](../03-operating-model/0004-architecture-review.md)
  evaluating outcomes against intent rather than implementation style.
- **Application in SolOh** — the Design System and UX specifications for
  the Authentication vertical slice were validated before API and screen
  implementation began.
- **Outcome** — downstream implementation effort decreased, and defects
  were caught at the design stage rather than in code review.

### Separating concerns at their true boundary

- **Challenge** — authentication intertwined with authorization, and
  infrastructure concerns leaking into business contracts.
- **Discovery** — authentication and authorization should be separated;
  database contracts should be treated as specifications rather than
  implementation details; stable API contracts decouple legacy database
  modernization from the rest of the system.
- **Decision** — separate authentication from authorization; move tenant
  resolution and store-alias handling into infrastructure rather than
  business contracts; standardize API contracts so multiple legacy
  databases could implement identical behavior behind a common interface.
- **AAOE Specification** — treating contracts as specifications reflects
  the [Specification Lifecycle](../01-standards/0001-specification-lifecycle.md)'s
  principle that specifications represent approved knowledge, not
  incidental implementation detail.
- **Application in SolOh** — the Authentication vertical slice was
  implemented against these separated, stabilized contracts.
- **Outcome** — the Authentication feature became the first complete
  vertical slice validating the whole engineering process, from
  specification through implementation and review.

### Specialized agents under human governance

- **Challenge** — AI tools produced inconsistent results when requirements
  were incomplete, and a single general-purpose AI struggled to hold the
  context a full feature required.
- **Discovery** — specialized AI agents produce higher-quality results than
  a single general-purpose AI; context quality matters more than model
  capability; polyrepo organization improves AI specialization; human
  architects increasingly act as systems conductors; features, not
  repositories, become the true unit of engineering work; stable
  requirements enable effective parallel AI implementation.
- **Decision** — organize implementation around specialized AI agents with
  well-defined responsibilities.
- **AAOE Specification** — this generalized into the
  [AI Agent Reference Architecture](../04-reference-architectures/0002-ai-agent-reference-architecture.md)'s
  Agent Responsibilities and Agent Boundaries, and into
  [Roles & Responsibilities](../03-operating-model/0003-roles-and-responsibilities.md)'
  Future Specialized Roles and the Human Architect role.
- **Application in SolOh** — implementation work was delegated to
  specialized agents through Work Orders scoped to a single feature, with
  human architects coordinating across them.
- **Outcome** — AI agents operated as specialized contributors rather than
  decision makers, validating AAOE's human-governed contribution model in
  practice rather than only in principle.

### AAOE itself as a discovery

- **Challenge** — the project needed a repeatable engineering process, not
  only a modernized ERP.
- **Discovery** — AAOE evolved from an orchestration concept into a
  complete Engineering Operating Model.
- **Decision** — formalize the workflow, roles, lifecycle, and governance
  that had emerged during SolOh into a named, reusable methodology.
- **AAOE Specification** — this decision is what this repository's
  Governance, Operating Model, and Reference Architecture domains
  formalize, consolidated by the
  [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md).
- **Application in SolOh** — SolOh's own engineering workflow now follows
  the same Discovery → Architectural Decision → Specification → Work
  Order → Implementation → Review → Release pattern it originally produced.
- **Outcome** — AAOE now governs its own continued evolution, not only
  SolOh's.

The full, repeatable engineering workflow validated on SolOh was:

1. Capture observations during modernization.
2. Record discoveries.
3. Make architectural decisions.
4. Produce formal specifications.
5. Create Work Orders for bounded implementation tasks.
6. Delegate implementation to specialized AI agents.
7. Produce Implementation Reports documenting completed work.
8. Perform Architecture Review before integration.
9. Incorporate validated outcomes into the evolving body of AAOE knowledge.

Throughout, human architects retained responsibility for business intent,
architectural approval, artifact review, agent coordination, and
acceptance of completed work; AI agents acted as specialized contributors,
never as decision makers, consistent with AAOE's Roles & Responsibilities
and Architecture Review specifications.

## Engineering Knowledge Produced

SolOh's discoveries and decisions are the factual basis for much of AAOE's
current Standards, Governance, and Reference Architecture domains,
including the [Specification Lifecycle](../01-standards/0001-specification-lifecycle.md),
the [Discovery Lifecycle](../02-discoveries/0001-discovery-lifecycle.md), the
[Architectural Decision Lifecycle](../00-governance/0001-architectural-decision-lifecycle.md),
the [AI Agent Reference Architecture](../04-reference-architectures/0002-ai-agent-reference-architecture.md),
and the [AAOE Meta-Model](../03-operating-model/0006-aaoe-meta-model.md).

The individual observations and discoveries summarized in this Case Study
have not yet been captured as separate, individually identified Discovery
records under `docs/02-discoveries/`. Doing so — tracing each discovery
listed above to its own DISC-numbered record — is a natural extension of
this Case Study and is noted under Future Evolution below.

## Traceability

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
```

Applied to the Authentication vertical slice: the observation that
authentication and authorization were intertwined led to a discovery about
separating them; that discovery informed the decision to separate
authentication from authorization and relocate tenant resolution into
infrastructure; the decision was formalized into API and database
contracts treated as specifications; those specifications scoped the Work
Orders issued to specialized agents; execution produced an Implementation
Report; Architecture Review evaluated the result against the original
architectural intent; and the approved result was released as the first
complete vertical slice validating the process end to end. Every stage
remains traceable to the one before it, consistent with the
[Traceability Model](../00-governance/0002-traceability-model.md).

## Reusability

The architectural practices SolOh produced are general enough to apply
beyond ERP modernization: specification-first engineering, UX and Design
System validation before implementation, treating contracts as
specifications, organizing implementation around specialized agents, and
preserving engineering knowledge through traceable artifacts rather than
isolated prompts. Future modernization initiatives can adopt these
practices directly through the AAOE specifications they generalized into,
without needing to rediscover them independently.

## Lessons Learned

The most important outcome was not progress on ERP modernization alone. The
project validated that an AI-first engineering organization can operate
effectively when specifications are the primary engineering artifact, AI
agents specialize around well-defined responsibilities, work is delegated
through structured Work Orders, human governance remains explicit, and
engineering knowledge is preserved through traceable artifacts rather than
isolated prompts. By the end of the modernization effort described here,
AAOE had moved from an idea about orchestrating AI agents into an
Engineering Operating Model governing roles, lifecycles, specifications,
repository structure, architecture validation, implementation
orchestration, and human oversight.

## Future Evolution

This Case Study will continue evolving alongside both the SolOh ERP
Modernization and future AAOE releases. Anticipated extensions include
capturing the individual discoveries summarized here as separate
DISC-numbered records, and documenting further vertical slices as they
reach the same maturity as the Authentication slice referenced throughout
this document.
