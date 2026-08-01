# AAOE Canonical Refactoring Roadmap
### CR-0001 — Phased Migration Plan from Current Canonical to Validated Target Architecture

**Prepared by:** AAOE Architecture Migration Planner (Curator Agent)
**Date:** 2026-08-01
**Status:** Advisory only — a plan, not an execution. No Canonical document was modified. No new concepts were introduced. No documents were rewritten. No repository taxonomy was changed. This report sequences work; it performs none of it.
**Governing inputs:** [System Boundary & Architecture Vision](2026-08-01-system-boundary-architecture-vision.md), [Conceptual Architecture Map](2026-08-01-conceptual-architecture-map.md), [Information Architecture Assessment](2026-08-01-information-architecture-assessment.md), [Canonical Index Reference Architecture](2026-08-01-canonical-index-reference-architecture.md), [Discovery Assessment (WI-0002)](2026-08-01-discovery-assessment-candidate-concepts.md).

---

## 1. Executive Summary

A verification before planning: PRs #59, #60, and #61 (Conceptual Architecture Map, Information Architecture Assessment, Canonical Index Reference Architecture) are confirmed merged into `release/v1.1` as of today. That much of the premise is accurate. But `release/v1.1` has not been merged into `main`, and — more consequentially for this roadmap — **none of the four prior reports touched `docs/00-07`.** All five documents this roadmap draws on, including this one, live in `reports/`, outside the canonical taxonomy. Nothing about the actual Canonical has changed. What exists today is a validated, merged *analysis* of where the Canonical is architecturally inconsistent and where it could grow — not yet any of that growth itself.

That is exactly why a roadmap is meaningful rather than redundant: if the target state were already realized, there would be nothing left to sequence. This roadmap identifies seven waves of actual Canonical work the four prior reports collectively imply, orders them by real dependency (not by the order they were written), and is explicit that every wave that touches `docs/00-07` must go through AAOE's own Engineering Lifecycle (OM-0001) and Governance processes (GV-0006/0007) like any other Canonical change — the advisory reports reaching `release/v1.1` via a plain merge does not exempt their recommendations from that discipline once those recommendations become actual edits to the Canonical.

