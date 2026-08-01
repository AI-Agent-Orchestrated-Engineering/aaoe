# AAOE Architecture Vision
### AARCH-0001 — Step 1: System Boundary & Architecture Vision

**Prepared by:** AAOE Architecture Team (Curator Agent)
**Date:** 2026-08-01
**Status:** Advisory only — not reviewed, not accepted, not canonical. No AAOE Canonical document was modified. No Standards were proposed. No documents were restructured.

---

## 1. System Definition

**What AAOE is, architecturally:** a **human-governed system for creating, validating, evolving, and publishing engineering knowledge about how AI-assisted software engineering should be organized** — realized concretely as a canonical corpus (governance rules, discoveries, decisions, specifications, reference architectures, guides, glossary) plus the operating model that applies it.

AAOE is not itself a piece of running software, a product, an AI system, or an engineering project. It is a **knowledge and governance system**, evidenced by what the existing canon actually contains: `docs/00-09` are documents about how knowledge is created and governed (Governance), how work is organized (Operating Model), what has been learned (Discoveries), what is prescribed (Standards), and what patterns recur (Reference Architectures) — not a codebase, not a deployed service, not an agent runtime.

**Purpose:** to let engineering organizations (their human engineers and the AI agents they employ) conduct AI-assisted software engineering under a shared, evidence-based, human-governed model — so that engineering quality, coherence, and traceability do not depend on any single team rediscovering them independently (README.md; CS-0001 "Reusability").

**Responsibilities (in scope):**
- Defining how engineering knowledge is created, validated, versioned, and evolved (GV-0000–0009).
- Defining the roles, lifecycle stages, and delegation boundaries through which humans and AI collaborate on engineering work (03-operating-model).
- Defining reusable, implementation-independent architectural patterns (04-reference-architectures).
- Preserving evidence, traceability, and historical integrity of that knowledge (GV-0002, GV-0005).
- Publishing consistent terminology and instructional material describing how to apply the model (06-guides, 07-glossary).

