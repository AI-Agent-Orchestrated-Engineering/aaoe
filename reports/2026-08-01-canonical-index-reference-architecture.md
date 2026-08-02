# Canonical Index — Reference Architecture
### AARCH-0004 — Platform Capability Definition

**Prepared by:** AAOE Curator Agent, acting as Enterprise Platform Architect
**Date:** 2026-08-01
**Status:** Advisory only — a proposed Reference Architecture, not yet canonical. No Canonical document was modified, no implementation was performed, no technology, format, storage, or API was chosen. If adopted, this should enter the Canonical the same way every other Reference Architecture did — through Discovery, Architecture Review, and Governance acceptance (see §10) — not by virtue of existing in this report.
**Governing inputs:** [System Boundary & Architecture Vision](2026-08-01-system-boundary-architecture-vision.md), [Conceptual Architecture Map](2026-08-01-conceptual-architecture-map.md), [Information Architecture Assessment](2026-08-01-information-architecture-assessment.md) — this document formalizes IA-0001's Recommendation #1.

---

## 1. Purpose

IA-0001 found that multiple audiences (website, Companion, curator, engineers, and now future MCP servers, IDEs, CLIs, and automation) each need to discover and navigate the same Canonical, and that without a shared discovery mechanism, every consumer would build its own ad-hoc list — reproducing exactly the "shadow canon" and "projection drift" risks that assessment flagged.

**The Canonical Index exists to be the one place discovery logic lives, so authority logic never has to be rederived by each consumer independently.** It answers "what canonical knowledge exists, where does it live, what state is it in, and how does it relate to other knowledge" — as a discoverability capability, not as a second place where that knowledge is defined.

Its necessity follows directly from AARCH-0002's Conceptual Architecture Map: canonical documents already declare rich relationships (a Standard states which Discovery it operationalizes; a Discovery cites its Case Study evidence; an ADR references related Specifications) — but today those relationships exist only as prose and inline links, readable one document at a time. No consumer can currently ask "what depends on this Discovery" or "what governs this kind of Work Order" without manually reading many documents. The Canonical Index formalizes *discovery of structure that already exists* — it does not create new structure.

---

## 2. Responsibilities

**Owns:**
- Discoverability — enumerating which canonical artifacts exist, by identifier, domain, and type.
- Reflecting lifecycle/status metadata already stated in each artifact (Draft/Accepted/Revised/Superseded/Archived, per GV-0008) — as a mirror, never as an independent judgment.
- Aggregating relationships and dependencies already declared inline in canonical documents (operationalizes, informs, supersedes, related-to) into a queryable structure.
- Providing one consistent discovery/query surface so consumers stop reimplementing their own navigation logic (the exact duplication IA-0001 warned against).
- Supporting the audience-specific navigation models IA-0001 designed, by exposing metadata those views can filter or group on.

**Explicitly does not own:**
- The canonical content itself. The Index carries metadata *about* artifacts; full text remains solely in the Canonical Repository. No duplication of knowledge.
- Determining what is canonical. Acceptance, status changes, and supersession remain exclusively Governance's responsibility (GV-0006, GV-0007, GV-0008) — the Index reports the outcome of those processes, it never performs them.
- Approval authority of any kind. The Index cannot mark anything Accepted; it can only state that the Canonical currently says so.
- Conflict resolution within the Canonical. Where the corpus itself is inconsistent (e.g., GV-0009 and OM-0006 currently disagree on which domains count as "Core Domains" — a fact this Architecture Team has flagged in two prior reports without resolving it), the Index must represent that inconsistency transparently rather than silently picking a side.
- Prescribing how any consumer presents the data it discovers. Presentation belongs to the Navigation Models (IA-0001) each consumer implements, not to the Index itself.
- Governance workflow execution (e.g., managing contribution review). It reflects governed facts; it does not participate in producing them.
- Independent authority of any kind. **If the Index and the Canonical ever disagree, the Canonical is correct by definition** — the same invariant IA-0001 established for every navigation view, applied here to the one capability every other view would depend on.

---

## 3. Consumers