The single highest-leverage sequencing insight: two waves have no dependency on anything else and should start immediately in parallel — **internal consistency corrections** (cheap, low-risk, unblocks everything downstream) and **evidence generation for the original candidate concepts** (the slowest wave, because it requires real practice, not document editing, and every week it's delayed is a week added to the critical path). Waves that add genuinely new canonical material — a formal Canonical Index Reference Architecture, any Discovery for Conversation-Driven Engineering or Engineering Companion — belong last, not first, and each is explicitly gated on evidence, not on architectural enthusiasm.

---

## 2. Current vs. Target Architecture

| | Current | Target (as described by the four prior reports) |
|---|---|---|
| **Domain consistency** | GV-0009 and OM-0006 disagree on which domains count as "Core Domains" (Guides/Glossary included in one, omitted from the other) — an inconsistency this Architecture Team has now flagged in three separate reports without resolving it. | One consistent, explicitly governed statement of the domain set. |
| **Role model** | ARCH-0001 names a "Knowledge Curator" actor that OM-0003's role model doesn't include. | Roles and reference-architecture actors reconciled — either OM-0003 gains the role or ARCH-0001's naming is corrected, decided through Governance, not assumed here. |
| **Repository boundary** | ADR-0002's intended hybrid strategy (`aaoe-specifications` as canonical Standards-text owner) has not been executed; full Standard text still lives in `docs/01-standards` today. | An unambiguous, current statement of where each Standard's authoritative text lives, reflected consistently everywhere that points to it. |
| **Terminology** | "Engineering Knowledge" (ARCH-0003's working title), "Organizational Knowledge" (formally defined), and "Engineering Memory" (glossary *candidate*) coexist without a stated relationship. | One reconciled definition per concept, with superseded/merged candidates explicitly marked as such — never silently dropped. |
| **Discovery/Navigation capability** | No shared discovery mechanism exists; each future consumer (website, Companion, curator tooling) would otherwise build its own list. | A Canonical Index exists as a formally accepted Reference Architecture (candidate ARCH-0005), scoped to primary fields only, per AARCH-0004. |
| **Candidate concepts** (Conversation-Driven Engineering, Engineering Companion, Knowledge-Driven Engineering, Engineering Observation, Knowledge Evolution, Engineering Knowledge Supply Chain) | Per the WI-0002 Discovery Assessment: none currently meet the Discovery Acceptance bar (GV-0006). No documented Observation exists for four of the seven; two duplicate DISC-0002. | Zero, some, or all of these become real Discoveries — strictly contingent on evidence that does not yet exist, not on architectural analysis that already does. |
| **Website** | Does not exist; explicitly deferred (ADR-0002, ADR-0005, ROADMAP Phase 3). | A presentation layer rendering the stabilized Canonical, per IA-0001's navigation models — downstream of everything above, not a parallel priority. |

The gap, stated plainly: every row in the "target" column requires an actual, governed change to `docs/00-07` (or a deliberate decision not to change it). None has happened yet. This roadmap sequences that work.

---

## 3. Refactoring Waves

### Wave 1 — Internal Consistency Corrections
**Objective:** resolve documented factual disagreements within the existing Canonical, introducing no new concepts.
**Documents affected:** `GV-0009` (Knowledge Domains), `OM-0006` (AAOE Meta-Model), `ARCH-0001` (Platform Reference Architecture), `OM-0003` (Roles & Responsibilities).
**Architectural rationale:** these are correctness fixes, not evolution — GV-0009 and OM-0006 cannot both be right about what counts as a Core Domain, and ARCH-0001's Knowledge Curator either belongs in OM-0003's role model or doesn't exist. Every later wave that reasons about "the domains" or "the roles" inherits whichever ambiguity is left unresolved here, so this is the cheapest possible point to fix it.
**Expected outcome:** one authoritative domain list; one authoritative role/actor model; zero self-contradiction on either question anywhere in the corpus.

### Wave 2 — Repository Boundary Resolution
**Objective:** determine, explicitly, whether ADR-0002's hybrid strategy (`aaoe-specifications` as canonical Standards-text owner) is executed now, deferred with a stated timeline, or revised.
**Documents affected:** `ADR-0002`, `01-standards/README.md`, potentially a new ADR recording the decision (not a rewrite of ADR-0002 itself, per GV-0000's "history preserved" principle — superseding, not editing).
**Architectural rationale:** flagged as a blocking dependency by both IA-0001 (the website's Standards section) and AARCH-0004 (the Canonical Index's Repository relationship). Left unresolved, both of those downstream efforts would have to encode a guess about where Standards live, and rework it later.
**Expected outcome:** every future reference to "the Standard's canonical text" points somewhere unambiguous and current.

### Wave 3 — Terminology Stabilization
**Objective:** reconcile Engineering Knowledge / Organizational Knowledge / Engineering Memory *(candidate)*, and clear the Glossary's other flagged *(candidate)* terms where enough usage now exists to settle them (e.g., AI Collaborator).
**Documents affected:** `07-glossary/*`, `ARCH-0003` (Engineering Knowledge Reference Architecture).
**Architectural rationale:** ARCH-0003 has used "Engineering Knowledge" as a working title since before this Architecture Team's review began, without ever being reconciled against the Glossary's separately-defined "Organizational Knowledge." Doing this after Wave 1 (not before) means terminology decisions are made against a domain model that isn't about to change out from under them.
**Expected outcome:** every term used more than once in the corpus has exactly one accepted definition; retired or merged candidates are marked superseded, not deleted (GV-0000).

### Wave 4 — Operating Model Enhancement: Release Synchronization Checkpoint
**Objective:** add a lightweight checkpoint to Release Management confirming derived navigation views (once any exist) remain consistent with any status change in the release being merged.
**Documents affected:** `OM-0005` (Release Management).
**Architectural rationale:** directly recommended by IA-0001 (Recommendation #5) as a low-cost way to prevent the "projection drift" risk that assessment identified, without introducing new governance machinery. Small, additive, and independent of every other wave — it can happen whenever convenient, but should exist before Wave 6 produces something (the Canonical Index) that would actually need it.
**Expected outcome:** Release Management explicitly accounts for keeping any future derived view in sync, closing a gap that currently doesn't exist because no such view exists yet either.

### Wave 5 — Evidence Generation for Candidate Concepts
**Objective:** produce actual, dated, attributable Observation documentation for Conversation-Driven Engineering, Engineering Companion, and Developer Experience — the three candidates the WI-0002 Discovery Assessment found had no supporting evidence at all (as opposed to Engineering-to-Execution Handoff and AI Execution Package, which that assessment found already duplicate DISC-0002).
**Documents affected:** none yet — this wave produces raw material for future Discoveries (`02-discoveries`), not documents themselves.
**Architectural rationale:** this is not a documentation task; it requires someone to actually run a timed onboarding session, capture a real instance of a conversation shaping a specification, or observe an AI acting in a continuous companion role, and document what happened. It is the only wave in this roadmap gated by real-world time rather than editing time, which makes it the critical-path item if it is not started immediately.
**Expected outcome:** either sufficient evidence exists to propose new Discoveries through the normal Discovery Acceptance Process (GV-0006), or the candidates remain correctly unaccepted — both are valid, successful outcomes of this wave; premature acceptance is not.

### Wave 6 — Canonical Index Formalization (candidate ARCH-0005)
**Objective:** propose the Canonical Index, as scoped in AARCH-0004, as a formal Reference Architecture — scoped to primary fields only (Canonical ID, Title, Domain, Artifact Type, Lifecycle Status, declared Relationships), per that report's own recommendation.
**Documents affected:** a new `04-reference-architectures/000X` document (candidate ARCH-0005); no existing Reference Architecture document is rewritten.
**Architectural rationale:** AARCH-0004 was explicit that this should not happen until (a) the repository boundary (Wave 2) is settled, since the Index's Repository relationship depends on it, (b) terminology (Wave 3) is stabilized, since the Index would otherwise index unratified terms as if settled, and (c) a narrow pilot (against the Curator's maintenance-queue view, the narrowest consumer identified) has produced its own Discovery-stage evidence, per that report's own evidence-first recommendation.
**Expected outcome:** a governed, Accepted Reference Architecture for the Canonical Index — or a documented decision that the evidence doesn't yet support one.

### Wave 7 — Website Synchronization (non-canonical, downstream, continuous)
**Objective:** build the website's navigation to render whichever of Waves 1–6 have actually completed, per IA-0001's Canonical Mapping.
**Documents affected:** none in `docs/00-07` — this wave is explicitly outside the Canonical (ADR-0001, ADR-0003) and outside this roadmap's authority to schedule as "Canonical work."
**Architectural rationale:** listed last not because it is unimportant, but because IA-0001's own Canonical Mapping table depends on Waves 1 and 2 (domain consistency, Standards location) at minimum being settled — building it earlier means building it on assumptions that are still in motion.
**Expected outcome:** a website that renders a stabilized Canonical rather than one that has to be reworked each time an upstream wave lands.

---

## 4. Dependency Analysis

```
Wave 1 (consistency)  ──┐
                        ├──▶ Wave 3 (terminology) ──┐
Wave 2 (repo boundary) ─┘                            ├──▶ Wave 6 (Canonical Index / ARCH-0005)
                                                       │
Wave 5 (evidence generation) ── (independent, longest lead time, starts now) ──▶ feeds future Discoveries,
                                                                                  independently of Waves 1–4/6

Wave 4 (release sync checkpoint) ── independent, low cost, anytime before Wave 6 lands

Waves 1 + 2 (minimum) ──▶ Wave 7 (website) — ideally also Wave 3 and Wave 6, but not strictly blocking
```

| Item | Depends on | Why |
|---|---|---|
| Wave 1 | Nothing | Pure internal correction; can start immediately. |
| Wave 2 | Nothing | A repository-strategy decision, independent of Wave 1's content fixes. |
| Wave 3 | Wave 1 (recommended, not strict) | Terminology decisions made against a stable domain model don't need to be revisited if Wave 1 shifts domain boundaries afterward. |
| Wave 4 | Nothing | Additive, low-cost, can happen anytime. |
| Wave 5 | Nothing | Depends on real-world practice, not on any other wave's documents. |
| Wave 6 | Wave 2, Wave 3 (strict, per AARCH-0004 §10) | The Index's Repository relationship and information model both depend on these being settled first. |
| Wave 7 | Wave 1, Wave 2 (strict, per IA-0001's Canonical Mapping); Wave 3, Wave 6 (soft) | The website's navigation would otherwise encode assumptions still in motion. |

---

## 5. Risk Analysis

1. **Sequencing Wave 6 before Wave 2/3.** A Canonical Index built before the repository boundary and terminology are settled would encode a wrong Repository pointer or unratified terms as if they were fact — exactly the risk AARCH-0004 flagged, made real by doing the waves out of order.
2. **Deferring Wave 5.** Because evidence generation is the only wave gated by real-world time rather than editing time, starting it late doesn't just delay Wave 5 — it delays every candidate concept's eventual path to Discovery status, since nothing can substitute for the missing Observation documentation.
3. **Sequencing Wave 7 before Wave 1/2.** A website built on the current, still-inconsistent domain model or an unresolved Standards location would need rework the moment either is resolved — the exact "Standards-location ambiguity" risk both IA-0001 and AARCH-0004 already named.
4. **Treating advisory-report merges as Canonical acceptance.** PRs #59–#61 landing in `release/v1.1` is a real, verified fact — but it is a merge of *analysis*, not an Architecture Review acceptance of any *change* to `docs/00-07`. Proceeding as though the target architecture is already "approved" in the Governance sense (GV-0001, GV-0007) would skip the review step every other Canonical change goes through.
5. **Resolving Wave 1's inconsistency unilaterally.** If GV-0009 and OM-0006's disagreement is "fixed" by simply editing one file to match the other, without a documented decision (an ADR or equivalent), the fix itself becomes a new, unreviewed assertion — the same category of governance shortcut this Architecture Team has flagged throughout its prior work.
6. **Fast-tracking Wave 6 or any Wave-5-derived Discovery.** Both AARCH-0004 and the WI-0002 Discovery Assessment were explicit that evidence must precede acceptance. Enthusiasm for the Canonical Index or for Conversation-Driven Engineering is not evidence; skipping the Discovery Acceptance Process (GV-0006) to move faster reintroduces the exact governance-bypass risk identified in the very first Architecture Impact Assessment of this engagement.

---

## 6. Migration Strategy

Evaluated objectively against the options this Work Item named:

- **"Architecture first" is correct, but incompletely specified — the precise claim is "internal consistency and boundary decisions first."** Waves 1 and 2 have no dependencies, are the cheapest to execute, and are blocking prerequisites for nearly everything else. They are architecture work in the narrowest sense: fixing what the Canonical already asserts about itself, not adding anything new.
- **"Glossary first" is correct only relative to what comes after it, not what comes before it.** Terminology stabilization (Wave 3) should follow Wave 1, not precede or replace it — reconciling terms against a domain model that's about to change wastes the reconciliation.
- **"Cross-reference updates" is not an independent wave — it is the mechanical tail of Waves 1–3.** Any document whose links or citations point at a term, domain, or role that Waves 1–3 change needs its cross-references updated as part of finishing that wave, not as a separate pass afterward.
- **"Terminology stabilization" is Wave 3, positioned deliberately after structural corrections (Wave 1) and before any new artifact that would cite unsettled terms (Wave 6).**
- **"Website synchronization" is correctly last, and continuous rather than a single wave.** IA-0001 already established the website as a downstream, non-authoritative presentation layer; nothing about this roadmap changes that — it only adds that building it before Waves 1–2 land means building it twice.
- **The one strategy option not named in the prompt but required by the evidence: evidence generation (Wave 5) runs in parallel with everything else, starting immediately, precisely because it is the only wave not gated by document-editing sequence at all.**

**Objectively determined order:** Waves 1 and 2 in parallel (no shared dependency) → Wave 3 → Wave 4 (whenever convenient, no strict position) → Wave 6 → Wave 7, continuously downstream — with Wave 5 running in parallel to all of the above from day one, on its own evidence-bound timeline.

---

## 7. Success Criteria

A successfully refactored Canonical is one where:

1. **No internal inconsistency remains undocumented.** GV-0009 and OM-0006 state the same domain set; ARCH-0001 and OM-0003 agree on what actors/roles exist — and if either was resolved by choosing one side over the other, that choice is recorded as a decision (an ADR or equivalent), not a silent edit.
2. **Every reference resolves to an actually-authoritative location.** The `aaoe` / `aaoe-specifications` boundary is stated unambiguously, and nothing in the corpus points to a Standard's text in a way that's now wrong.
3. **Every multiply-defined term has exactly one accepted definition**, with any merged or retired *(candidate)* clearly marked superseded rather than silently removed (GV-0000's history-preservation principle intact).
4. **Every new artifact introduced during this migration — a Canonical Index Reference Architecture, any Discovery arising from Wave 5 — passed through the same Discovery → Governance → Acceptance path as every existing artifact.** No fast-tracking, regardless of how validated the underlying analysis felt.
5. **Traceability remains unbroken throughout** (GV-0002) — every changed or added artifact still traces to the evidence that justified it.
6. **The advisory reports this Architecture Team produced are resolved, not left permanently ambiguous.** Each either results in an actual, governed Canonical change, or a documented decision not to make one — they do not linger indefinitely as merged-but-unactioned analysis.
7. **No canonical knowledge was ever duplicated into a navigation, index, or website layer during the process** — the invariant IA-0001 and AARCH-0004 both established holds not just as an end state, but at every intermediate point of the migration.