**Non-scope (explicitly not AAOE's responsibility):**
- Implementing software, prescribing languages, stacks, or cloud providers (GV-0000, stated explicitly).
- Executing engineering projects. SolOh ERP Modernization is external to AAOE — it is the project AAOE observed and generalized from (CS-0001), not AAOE itself.
- Building, owning, or operating AI models, agent runtimes, IDEs, or any product.
- Prescribing an adopter organization's structure or delivery process.
- Serving as a second source of truth outside the canonical repositories (ADR-0001, ADR-0003) — anything with a UI, including a future website, is derived presentation, not AAOE's substance.

**One-sentence scope boundary:** AAOE is a body of governed engineering knowledge and an operating model for applying it — not running software, not a project, not an organization.

---

## 2. System Boundary

| Inside AAOE | Outside AAOE |
|---|---|
| Engineering Knowledge itself: Observations, Discoveries, Architectural Decisions, Specifications, Reference Architectures, Case Studies, Guides, Glossary (the canonical corpus) | **Source Code** — belongs to adopter engineering projects (e.g., SolOh), never to AAOE |
| Governance rules for how that knowledge is created, reviewed, versioned, and evolved | **Engineering Projects** themselves (SolOh is an external evidence *source*, not a part of AAOE) |
| The Operating Model **as a definition** — roles, lifecycle stages, Work Order structure, delegation boundaries | **Organizations** that adopt AAOE — external actors who apply the model to their own work |
| Role and boundary definitions for how AI participates in AAOE-governed engineering (e.g., ARCH-0002's Agent Boundaries) | **AI Models and AI Agents as running software** (Claude, GPT, Claude Code, ChatGPT, or any specific agent implementation) — AAOE defines the boundary such an agent must respect; it does not build or own the agent |
| Terminology and glossary | **Human Engineers** as people — external actors who occupy AAOE-defined roles (Human Architect, Human Reviewer, etc.) while doing their work; the *role* is inside AAOE, the *person* is not |
| `aaoe` and `aaoe-specifications` repositories (both canonical per ADR-0002, despite being organizationally separate) | **Git hosting infrastructure** (GitHub itself) — the substrate ADR-0001 designates as canonical *storage*, but the platform is external infrastructure |
| — | **Websites** — explicitly derived, non-authoritative presentation (ADR-0001, ADR-0003); lives outside the canonical taxonomy until a dedicated repository is warranted (ADR-0002, ADR-0005) |
| — | **Documentation of adopter systems**, their CI/CD, and their cloud infrastructure — explicitly disclaimed by GV-0000 |

**The key distinction this boundary rests on:** AAOE defines *roles* (Human Architect, Implementation Agent, AI Agent boundaries); it does not own the *actors* who occupy those roles (specific humans, specific AI models, specific companies). This single distinction is what determines, later in this document, whether a candidate concept belongs inside AAOE or describes an external tool that merely plays a role AAOE has defined.

---

## 3. Core Responsibilities

Determined by what the existing canon actually does, not by assumption:

| Candidate responsibility | In scope? | Evidence |
|---|---|---|
| **Knowledge Governance** (creation, validation, versioning, evolution of engineering knowledge) | **Yes — core** | Entire 00-governance domain exists for exactly this. |
| **Traceability & Evidence Assurance** | **Yes — core** | GV-0002, GV-0005; "an artifact that is correct but untraceable is still a governance gap." |
| **Operating Model Definition** (roles, lifecycle stages, delegation boundaries) | **Yes — core** | 03-operating-model domain. |
| **Reference Architecture Definition** (recurring, implementation-independent capability patterns) | **Yes — core** | 04-reference-architectures domain. |
| **Terminology Stewardship** | **Yes — core** | 07-glossary, explicitly self-flags unsettled terms rather than asserting them. |
| **Knowledge Evolution** (knowledge maturing from Observation through Specification and beyond) | **Yes — already a responsibility**, though not currently named exactly this. GV-0000 ("knowledge evolves through validation") and GV-0008 (Versioning & Evolution) already own this. A candidate concept using this name is very likely a renaming/formalization of existing scope, not new scope (see §Boundary Test below). |
| **Engineering Governance** (approval authority, human governance of AI participation) | **Yes — core** | STD-0008, ARCH-0004, ADR-0004. |
| **Engineering Guidance** (instructional, non-normative practice material) | **Yes — secondary** | 06-guides domain, deliberately kept non-normative and distinct from Standards (GUIDE-0000). |
| **Engineering Execution** (actually writing code / performing project work) | **No — explicitly excluded** | GV-0000 disclaims implementation prescriptions; execution happens in adopter projects using AAOE's governance, delegated via Work Orders — but the act of execution is not something AAOE performs or owns. |
| **Product / Tooling Ownership** (building an AI companion, an agent runtime, an IDE) | **No — not currently in scope** | Nothing in the canon describes AAOE as producing software; expanding into this would be a distinct, deliberate architectural decision, not an incidental consequence of naming a new concept. |

---

## 4. External Systems

Systems AAOE interacts with, depends on being interpreted correctly by, or is applied within — but does not own:

- **GitHub** (or any Git host) — the storage substrate ADR-0001 designates as canonical source of truth; the platform itself is external infrastructure.
- **Claude Code, ChatGPT, and other AI assistants** — external tools that *implement* the AI Agent role (and any future Engineering Companion role) AAOE defines boundaries for. AAOE governs what such a tool may and may not do while participating in AAOE-governed engineering; it does not build, license, or operate the tool.
- **IDEs** — external, adopter-side tooling; explicitly out of scope (OM-0004 lists "IDE configuration" as something Architecture Review does not evaluate).
- **CI/CD systems** — external, adopter delivery infrastructure; GV-0000 explicitly disclaims prescribing "delivery processes."
- **Cloud Providers** — external, adopter infrastructure choice; explicitly disclaimed by GV-0000.
- **Adopter engineering projects** (e.g., SolOh ERP Modernization) — external systems that generate evidence *for* AAOE (as Case Studies) and consume AAOE's governance, but are not part of AAOE itself.
- **The future AAOE Website** — an external, derived consumer/publisher of AAOE knowledge (ADR-0003); part of the AAOE *ecosystem* once it exists (ADR-0002), but not part of the AAOE *system boundary* as defined here, and not a source of truth.

Not external, for clarity: **`aaoe-specifications`** is a separate repository but is canonical (ADR-0002) — it is inside the boundary despite being organizationally distinct from this repository.

---

## 5. Architectural Principles

Recommended as the foundation against which every future AAOE concept — including all seven named in this Work Item's context — should be evaluated:

1. **Knowledge and role boundaries before tooling.** AAOE defines what knowledge is and what a role may/may not do. It does not own the products or tools that implement those roles. Any new concept must first be classified as one or the other before it can be evaluated for inclusion.
2. **Authority never originates in execution.** Already established for AI Agents (ARCH-0004); any new role definition must state what it may never do before what it may do.
3. **Evidence precedes concept acceptance.** No concept enters the canonical corpus without a documented, attributable Observation and Discovery (GV-0005, GV-0006) — narrative description of a concept is not evidence that it exists in practice.
4. **Roles are internal constructs; actors are external.** Humans, specific AI models, and organizations are external; the roles they occupy while engineering (Human Architect, AI Agent, and any future role) are defined inside AAOE. This is the resolving test for role-like candidate concepts.
5. **The canonical repository is the sole source of truth; every other artifact is derived.** Websites, tools, and products built around AAOE knowledge are downstream and non-authoritative (ADR-0001, ADR-0003), regardless of how central they become to adoption.
6. **New scope requires new boundary justification, not just new terminology.** Mirrors ADR-0002's principle for repositories: a new concept must show why it doesn't already fit an existing responsibility (§3) before it is treated as new scope.
7. **Governance and Operating Model remain separate.** GV-0000's foundational split — how knowledge evolves vs. how execution is organized — must be preserved as new concepts are absorbed; a concept should not be allowed to blend the two.
8. **AAOE governs its own evolution the same way it governs adopters' work.** Per CS-0001 ("AAOE itself as a discovery"), any change to AAOE — including the concepts evaluated here — should itself pass through Observation → Discovery → Decision → Specification, not enter by assertion.

---

## Boundary Test — Applying This Vision to the Seven Named Concepts

This section applies the boundary above; it does not decide inclusion, propose Standards, or modify the canon. It is offered because the Success Criteria asks this vision to be usable as an evaluation foundation, and demonstrating the test in use is the clearest way to make it usable.

| Concept | Classification | Reasoning |
|---|---|---|
| **Engineering Companion** | **Split concept.** The *role/boundary definition* (what such an AI may and may not do while participating in AAOE-governed engineering) is inside AAOE's boundary, analogous to ARCH-0002's AI Agent. The *actual conversational AI product* is outside AAOE's boundary — external tooling, like Claude Code or ChatGPT, that would implement that role. Conflating the two would pull product ownership into AAOE's scope, which §3 found is not currently a responsibility. |
| **Conversation-Driven Engineering** | **Inside**, as a candidate engineering *practice* — same category as Specification-Driven Development. Subject to the evidence gate (Principle 3); classification as in-scope does not mean accepted. |
| **Knowledge-Driven Engineering** | **Inside**, same category — but overlaps in name with Specification-Driven Development and Context Engineering closely enough that it needs reconciling against existing Standards before being treated as distinct. A terminology question, not a boundary question. |
| **Engineering Knowledge** | **Inside** — ARCH-0003 already uses this working title. Overlaps with existing "Organizational Knowledge" and the glossary-candidate "Engineering Memory"; needs terminology reconciliation, not a boundary decision. |
| **Engineering Observation** | **Inside** — very likely a rename/formalization of the "Observation" stage already defined in GV-0004/GV-0006, not new scope. |
| **Knowledge Evolution** | **Inside** — already a described responsibility (GV-0000, GV-0008); likely a naming exercise, not new scope. |
| **Engineering Knowledge Supply Chain** | **Inside as a metaphor for the existing Traceability/Knowledge Lifecycle model (GV-0002, GV-0004)** — but the "supply chain" framing should be checked for whether it implies new operational responsibilities (e.g., managing external knowledge sources or dependencies) beyond what §3 currently scopes. If it's purely descriptive of the existing flow, it needs no new boundary. If it implies AAOE managing something it doesn't today, Principle 6 requires that be justified explicitly, not assumed. |

**Net observation:** none of the seven concepts described in this Work Item's context require AAOE's system boundary to expand. Four of the seven (Engineering Knowledge, Engineering Observation, Knowledge Evolution, Engineering Knowledge Supply Chain) appear to be renamings or formalizations of responsibilities the canon already owns. The two practice-level concepts (Conversation-Driven Engineering, Knowledge-Driven Engineering) fit the existing "X-Driven Engineering" category without requiring new scope. Only Engineering Companion raises a genuine boundary question, and it resolves cleanly once the role/product distinction in Principle 1 and Principle 4 is applied.

---

## Repository Record

- **Files created:** `reports/2026-08-01-system-boundary-architecture-vision.md`
- **Files modified:** none
- **Branch:** `release/v1.1`
- **Commit:** *(recorded after commit — see below)*
- **Timestamp:** *(recorded after commit — see below)*