| Consumer | Status | How it would use the Index |
|---|---|---|
| **Website** | Defined in IA-0001 | Broad, catalog-style discovery — rendering registers (Standards catalog, Guides reading order) instead of hand-maintaining its own lists. |
| **Engineering Companion** | Defined in IA-0001 | Narrow, task-scoped discovery — resolving exactly the bounded set of artifacts a given task requires (per STD-0003's context-scoping principle, applied to the Companion's own consumption), plus term disambiguation via the Glossary reflection. |
| **Curator / Maintainer** | Defined in IA-0001 | Status- and maturity-filtered discovery — "list all Draft Discoveries," "list all candidate Glossary terms" — the maintenance-queue view IA-0001 already described, made queryable instead of manually assembled. |
| **Human Engineers** | Defined in IA-0001 | Indirect — most humans consume the Index only through a rendered view (website, docs, CLI output), rarely querying it directly. |
| **Future MCP Servers** | Anticipated, not yet existing | A Model Context Protocol server exposing AAOE knowledge to arbitrary AI tools would use the Index as its resource-listing/discovery layer — this is the concrete shape of the "Future Engineering Tools" consumer ARCH-0003 already anticipated. Architecturally distinct from the others: such a server is largely a thin exposure of the Index's discovery surface, not a downstream renderer that reshapes it. |
| **IDE Integrations** | Anticipated, not yet existing | Contextual discovery scoped to the engineer's current work (e.g., "what Standard governs this kind of code") — similar in shape to the Companion's task-scoping, but triggered by IDE context rather than conversation. |
| **CLI** | Anticipated, not yet existing | Direct, ad hoc lookup by identifier or keyword — the most literal query pattern, closest to reading the Index's raw discovery surface. |
| **Automation** | Anticipated, not yet existing | Validation-style queries — "does artifact X exist, and is it currently Accepted" — used to check assumptions (e.g., that a PR's cited Discovery is real and active) rather than to browse or present. |

The architectural point common to all eight: none of them requires a *different capability*. They require different **query shapes** — catalog browsing, task-scoped retrieval, status filtering, identifier lookup, existence/validation checks — over the same single discovery surface.

---

## 4. Information Model

Described conceptually — no schema, format, or storage implied. Determined by what the Canonical already states today, distinguishing what the Index can faithfully *reflect now* from what it could only *represent later*, and only once the Canonical itself grows the underlying metadata through Governance.

**Primary fields — directly and unambiguously reflectable from the Canonical as it exists today:**

| Field | Source in the existing Canonical |
|---|---|
| Canonical ID | Already present on every governed document (GV-0001, STD-0001, DISC-0001, OM-0001, ARCH-0001, CS-0001) as explicit metadata. |
| Title | The document's own heading. |
| Domain | Unambiguous from the existing `docs/00-07` folder structure — Governance, Standards, Discoveries, Operating Model, Reference Architectures, Case Studies, Guides, Glossary. |
| Artifact Type | Already implied by domain and document convention (Specification, Discovery, ADR, Reference Architecture, Case Study, Guide, Glossary Term). |
| Lifecycle Status | Already stated in each document's metadata header (Draft/Accepted/Revised/Superseded/Archived, per GV-0008). |
| Relationships / Dependencies | Already declared inline today (e.g., "Operationalizes DISC-0002," "Related Specifications," "Related Evidence") — the Index's job is to aggregate what's already asserted into one queryable structure, not to infer or invent new relationships. |

**Secondary fields — named in this Work Item's examples, but not presently first-class canonical metadata:**

| Field | Assessment |
|---|---|
| Knowledge Layer | Maps to the structural layering this Architecture Team proposed in AARCH-0002 (constitutional / evidence-to-norm / execution / consolidating / supporting) — but that layering is itself advisory, not yet governed. Using it as Index metadata today would present un-ratified architectural commentary as if it were canonical fact. Should only become a primary field if AARCH-0002's classification is itself accepted through Governance. |
| Audience | Maps to IA-0001's six navigation personas — also advisory, not a field any canonical document currently declares about itself. Same caveat as Knowledge Layer. |
| Tags | Not present anywhere in the Canonical today. Domain and Artifact Type can serve much of this purpose already; introducing free-form tags would need its own Governance decision, not an Index-level invention. |
| Prerequisites | Partially present (e.g., "operationalizes," GUIDE-0000's stated reading order, OM-0002's "architecture is never inferred" implying Work Orders presuppose approved Architecture) but not systematically declared across all documents — reflectable where explicit, absent elsewhere. |

**Determination:** the Index's core information model should be built from the primary fields only. Secondary fields are legitimate future direction, but including them today would mean the Index silently asserting classifications (Knowledge Layer, Audience, Tags) that have not themselves passed through Discovery or Governance acceptance — precisely the kind of authority duplication this whole capability exists to prevent.

---

## 5. Relationships

| Related domain | Relationship to the Canonical Index |
|---|---|
| **Repository** | Strictly upstream. The Index reads from the Repository and never writes to it (ADR-0001's canonical-source-of-truth principle, applied here). The Repository remains authoritative regardless of what the Index reflects. |
| **Governance** | The Index reports governance-determined facts (status, acceptance) but never participates in governance decisions. A change in what the Index shows must originate from an actual Governance action (GV-0006, GV-0007, GV-0008); the Index is never itself the place such a change occurs. |
| **Standards** | The Index surfaces the existing Standards register (`01-standards/README.md`) plus each Standard's operationalizes-relationship back to its Discovery, making today's manual traceability queryable. |
| **Discoveries** | The Index surfaces Discovery status and maturity and which Standards/ADRs cite each one — enabling "what depends on this Discovery" queries that require manual cross-reading today. |
| **Guides** | Because Guides are explicitly non-normative (GUIDE-0000), the Index must preserve that distinction in its Artifact Type field rather than flattening Guides and Standards into one undifferentiated list. |
| **Reference Architectures** | Per AARCH-0002, Reference Architectures are themselves a consolidating/meta layer describing patterns found in other domains. The Index should represent an ARCH document's relationships as pointing *into* the domains it consolidates, not as an independent originating source of authority. |

---

## 6. Synchronization Model

Described architecturally — no generator, pipeline, or storage mechanism implied.

- **Regenerable, not hand-maintained.** The Index carries no state of its own that isn't derivable from the current Canonical. Architecturally, it must always be reconstructible from the Repository's present state — it is a projection, not a ledger.
- **Change-triggered, not schedule-driven.** Conceptually, whatever marks a canonical document's status change (a Governance action under GV-0006/0007/0008, or a Release under OM-0005) is what should mark the Index as eligible for refresh — synchronization is tied to actual Canonical change events, not to an arbitrary cadence.
- **Freshness is a first-class concept, mechanism is not.** Consumers should be able to know whether they are looking at a current or a potentially stale reflection, without needing to know *how* refresh happens.
- **One-way dependency, always.** Repository → Index, never Index → Repository. If the Index appears to misstate something, the fix is either in the canonical document being reflected, or in the reflection logic — never a direct edit to the Index in isolation. This is the architectural expression of IA-0001's Navigation Principle 3 ("no navigation artifact carries authority"), applied specifically to synchronization.
- **No independent version lifecycle.** The Index's "version" is a freshness marker — as of which Canonical state it was last derived — not a knowledge-maturity marker of its own. It must not acquire the Draft→Accepted→Superseded lifecycle (GV-0008) that governed knowledge artifacts have; that lifecycle belongs to the Canonical, not to its reflection.

---

## 7. Navigation Model

Extending IA-0001's per-audience navigation models: every consumer queries the same discovery surface, but the *shape* of the query differs by consumer, not the underlying capability:

- **Catalog queries** (Website): "list all Standards," "list all Guides in reading order" — broad, register-style retrieval.
- **Task-scoped queries** (Engineering Companion, IDE Integrations): "what governs this kind of work" — a narrow, bounded context set resolved on demand, never the whole corpus.
- **Status/maturity-filtered queries** (Curator/Maintainer): "list all Draft Discoveries," "list all candidate Glossary terms" — the maintenance-queue view.
- **Identifier/keyword lookup** (CLI): direct retrieval by Canonical ID or free-text match — the most literal query shape.
- **Exposure/pass-through** (Future MCP Servers): the Index's discovery surface presented outward largely as-is, to tools that were never designed with AAOE's structure in mind.
- **Existence/validation checks** (Automation): "does artifact X exist, and is it currently Accepted" — a boolean/assertion query rather than a browsing one.
- **Rendered, indirect consumption** (Human Engineers): humans mostly never query the Index directly; they consume whichever of the above a downstream view already rendered for them.

One coherent capability, five distinct query shapes — no consumer requires the Index to be architecturally different for their benefit.

---

## 8. Governance

- **Ownership of the Index's definition** (its reference architecture) sits with the same governance layer that owns every other Reference Architecture — meaning, were this formally adopted, it would be reviewed and accepted the same way ARCH-0001 through ARCH-0004 were.
- **Ownership of the Index's content** is a different question, and the answer is: nobody, by design. The Index has no independent authority to approve — there is no workflow for "approving what the Index says" beyond confirming it accurately reflects the Canonical it derives from. Governance applies to the Index's *design*, never to its *contents*.
- **Validation** of the Index's design (once formally proposed) is an Architecture Review matter (STD-0009/OM-0004), evaluating specifically whether the design preserves the no-duplicated-authority invariant — the same review discipline every other Reference Architecture undergoes.
- **Versioning** of the Index's *definition* would follow GV-0008 like any Specification. Versioning of the Index's *data*, per §6, is not a knowledge-maturity concept at all — it is a freshness marker tracking the Canonical's own state, not an independent evolution of knowledge.
- **Maintenance** of the Index's definition over time would sit with the Curator/Maintainer role (OM-0003) and the Architecture Team, consistent with how the existing Reference Architectures domain is already maintained.

---

## 9. Risks

1. **De facto second source of truth.** If the Index is faster or more convenient to query than the Repository, consumers may start trusting it over the Canonical in practice, even though it holds no authority in principle — the same dynamic IA-0001 flagged for the website, recurring here for a capability every other view would depend on, and therefore more consequential if it happens.
2. **Silent invention of secondary fields.** Any future implementation could quietly treat Knowledge Layer, Audience, Tags, or Prerequisites as first-class canonical facts before they've passed through Discovery or Governance — smuggling advisory classification in as though it were settled knowledge.
3. **Synchronization lag.** If refresh isn't tightly coupled to actual Canonical change events, a consumer could act on stale status (e.g., treating a Superseded Discovery as still Accepted).
4. **Consumer-specific logic creeping into the Index itself.** Building website-specific formatting or Companion-specific context-bundling directly into the Index's core model would recreate the exact per-consumer, divergent navigation logic this capability exists to eliminate.
5. **Unrepresented internal inconsistency.** If the Index is built to always resolve a single answer per query, it may be forced to silently pick a side on the corpus's existing unresolved disagreements (e.g., GV-0009 vs. OM-0006 on Core Domains) rather than surfacing the disagreement — quietly manufacturing consistency the Canonical doesn't actually have.
6. **Repository-boundary dependency.** The unresolved `aaoe` vs. `aaoe-specifications` split for Standards' authoritative text (flagged in IA-0001) directly affects the Index's Repository relationship (§5) — if that boundary shifts, the Index's source-of-truth pointer must follow, and an incorrect assumption here would make the Index reflect the wrong repository's content.

---

## 10. Recommendations

1. **Route this through Governance before treating it as architecture.** This report is a proposal, not an acceptance. If the Architecture Team wants the Canonical Index to become real, it should be captured as a Discovery from actual pilot experience (per GV-0006) and, if validated, proposed formally as a new Reference Architecture (a natural candidate ID would be ARCH-0005) — not adopted because this report describes it.
2. **Scope the first version to primary fields only.** Canonical ID, Title, Domain, Artifact Type, Lifecycle Status, and declared Relationships are ready today; Knowledge Layer, Audience, Tags, and Prerequisites are not, per §4, and should wait for their own governance decision.
3. **Resolve the `aaoe`/`aaoe-specifications` boundary first.** The Index's correctness depends on knowing, unambiguously, where each Standard's authoritative text lives (§5, §9.6) — this should be settled before the Index's Repository relationship is finalized.
4. **Pilot against the narrowest, most concrete consumer first.** The Curator/Maintainer maintenance-queue view (§3) needs only primary fields and has the clearest, most bounded query shape — a better proving ground than MCP Servers or IDE Integrations, which would immediately want secondary fields the Canonical doesn't yet have.
5. **Any future canonical-metadata expansion should go through Governance, not through the Index's implementers.** If Audience, Tags, or Prerequisites are later judged worth adding to source documents, that is a Canonical change like any other and belongs to GV-0006/0007, not to whoever eventually builds the Index.
6. **Capture pilot experience as evidence before generalizing.** Once a narrow pilot exists, its results should become a Discovery before the Canonical Index is generalized into a Standard or formal Reference Architecture — the same evidence-first discipline this Architecture Team has applied throughout its prior work.

---

## Repository Record

- **Branch:** `feature/AARCH-0004-canonical-index-architecture` (created from `release/v1.1`)
- **Files created:** `reports/2026-08-01-canonical-index-reference-architecture.md`
- **Files modified:** none
- **Commit:** `5a013a37d1e289623f275c114273e749f6bdcafe` — "docs(architecture): define canonical index reference architecture"
- **Timestamp:** 2026-08-01T23:01:22Z
- **Pull Request:** https://github.com/AI-Agent-Orchestrated-Engineering/aaoe/pull/61 (feature/AARCH-0004-canonical-index-architecture → release/v1.1)
