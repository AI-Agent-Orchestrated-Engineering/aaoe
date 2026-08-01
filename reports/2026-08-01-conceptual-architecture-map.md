# AAOE Conceptual Architecture Map
### AARCH-0002 — Architecture Synthesis of the Existing Canonical

**Prepared by:** AAOE Architecture Team (Curator Agent)
**Date:** 2026-08-01
**Status:** Advisory only — not reviewed, not accepted, not canonical. No Canonical document was modified. No new concepts were introduced. No terminology was changed. No Standards were proposed or rewritten.
**Governing input:** [System Boundary & Architecture Vision, AARCH-0001](2026-08-01-system-boundary-architecture-vision.md) — this map organizes only what already exists inside that vision's system boundary.

---

## 1. Domain Model

AAOE's canonical corpus is organized into eight architectural domains. This matches the existing `docs/00-07` taxonomy exactly — no domain is invented here. (One factual note: GV-0009 "Knowledge Domains" lists six Core Domains and omits Guides and Glossary, while OM-0006 "AAOE Meta-Model" lists all eight. This map uses the eight-domain view, consistent with OM-0006, and simply records the pre-existing inconsistency rather than resolving it — resolving it would be a Canonical change, out of scope here.)

| Domain | Purpose | Responsibilities | Dependencies |
|---|---|---|---|
| **Governance** (`00-governance`) | Defines how engineering knowledge itself is created, validated, organized, versioned, and evolved. The foundational, rule-setting domain — it governs knowledge, not projects. | Evidence Standard, Discovery Acceptance Process, Specification Governance, Versioning & Evolution, Traceability Model, Body-of-Knowledge Governance, Architectural Decision Lifecycle, Knowledge Domains, and the five founding ADRs (source of truth, repo strategy, publishing model, human governance, taxonomy). | None upstream — this is the constitutional layer every other domain operates within. Consumes raw evidence as input. |
| **Case Studies** (`05-case-studies`) | Holds primary empirical evidence from real applied engineering work. | CS-0001 (SolOh ERP Modernization) — the sole evidence source underlying nearly every Discovery currently in the corpus. | None upstream — this is a primary evidence source. Governed by Governance's Evidence Standard (GV-0005). |
| **Discoveries** (`02-discoveries`) | The first formal representation of engineering knowledge: evidence-based observations, not yet architecture, not yet a standard. | DISC-0000–0008, each traceable to Case Study evidence, each carrying "no authority on its own" until accepted. | Depends on Case Studies for evidence; governed by Governance's Discovery Acceptance Process (GV-0006). |
| **Standards** (`01-standards`) | Prescribes normative, required engineering practices for AAOE adopters. | STD-0001–0012, each explicitly stating which Discovery it "operationalizes." | Depends on Discoveries (each Standard traces to one); governed by Governance's Specification Governance (GV-0007) and Specification Lifecycle (STD-0001 itself). |
| **Operating Model** (`03-operating-model`) | Defines how engineering execution is organized once architecture/specification already exist: roles, lifecycle stages, delegation, Work Orders, releases. | Engineering Lifecycle (OM-0001), Work Orders (OM-0002), Roles & Responsibilities (OM-0003), Architecture Review (OM-0004), Release Management (OM-0005), AAOE Meta-Model (OM-0006). | Depends on Standards/Architectural Decisions being already accepted (architecture precedes Work Order); governed by Governance's traceability and evidence rules. |
| **Reference Architectures** (`04-reference-architectures`) | A consolidating/meta layer: describes recurring, implementation-independent capability patterns *drawn from* the other domains, rather than introducing new authority itself. | Platform Reference Architecture (capabilities spanning everything), AI Agent Reference Architecture (generalizes Operating Model's agent boundary), Engineering Knowledge Reference Architecture (generalizes Discoveries+Standards+knowledge flow), Governance Reference Architecture (generalizes Governance's own capabilities as a pattern). | Synthesizes patterns already established in Governance, Operating Model, and Standards — does not originate authority of its own. |
| **Guides** (`06-guides`) | Instructional, explicitly non-normative material teaching practical application of the model. | GUIDE-0000–0010: practical walkthroughs elaborating Standards and Operating Model concepts (e.g., "Writing Good Work Orders" elaborates OM-0002). | Derives from and elaborates Standards + Operating Model; introduces no governed authority of its own (GUIDE-0000's explicit Standard-vs-Guide distinction). |
| **Glossary** (`07-glossary`) | Cross-cutting terminology stewardship. | Defines/indexes terms used across every other domain; explicitly flags unsettled terms as *(candidate)* rather than asserting definitions. | Depends on every other domain for source definitions; owns no authority of its own — a shared dictionary service, not a producer of knowledge. |

**Structural observation:** these eight domains are not peers of equal architectural weight. Governance is constitutional (sets the rules), Case Studies/Discoveries/Standards form the evidence-to-norm pipeline, Operating Model is the execution layer that consumes accepted norms, Reference Architectures is a synthesizing layer that describes patterns *found in* the other domains, and Guides/Glossary are supporting/cross-cutting layers that add no independent authority. This layering is made explicit in §8's diagram.

---

## 2. Concept Classification

Every concept is classified under exactly one owning domain — the domain whose specification most authoritatively defines that concept's lifecycle or structure. Where a concept is *referenced* by more than one domain, the table notes the distinction rather than assigning dual ownership.

| Concept | Owning Domain | Why |
|---|---|---|
| Governance, Human Governance | Governance | GV-0000, ADR-0004 define these; no other domain defines what governance itself is. |
| Observation | Governance | Its only defined form is a lifecycle *stage* in GV-0004/GV-0006 — it has no artifact template of its own (a gap, not an assignment error). |
| Discovery | Discoveries | DISC-0001 defines its lifecycle; GV-0006 governs its *acceptance*, but the artifact itself belongs to Discoveries. |
| Architectural Decision (the act) | Governance | GV-0001 defines the decision lifecycle (Proposed→Accepted→Superseded) as distinct from the ADR document. |
| Architecture Decision Record (the artifact) | Standards | STD-0012 defines the ADR's required template/contents — the *document standard*, distinct from the decision act above. |
| Traceability | Governance | GV-0002 is the sole authority on the evidence chain. |
| Evidence | Governance | GV-0005 defines what counts as evidence and its required properties. |
| Case Study | Case Studies | CS-0001 is the only instance; no other domain defines this artifact type. |
| Specification (general) | Standards | STD-0001 (Specification Lifecycle) is the authoritative lifecycle; GV-0007 governs its *acceptance process*, not its structure. |
| Specification-Driven Development, Context Engineering, Shared Specifications, UX-First Engineering, Design-System-First Engineering, Separation of Identity/Authorization, Human-Governed Engineering, AI-Assisted Engineering | Standards | Each is a numbered STD document, each stating the Discovery it operationalizes. |
| Architecture Review (normative definition of what it evaluates) | Standards | STD-0009 states the evaluation criteria and outcomes as a Standard. |
| Architecture Review (procedural placement in the lifecycle) | Operating Model | OM-0004 places it as a stage between Implementation Report and Approval — the *procedural* home. |
| Implementation Report (requirement that one must exist) | Standards | STD-0010 states the requirement. |
| Implementation Report (required section structure) | Operating Model | OM-0002 defines the actual section template as part of the Work Order's response contract. |
| Engineering Lifecycle | Operating Model | OM-0001 is the sole authority on the stage sequence. |
| Work Order | Operating Model | OM-0002 — canonical interface between Architecture and Implementation. |
| Human Architect, Implementation Agent, Human Reviewer, Release Manager | Operating Model | OM-0003 is the sole role definition. |
| Release Management | Operating Model | OM-0005. |
| AAOE Meta-Model | Operating Model | OM-0006 — the consolidating diagram lives in this domain, though it describes concepts across all domains. |
| Engineering Intent, Scope, Constraint, Acceptance Criteria, Validation, Stop Condition | Operating Model | All are Work Order structural fields defined in OM-0002. |
| Capability | Reference Architectures | ARCH-0001's basic building-block term. |
| Boundary (Agent / Context / Tool / Trust) | Reference Architectures | ARCH-0002 is the sole definition. |
| AI Agent | Reference Architectures | ARCH-0002 is explicitly named canonical for this term by the Glossary itself. |
| AI Collaborator *(candidate)* | Reference Architectures | Glossary marks it an informal synonym for AI Agent, deferring to ARCH-0002. |
| Knowledge Curator | Reference Architectures | Named only in ARCH-0001; not present in Operating Model's role list (OM-0003) — a documented gap, not a dual assignment. |
| Engineering Knowledge | Reference Architectures | ARCH-0003's working title; the Glossary does not yet give it an independent definition distinct from Organizational Knowledge. |
| Organizational Knowledge | Glossary | Formally defined there, independent of ARCH-0003's still-unsettled "Engineering Knowledge." |
| Engineering Memory *(candidate)* | Glossary | Explicitly flagged there as unresolved, closest to "organizational memory" (an informal term from GUIDE-0009). |
| Governance capability model (Policy/Decision/Authority/Approval Management, etc.) | Reference Architectures | ARCH-0004 — itself a Reference-Architecture-domain description *of* the Governance domain's own capabilities (see structural observation in §1). |
| Guide (artifact type), all GUIDE-000x content | Guides | GUIDE-0000 defines the Standard-vs-Guide distinction that places all of this domain's content as non-normative. |
| All 37 defined terms not listed above (Artifact, Assumption, Boundary, Constraint, Context, Decision, Lifecycle, Multi-Agent Engineering, Orchestration, Responsibility, Review, Scope, Shared Context, Shared Specification, Trade-off, Workflow, etc.) | Glossary | The Glossary is the sole domain that indexes term definitions, even when the underlying concept's authority sits elsewhere (the Glossary itself states it "does not introduce new concepts"). |

---

## 3. Information Flow

Engineering *content* moves through the domains in one direction, formalizing at each step:

```
Practical engineering work (external adopter project, e.g. SolOh)
        → Case Study (Case Studies domain: raw evidence)
        → Observation (a Governance-defined stage, not yet its own artifact)
        → Discovery (Discoveries domain: first formal knowledge)
        → Architectural Decision / ADR (Governance + Standards domain: authority established)
        → Specification / Standard (Standards domain: generalized, normative)
        → Work Order (Operating Model domain: scoped, delegated task)
        → Implementation (external — performed by an Implementation Agent, outside AAOE's boundary per the Architecture Vision)
        → Implementation Report (Operating Model/Standards domain: what happened)
        → Architecture Review (Operating Model/Standards domain: evaluated against intent)
        → Release (Operating Model domain: integrated)
        → Organizational Knowledge (Glossary/Reference Architecture domain: preserved, feeds future Observations)
```

This is exactly GV-0002's Traceability Model and OM-0006's Engineering Knowledge Graph, read as a single content pipeline. Guides and Glossary do not sit *in* this pipeline — they sit alongside it, explaining and indexing it without adding new content of their own (consistent with §1's "supporting/cross-cutting" note).

---

## 4. Governance Flow

Governance flow tracks *authority*, not content — who may approve what, at each gate the Information Flow passes through:

```
Evidence exists (no authority required — GV-0005: "shall not depend upon authority")
        ↓
Discovery proposed  →  Architecture Review evaluates governance criteria (GV-0006)  →  Accepted Discovery
        ↓
Architectural Decision proposed  →  Human review/acceptance (GV-0001)  →  ADR Published
        ↓
Specification/Standard drafted (may be AI-assisted, STD-0011)  →  Human approval via Specification Governance (GV-0007)  →  Accepted
        ↓
Work Order authored  →  Human Architect only (OM-0003) — "architecture is never inferred"
        ↓
Implementation performed  →  Implementation Agent — no approval authority, output is a proposal (ARCH-0002)
        ↓
Architecture Review performed  →  Human Reviewer only (OM-0004/STD-0009) — "Implementation Agents do not participate in approval decisions"
        ↓
Release  →  Release Manager — merges only what was already approved, cannot alter content (OM-0003/OM-0005)
```

The invariant threaded through every single gate above, stated identically by ARCH-0002, ARCH-0004, and STD-0008: **AI may produce, draft, or propose at any stage; only a human may approve.** This is the one rule that appears in every domain and is violated by none of them — the clearest cross-cutting principle in the whole architecture.

---

## 5. Engineering Flow

Where Governance Flow asks "who may approve," Engineering Flow is the narrower, purely procedural sequence a single piece of work follows once architecture is already settled — this is OM-0001 verbatim:

```
Architecture (already approved)
   → Work Order (scoped to one Task, one objective)
   → Implementation (bounded by Work Order's stated scope/constraints)
   → Implementation Report (Summary, Files, PR, Notes, Questions)
   → Architecture Review (Approved / Approved with Recommendations / Revision Required)
   → Approval
   → Merge
   → Next Work Order (begins from the latest approved release state)
```

Engineering Flow is entirely contained within the Operating Model domain. It assumes the Information Flow's upstream stages (Discovery → Decision → Specification) have already completed — OM-0001 explicitly begins at "Architecture," not at "Observation." This is the same boundary the AARCH-0001 Architecture Vision and the earlier Discovery Assessment both identified: everything upstream of Architecture is informal/narrative (Guides domain) rather than a governed stage.

---

## 6. Knowledge Evolution Flow

Where the previous three flows describe *movement*, Knowledge Evolution describes *confidence deepening over time* — a dimension orthogonal to all of them. It has two independent axes, both defined in Governance (GV-0003):

```
Artifact Status axis (governs the document):
  Draft → Accepted → Revised → Superseded → Archived

Knowledge Maturity axis (reflects confidence, independent of document status):
  Observed → Repeated → Validated → Generalized
```

A Discovery can be an "Accepted" artifact (status) while still only "Observed" once (maturity) — GV-0003 deliberately keeps these separate so that formal acceptance doesn't overstate confidence. Knowledge matures along the second axis as more Case Studies produce the same observation (e.g., a future second case study repeating DISC-0002's finding would move it from Observed toward Repeated/Validated), and it is this axis — not artifact status — that ultimately justifies a Discovery generalizing into a Standard (GV-0008's Versioning & Evolution governs the document mechanics of that generalization once it happens).

Currently, nearly every Discovery and Standard in the corpus sits at "Observed" maturity with a single supporting Case Study (CS-0001) — a fact this map surfaces structurally but does not evaluate, consistent with the prior Discovery Assessment's findings.

---

## 7. Concept Relationships

**Parent concepts** (foundational, domain-defining — nothing above them):
Governance · Case Studies (as primary evidence) · Reference Architectures (as the consolidating/meta layer over the domains below)

**Child concepts** (specific instances governed by a parent):
Individual GV-000x specifications and the five ADRs (children of Governance) · Individual DISC-000x records (children of Discoveries) · Individual STD-000x specifications (children of Standards) · Individual OM-000x specifications, and within OM-0002 the Work Order's own fields — Scope, Constraint, Acceptance Criteria, Validation, Stop Condition (children of Operating Model) · Individual ARCH-000x documents (children of Reference Architectures) · Individual GUIDE-000x chapters (children of Guides)

**Supporting concepts** (exist to serve other concepts; carry no authority of their own):
Guides (support adoption of Standards/Operating Model) · Glossary (supports terminology consistency across every domain) · Implementation Report (supports Architecture Review by documenting what happened) · Traceability (supports Governance's evidence chain rather than standing alone)

**Cross-cutting concepts** (appear across multiple domains without being owned by any single one, beyond the classification given in §2):
Evidence (spans Case Studies, Discoveries, Governance) · Traceability (spans all eight domains) · Human Governance / "AI may propose, only humans approve" (spans Governance, Standards, Operating Model, Reference Architectures — see §4) · Context / Context Engineering (spans Standards STD-0003, Discoveries DISC-0005, Guides GUIDE-0005) · Architecture Review (spans Standards' normative definition and Operating Model's procedural placement, per §2)

---

## 8. Architecture Diagram

```
 ┌────────────────────────────────────────────────────────────────────────┐
 │                              GOVERNANCE                                │
 │   Evidence Standard · Traceability Model · Versioning & Evolution ·    │
 │   Discovery Acceptance · Specification Governance · ADR Lifecycle ·    │
 │   Founding ADRs (source of truth, repo strategy, publishing, human     │
 │   governance, taxonomy)                                                │
 │           the constitutional layer — sets rules, is not executed       │
 └───────────────────────────────△────────────────────────────────────────┘
                                  │ governs every domain below
     ┌────────────────────────────────────────────────────────────┐
     │                                                              │
┌────▼─────────┐  evidence   ┌───────────────┐  generalizes   ┌────▼──────────┐
│ CASE STUDIES │────────────▶│  DISCOVERIES  │───────────────▶│   STANDARDS   │
│  CS-000x     │             │   DISC-000x   │                │   STD-000x    │
│ (raw         │             │ (first formal │                │ (normative,   │
│  evidence)   │             │  knowledge)   │                │  operationa-  │
│              │             │               │                │  lizes a      │
│              │             │               │                │  Discovery)   │
└──────────────┘             └───────────────┘                └───────┬───────┘
                                                                        │ specification precedes
                                                                        │ Work Order
 ┌──────────────────────────────────────────────────────────────────────▼───┐
 │                    OPERATING MODEL   (OM-000x)                           │
 │                                                                          │
 │   Architecture ─▶ Work Order ─▶ Implementation ─▶ Implementation Report │
 │        ─▶ Architecture Review ─▶ Approval ─▶ Merge ─▶ (next Work Order) │
 │                                                                          │
 │   Roles: Human Architect · Implementation Agent (no approval authority) │
 │          · Human Reviewer · Release Manager (no content authority)      │
 └───────────────────────────────△──────────────────────────────────────────┘
                                  │ patterns generalized from the domains above
                    ┌──────────────────────────────┐
                    │   REFERENCE ARCHITECTURES     │
                    │        (ARCH-000x)            │
                    │  Platform · AI Agent ·        │
                    │  Engineering Knowledge ·      │
                    │  Governance                   │
                    │  — a consolidating/meta layer,│
                    │  not a peer authority source  │
                    └──────────────────────────────┘

  ┌────────────────────────┐        ┌─────────────────────────┐
  │         GUIDES          │        │        GLOSSARY          │
  │  non-normative "how"    │        │  cross-cutting terms —   │
  │  elaborates Standards / │        │  indexes every domain    │
  │  Operating Model        │        │  above without owning    │
  │  (no authority of       │        │  authority                │
  │   its own)              │        │                          │
  └────────────────────────┘        └─────────────────────────┘

        ── feedback loop ──
  Release ──▶ Organizational Knowledge ──▶ feeds future Observations,
              re-entering at Case Studies / Discoveries (top-left)

  ── outside the boundary (per AARCH-0001), interfacing at the edges ──
  adopter engineering projects (feed Case Studies) · AI models/agents as
  running software (implement the Implementation Agent role) · the future
  website (a derived, non-authoritative consumer of Standards/Guides/
  Glossary)
```

---

## Repository Record

- **Files created:** `reports/2026-08-01-conceptual-architecture-map.md`
- **Files modified:** none
- **Branch:** `feature/AARCH-0002-conceptual-architecture-map` (created from `release/v1.1`)
- **Commit:** `ef21cf49296a537d250bea29ec0766525fa6d1f1` — "docs(architecture): define conceptual architecture map"
- **Timestamp:** 2026-08-01T22:41:36Z
- **Pull Request:** https://github.com/AI-Agent-Orchestrated-Engineering/aaoe/pull/59 (feature/AARCH-0002-conceptual-architecture-map → release/v1.1)
