# AAOE Discovery Assessment
### WI-0002 — Discovery Authoring: Candidate Concepts from the Architecture Impact Assessment

**Prepared by:** AAOE Canonical Curator (Discovery Assessment)
**Date:** 2026-08-01
**Status:** Advisory only — not reviewed, not accepted, not canonical. No AAOE Canonical document was modified. No Discovery records, Standards, ADRs, or Guides were drafted or created.

---

## 1. Executive Summary

None of the five candidate concepts currently meet AAOE's own Discovery Acceptance criteria (GV-0006) or Evidence Standard (GV-0005). This is not a close call on most of them.

The Work Item's framing states that "the AAOE architects continued validating the methodology while evolving the AAOE Website and discussing the practical experience of engineers using AAOE." That framing is a narrative claim, not evidence. Per GV-0005, evidence must be observable, traceable, attributable, and "shall not depend upon authority." A search of this repository finds **no website directory, no website case study, no DX measurement, no observation log, and no documented conversation record of any kind** supporting that narrative — `research/` and `archive/` are empty placeholders, and ROADMAP.md explicitly defers the website to a future, not-yet-triggered phase. The sole documented evidence source in the entire corpus remains **CS-0001 (SolOh ERP Modernization)**, and it does not mention a website, a conversational companion, or developer-experience observations at all.

Two of the five candidates (**Engineering-to-Execution Handoff**, **AI Execution Package**) describe a pattern that *is* evidenced — but the evidence already belongs to an existing Discovery (DISC-0002) and an existing Specification (OM-0002, Work Orders). They are not new observations; they are restatements of a settled one.

One candidate (**Engineering Companion**) doesn't just lack evidence — the evidence that *does* exist (ARCH-0002's stateless, no-inherited-context agent boundary, validated against CS-0001) points the opposite direction. Treating it as a Discovery today would mean asserting a new observation that contradicts already-accepted evidence, which is exactly the situation GV-0005 requires additional, explicit, attributable evidence to resolve — not narrative assertion.

The remaining two (**Conversation-Driven Engineering**, **Developer Experience**) are plausible future Discoveries in principle, but nothing in this repository currently documents the underlying Observation with enough specificity, attribution, or reproducibility to progress past the "Observation" stage of GV-0006's lifecycle (`Observation → Documented → Evidence Attached → Architecture Review → Accepted Discovery`).

**Recommendation: zero new Discovery records at this time.** The correct next governance action is not drafting Discoveries — it is producing the actual Observation documentation (dated notes, transcripts, measurements, or a new Case Study) that Discoveries are supposed to summarize. That documentation does not yet exist.

---

## 2. Evidence Matrix

