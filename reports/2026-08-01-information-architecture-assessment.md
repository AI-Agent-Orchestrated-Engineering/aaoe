# AAOE Information Architecture Assessment
### IA-0001 — Multiple Navigation Views Over a Single Canonical Source

**Prepared by:** AAOE Curator Agent, acting as Information Architect
**Date:** 2026-08-01
**Status:** Advisory only — not reviewed, not accepted, not canonical. No Canonical document was modified. No repository structure was changed. No documents were moved. No knowledge was duplicated — every navigation model below is a sequencing or grouping of existing canonical documents, never a restatement of their content.

---

## Executive Summary

AAOE already has one coherent, well-governed source of truth — the eight-domain Canonical corpus mapped in AARCH-0002. What it does not yet have is any *deliberate* answer to "who reads this, in what order, for what purpose." Right now, the only navigation aid is a flat repository map (README.md) plus per-domain register tables (each `README.md` under `docs/0X-*`) — a filing-cabinet view, not an audience view. It works for someone who already knows the taxonomy; it does not work for a first-time engineer, a time-pressured practitioner, or a machine reading it as context.

The answer this assessment proposes is architecturally simple: **treat every audience-specific experience as a projection, not a copy.** A navigation model is nothing more than a curated sequence or grouping of pointers into the existing corpus. It carries no content of its own, and therefore carries no authority of its own — if a navigation view and the Canonical ever disagree, the Canonical is definitionally correct (this is already ADR-0001/ADR-0003's principle, just not yet applied to anything other than the website). Five human/AI audiences and one presentation surface (the website) can each get a purpose-built path through the same corpus without a single document moving, splitting, or being restated.

The main risk this introduces is not architectural — it's a maintenance discipline. Every projection can silently drift out of sync with the Canonical it derives from, and one projection (the website, by virtue of being the most visible) risks acquiring *perceived* authority it was never granted. Both are addressed in §Risks and §Recommendations without requiring any change to governance, taxonomy, or the Canonical itself.

---

## Repository Architecture (Current)

The current, unchanged Canonical structure (fully described in AARCH-0002's Domain Model, reused here without modification):

```
docs/
  00-governance/              rules for how knowledge is created/validated/evolved
  01-standards/               normative, required engineering practices
  02-discoveries/             evidence-based observations, first formal knowledge
  03-operating-model/         roles, lifecycle, Work Orders, releases
  04-reference-architectures/ consolidating, implementation-independent patterns
  05-case-studies/            primary empirical evidence (CS-0001, SolOh)
  06-guides/                  non-normative instructional material
  07-glossary/                cross-cutting terminology
agents/ · research/ · archive/   currently empty placeholders
```

The only existing navigation aids are: the root `README.md` (a flat repository map), each domain's `README.md` (a register table of that domain's documents and their status), and inline cross-links inside individual documents (e.g., a Standard citing the Discovery it operationalizes). There is no audience-specific entry point, no task-oriented index, and no machine-consumable manifest. This is the gap this assessment addresses — not by changing the structure above, but by designing views over it.

---

## Information Architecture (Proposed)

**Core principle:** every audience gets a *view* — an ordered or grouped set of links into the existing corpus, optionally with a short orienting sentence per stop — never new normative content. A view is documentation about how to read the Canonical, not a second place to read it.

Six views are proposed, one per required audience plus the website. None requires a new folder, a new document type, or a change to `docs/00-07`. Where a view would benefit from a durable home (e.g., a "Get Started" page), it belongs on the website (a presentation layer, per ADR-0003) or as a curated reading-order note *referencing* existing docs (as `GUIDE-0000` already does for the Guides domain, without duplicating anything the Guides themselves say) — not as new canonical content.

---

## Navigation Models

### 1. First-Time Engineer
**Goal:** understand AAOE, start a project, deliver the first Work Item.
**Consumption shape:** linear, narrative, one-time.

1. `README.md` — what AAOE is, in three sentences.
2. `GUIDE-0000` — Standards-vs-Guides distinction, reading order for the rest.
3. `GUIDE-0001` (Thinking in Specifications) — the mindset shift away from "open IDE, write code."
4. `GUIDE-0002` (Working with AI) — how humans and AI divide responsibility.
5. `OM-0001` (Engineering Lifecycle) — the shape of the process they're about to enter.
6. `OM-0002` + `GUIDE-0003` (Work Orders + Writing Good Work Orders) — the first artifact they'll actually produce.
7. `GUIDE-0010` (Complete End-to-End Example) — a concrete worked example, start to finish.
8. `STD-0002` (Specification-Driven Development) — the one normative rule they need before writing anything.

This path deliberately skips Governance (`00-governance`) entirely — a first-time engineer needs to *operate inside* the model, not *govern* it. Governance is reachable later, once they ask "why does it work this way," not before.

### 2. Practicing Engineer
**Goal:** execute efficiently, locate Standards fast, navigate Work Items, understand lifecycle.
**Consumption shape:** lookup-first, non-linear, high-frequency.

Not a reading order — a task-keyed index:

| "I need to..." | Go to |
|---|---|
| Check what a Standard requires | `01-standards/README.md` (register) → specific `STD-000x` |
| Write a Work Order | `OM-0002` + `GUIDE-0003` |
| Prepare for Architecture Review | `OM-0004` + `STD-0009` + `GUIDE-0004` |
| File an Implementation Report | `STD-0010` + `GUIDE-0008` |
| Recall a lifecycle stage | `OM-0001` (kept as a single-page quick reference) |
| Resolve a term | `07-glossary/README.md` |

This audience should never need to read narratively — the index above should get them to the exact `STD-`/`OM-` document in one hop.

### 3. Architect
**Goal:** understand architecture, relationships between concepts, governance, and referenced decisions.
**Consumption shape:** relational/graph, moderate frequency, "why" over "what."

1. `04-reference-architectures/README.md` — the consolidating layer, entry point for cross-domain patterns.
2. `00-governance/0000` through `0009` + `decisions/README.md` — the constitutional layer and its decision register.
3. `OM-0006` (AAOE Meta-Model) — the single consolidating diagram.
4. `GV-0002` (Traceability Model) — the cross-reference key for tracing any artifact back to its evidence.
5. `ARCH-0001` through `ARCH-0004` in sequence — Platform, AI Agent, Engineering Knowledge, Governance.

Supplementary, non-canonical orientation aids already produced by prior Curator Work Items — `2026-08-01-system-boundary-architecture-vision.md` and `2026-08-01-conceptual-architecture-map.md` under `reports/` — are useful entry material for this audience specifically, but must be presented as advisory synthesis, not as an alternative to reading the primary sources above.

### 4. Curator / Maintainer
**Goal:** maintain the Canonical, review contributions, evaluate Discoveries, maintain terminology, govern knowledge evolution.
**Consumption shape:** process-triggered, event-driven (a contribution arrives, a Discovery is proposed) rather than scheduled reading.

1. `CONTRIBUTING.md` — the contribution workflow entry point.
2. `GV-0006` (Discovery Acceptance Process) — triggered whenever a new Discovery is proposed.
3. `GV-0007` (Specification Governance) — triggered whenever a Specification/Standard is proposed or revised.
4. `GV-0003` (Body of Knowledge Governance) — the Artifact-Status vs. Knowledge-Maturity distinction, checked whenever a status change is being considered.
5. `GV-0008` (Versioning & Evolution) — checked whenever a document is superseded or revised.
6. `07-glossary/README.md` — specifically the *(candidate)* terms, which function as this audience's active maintenance queue.
7. `ROADMAP.md` + `CHANGELOG.md` — living state trackers, checked to know what phase of work the corpus is currently in.

### 5. Engineering Companion (AI consumer)
**Goal:** load context, look up knowledge, navigate, give engineering guidance, generate artifacts — using the Canonical as its knowledge source.
**Consumption shape:** on-demand, task-scoped, machine-resolved — never "reads the whole corpus" in one pass.

- **Context loading:** should be scoped by *task type*, not by folder. A request to help draft a Work Order should load `OM-0002` + `GUIDE-0003` + the relevant `STD-` document(s) it must satisfy — not the entire `docs/` tree. This is a direct application of `STD-0003` (Context Engineering)'s own principle that context is a first-class, deliberately scoped artifact, applied reflexively to the Companion's own consumption of AAOE.
- **Knowledge lookup:** any term must resolve through `07-glossary` before being asserted with confidence. Where the Glossary marks a term *(candidate)* (e.g., Engineering Memory, AI Collaborator), the Companion should surface that uncertainty rather than presenting it as settled — the Glossary's own self-flagging convention should propagate into how an AI reports confidence.
- **Navigation:** when asked "why" a rule exists, the Companion should walk `GV-0002`'s Traceability Model chain backward (Specification → Discovery → Case Study) rather than presenting a Standard as a bare assertion — this is what distinguishes AAOE-grounded guidance from generic advice.
- **Engineering guidance:** must preserve the Standards-vs-Guides distinction (`GUIDE-0000`) in how it speaks — representing Standards as "shall" and Guides as "consider," never blending the two registers.
- **Artifact generation:** any artifact the Companion drafts (a Work Order, a Discovery draft, an ADR) should conform to the existing canonical template for that artifact (`OM-0002`'s Work Order structure, `STD-0012`'s ADR structure, etc.) and must be marked as a proposal pending human review — the same non-negotiable boundary established in `ARCH-0002`/`STD-0008` for every other AI role in AAOE applies identically here. This section describes information architecture only; it does not specify prompts, tool design, or implementation.

### 6. Website (aaoe.io)
**Goal:** public-facing presentation of the Canonical. Not the Canonical — a rendering of it (ADR-0001, ADR-0003).
**Consumption shape:** shallow, exploratory, credibility-establishing — often someone's very first touchpoint, upstream of "First-Time Engineer" above.

Recommended top-level sections, each a rendering of an existing domain, none introducing new authoritative text:

- **Home** — drawn from `README.md` + `GV-0000`'s purpose statement.
- **Get Started** — a rendering of the First-Time Engineer path above.
- **Standards** — a browsable catalog rendering `01-standards/README.md`'s register, linking out to each `STD-` document's canonical text wherever it currently resides (see Canonical Mapping note below on the `aaoe` / `aaoe-specifications` split).
- **Guides** — a rendering of `06-guides`.
- **Discoveries & Case Studies** — a rendering of `02-discoveries` and `05-case-studies`, positioned as "the evidence behind AAOE."
- **Governance & Architecture** — a rendering of `00-governance` and `04-reference-architectures`, for architects and curators who arrive via the site.
- **Glossary** — a rendering of `07-glossary`.
- **Roadmap** — a rendering of `ROADMAP.md`.
- **Contribute** — a rendering of `CONTRIBUTING.md`.

---

## Knowledge Views

Navigation Models describe *paths*; Knowledge Views describe *how the same content is actually consumed* once reached — these are complementary, not the same thing:

| Audience | Mode | Frequency | Depth expectation |
|---|---|---|---|
| First-Time Engineer | Narrative, sequential | One-time (onboarding) | Conceptual understanding before rules |
| Practicing Engineer | Reference/lookup, non-sequential | High-frequency | Speed-to-answer over narrative |
| Architect | Relational/graph | Moderate, recurring | "Why," and cross-document consistency |
| Curator/Maintainer | Process-triggered | Event-driven | Governance-state precision |
| Engineering Companion | On-demand, task-scoped | Per-request | Exactly the slice needed, nothing more |
| Website visitor | Shallow, exploratory | Often once, pre-onboarding | Credibility and orientation, not mastery |

Every row consumes the *identical* underlying text (e.g., `STD-0002`'s content does not change based on who's reading it) — only the mode, frequency, and depth of engagement differ. No audience is ever shown a simplified, paraphrased, or audience-specific rewrite of a canonical document; that would constitute duplication.

---

## Canonical Mapping

Every proposed Website section maps to an existing canonical source, with no new authoritative text created:

| Website Section | Canonical Source | Notes |
|---|---|---|
| Home | `README.md`, `GV-0000` | Rendering only |
| Get Started | `GUIDE-0000/0001/0002`, `OM-0001/0002`, `GUIDE-0003`, `GUIDE-0010`, `STD-0002` | A sequenced rendering (the First-Time Engineer path) |
| Standards | `01-standards/README.md` register, individual `STD-000x` | Per ADR-0002, `aaoe-specifications` is intended to own canonical Standard text going forward; today the full text still resides in this repo's `docs/01-standards`. The website must link to wherever the text authoritatively resides at any given time — never fork or copy it. |
| Guides | `06-guides/README.md`, `GUIDE-000x` | Rendering only |
| Discoveries & Case Studies | `02-discoveries/README.md`, `05-case-studies/README.md` | Rendering only |
| Governance & Architecture | `00-governance/README.md`, `decisions/README.md`, `04-reference-architectures/README.md` | Rendering only |
| Glossary | `07-glossary/README.md` | Rendering only |
| Roadmap | `ROADMAP.md` | Rendering only |
| Contribute | `CONTRIBUTING.md` | Rendering only |

No section listed above restates a rule in its own words in place of the canonical text; each is a navigational/orienting wrapper around a link to the source.

---

## Navigation Principles

1. **Single source of truth, multiple projections.** Every navigation view is a filtered, sequenced, or grouped set of pointers into the same Canonical — never a copy of its content.
2. **Views differ by sequence and grouping, never by content.** The text a first-time engineer, a practicing engineer, and a website visitor eventually reach for `STD-0002` is identical; only the path to it differs.
3. **No navigation artifact carries authority.** An index, a sitemap, or a website page is never where a rule is defined. If a navigation view and the Canonical ever disagree, the Canonical wins by definition (ADR-0001, ADR-0003) — this principle already exists for the website and is extended here to every other view.
4. **Audience determines sequence and depth, not scope restriction.** A practicing engineer's index is faster to traverse than a first-time engineer's narrative path, but neither is shown an edited or partial version of a Standard — both eventually read the same document in full if they need to.
5. **Machine and human consumers share the same source, different retrieval strategy.** The Engineering Companion's context-loading must resolve to the identical canonical text a human would read at the same point in the corpus; only the retrieval mechanism (task-scoped query vs. linear reading) differs.
6. **Navigation evolves independently of the Canonical's governance cycle — until it would change what counts as authoritative.** Reordering an index or renaming a website menu label doesn't require Discovery Acceptance or Specification Governance, since no knowledge changes. Anything that would change which document a reader is pointed to for a given topic's authority does require going through that governance.

---

## Risks

1. **Projection drift.** Any navigation view (an index, a website nav tree, a Companion's cached context) can silently fall out of sync with the Canonical once a document's status changes (e.g., a Standard moves Draft → Accepted). None of the views proposed here include an update mechanism — this is a maintenance discipline risk, not an architectural flaw, but it is real from day one.
2. **Shadow canon via "helpful" paraphrase.** The greatest risk to Principle 2 is well-intentioned: a practicing-engineer quick-reference index that starts summarizing a Standard's requirement in its own words, rather than linking to it, becomes an un-governed second source for that requirement — exactly the duplication this assessment is constrained to avoid.
3. **Context staleness in the Engineering Companion.** If a Companion implementation caches or summarizes canonical content rather than re-resolving it per request, its internal representation can drift from the source document silently, with no governance event marking the divergence.
4. **Competing "first" experiences.** `README.md`, a future website "Get Started" page, and `GUIDE-0000`'s reading order are three independent candidates for "where a newcomer starts." Left unreconciled, they risk sending first-time engineers down three different first impressions rather than one coherent path.
5. **Perceived authority via visibility, not design.** ADR-0001/ADR-0003 assign the website zero authority, but a public, SEO-indexed website is likely to be seen, cited, and searched far more than the git repository itself. This is a socio-technical risk this Information Architecture cannot resolve by design alone — it can only be mitigated by making the "this is a presentation of the Canonical, see source" framing visible on every page.
6. **Standards-location ambiguity.** Because `aaoe-specifications`' intended role as the canonical Standards-text repository (ADR-0002) has not yet materialized, any navigation view pointing at "the Standard" currently means `docs/01-standards` in this repo — a website or index built today could hard-code that assumption and require rework once the hybrid strategy is actually executed.

---

## Recommendations

1. **Immediate:** before building any website navigation, produce a single authoritative Canonical Index (ID, title, domain, status, path) that every view — website, Companion, human indexes — draws from, rather than each view hand-maintaining its own list. This directly mitigates Risk 1 and Risk 4. (This is itself a candidate future Work Item requiring its own scoping — not undertaken here, since it would introduce a new artifact and this assessment is constrained to analysis only.)
2. **Immediate:** resolve where each Standard's authoritative text currently lives (`aaoe` vs. the still-pending `aaoe-specifications` hybrid strategy) before the website's Standards section is built — the mapping in §Canonical Mapping depends on this being unambiguous.
3. **Short-term:** reconcile the three candidate "first experiences" (`README.md`, `GUIDE-0000`, and any future website landing page) so they explicitly point to one another rather than compete, mitigating Risk 4.
4. **Short-term:** adopt the six navigation models in this report as the basis for the website's eventual sitemap — a distinct, future website-design Work Item, not undertaken here.
5. **Medium-term:** add a lightweight synchronization checkpoint to Release Management (`OM-0005`) confirming derived navigation views remain consistent with any status change in the release being merged — mitigating Risk 1 without introducing new governance machinery.
6. **Medium-term:** ensure every future website page carries a visible "this is a presentation of canonical content; see source" pointer, operationalizing Navigation Principle 3 visibly rather than leaving it purely architectural — mitigating Risk 5.