| Candidate | Evidence found in repository | Source project(s) | Reproducibility | Confidence |
|---|---|---|---|---|
| **Conversation-Driven Engineering** | Only informal, narrative material: GUIDE-0001 ("Thinking in Specifications") walks through turning a vague request into clarifying questions; GUIDE-0002/0006 describe iterative dialogue with AI. No dated Observation, transcript, or measurement exists showing conversations *consistently* preceded architecture across multiple instances. | None documented as evidence (Guides are instructional, not evidentiary per GV-0000/GUIDE-0000's own Standards-vs-Guide distinction) | Not assessed — no raw observation exists to reproduce | **Low** |
| **Engineering Companion** | None. CS-0001 documents specialized, stateless, task-scoped AI agents coordinated through Work Orders — the opposite interaction model. ARCH-0002 states agents "never hold architectural... authority" and receive no inherited context. No case, log, or example anywhere shows an AI acting as a continuous cross-lifecycle collaborator. | None | Not applicable — no observation exists | **None / Contradicted by existing evidence** |
| **Engineering-to-Execution Handoff** | Fully evidenced, but as part of an *existing* Discovery: CS-0001 "Specifications over prompts" section and DISC-0002 already document that structured specifications outperform ad-hoc prompts, with implementation quality becoming "repeatable rather than dependent on how a given prompt happened to be phrased." OM-0002 (Work Orders) is the existing formalized mechanism for this. | SolOh ERP Modernization (Authentication vertical slice) — CS-0001 | Demonstrated once, in the Authentication slice; not yet repeated across additional slices | **Moderate-High**, but attributed to DISC-0002, not a new observation |
| **AI Execution Package** | Same evidence base as above; no evidence distinguishes a package format from the existing Work Order. STD-0003's own "Future Evolution" section already names "Agent Context Contracts" as an anticipated, not-yet-evidenced, next step. | SolOh ERP Modernization — CS-0001 (indirectly) | Not applicable — no distinct artifact has been observed | **Low** as a distinct concept |
| **Developer Experience** | "Onboarding" appears exactly twice, in passing, as a qualitative side-benefit of context engineering (DISC-0005, DISC-0006, GUIDE-0005) — never measured, no baseline, no target, no timed session on record. The "<5 minutes" figure appears nowhere in the corpus prior to the Architecture Impact Assessment that introduced it as a candidate framing. | None documented | Not assessed — no measurement exists to reproduce | **Low** |

---

## 3. Discovery Recommendation

| Candidate | Disposition | Reasoning |
|---|---|---|
| **Conversation-Driven Engineering** | **More evidence required** | Plausible in principle, but no dated, attributable Observation exists distinguishing "conversation precedes architecture" as its own pattern, separate from what DISC-0002 already covers (specs vs. prompts). GV-0006 requires "a clearly stated engineering observation" with "supporting evidence" — neither exists yet in documented form. |
| **Engineering Companion** | **Reject at this time (not sufficiently evidenced; conflicts with existing evidence)** | The only documented evidence on this exact question (ARCH-0002, validated against CS-0001) shows the opposite pattern: stateless, task-scoped agents with no inherited context, never holding authority. GV-0005 permits conflicting evidence to "reveal boundary conditions," but that requires *new, attributable* evidence of the claimed pattern — not an assertion that it occurred. None is on record. Rejection per GV-0006 does not invalidate the underlying idea; it can be reconsidered if a specific, attributable instance is documented. |
| **Engineering-to-Execution Handoff** | **Merge into existing Discovery (DISC-0002)** | The observation described — structured artifacts outperforming ad-hoc prompts — is already the substance of DISC-0002 and is already formalized as OM-0002 (Work Orders). This is a restatement, not a new observation. If a genuinely distinct pattern emerges (e.g., a package format Work Orders can't express), it would need its own new evidence, not a rename of existing evidence. |
| **AI Execution Package** | **Merge into existing Discovery (DISC-0002) / flag as anticipated future work (STD-0003)** | No evidence distinguishes this from the Work Order already in place. STD-0003 already reserves this exact territory under "Future Evolution → Agent Context Contracts" — the corpus has already correctly classified this as *not yet evidenced*, which this assessment confirms remains true. |
| **Developer Experience** | **More evidence required** | Onboarding is mentioned only as an informal aside, never measured. Before this can become a Discovery, someone needs to actually run and document a timed onboarding session (or several) as a dated Observation. Nothing currently in the repository does this. |

---

## 4. Draft Discovery List

**No new Discovery records are recommended for creation at this time.** Per GV-0006, "not every observation becomes an Accepted Discovery," and rejection "does not invalidate the observation" — additional evidence may support reconsideration later. The table below reserves provisional dispositions only; no IDs are being claimed or drafted.

| Candidate | Recommended disposition | Provisional next ID (only if/when evidenced) |
|---|---|---|
| Conversation-Driven Engineering | Hold — pending a documented Observation | DISC-0009 *(not assigned; reserved only if evidence materializes)* |
| Engineering Companion | Hold — pending attributable evidence that doesn't merely restate the proposal | Not assigned |
| Engineering-to-Execution Handoff | No new record — already covered by DISC-0002 | N/A |
| AI Execution Package | No new record — already anticipated in STD-0003 Future Evolution | N/A |
| Developer Experience | Hold — pending a measured onboarding Observation | Not assigned |

No Standards, ADRs, or Guides are implied or drafted by this table. It exists solely to tell the architects what evidence-gathering work — not documentation work — would need to happen next.

---

## 5. Governance Assessment

**Partially correct, not yet complete.** The sequencing intent is right: this Work Item correctly routes the candidate concepts through Discovery consideration before any ADR, Standard, or Guide, which is what GV-0001/GV-0004 require and what the prior Architecture Impact Assessment recommended.

But GV-0006's actual lifecycle is `Observation → Documented → Evidence Attached → Architecture Review → Accepted Discovery`. This assessment could only evaluate the *first* stage, and found that for four of the five candidates, no documented Observation exists at all — only narrative assertions in the Work Item's framing and in the prior Architecture Impact Assessment (which was itself explicitly an analysis of a hypothetical proposal, not a source of evidence per GV-0005's "shall not depend upon authority" — including the authority of a prior assessment). Treating "architects discussed this" as evidence, without a documented, attributable, reproducible record of what was actually observed, is precisely the shortcut GV-0005/GV-0006 exist to prevent, and precisely Risk #1 flagged in the prior Architecture Impact Assessment.

**The corrected next step is not writing Discoveries — it is writing Observations.** Someone with direct access to the underlying practical experience (the actual website work, the actual engineer conversations) needs to document specific, dated, attributable instances: what was observed, in what context, by whom, with what evidence. Only once that documentation exists can it be evaluated against GV-0006's acceptance criteria. This report cannot manufacture that evidence on the architects' behalf, and doing so would violate the objectivity this Work Item explicitly requires.

---

## Repository Record

- **Files created:** `reports/2026-08-01-discovery-assessment-candidate-concepts.md`
- **Files modified:** none
- **Branch:** `release/v1.1`
- **Commit:** `34b6933f7ab6eb9f42978f6ad15dbbf3e19789cd` — "feat(discovery): assess conversation-driven engineering discoveries"
- **Timestamp:** 2026-08-01T22:24:23Z
