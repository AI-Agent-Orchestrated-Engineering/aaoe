# Implementation Report
### GUIDE-0001 (Work Item) — Engineering Recipes

Prepared per [STD-0010 — Implementation Reports](../docs/01-standards/0010-implementation-reports.md).

---

**Repository:** `AI-Agent-Orchestrated-Engineering/aaoe`

**Branch:** `feature/GUIDE-0001-engineering-recipes`

**Task Identifier:** GUIDE-0001 (Work Item label)

---

## Summary

Authored **GUIDE-0011 — Engineering Recipes**, introducing Engineering
Recipes as a standardized onboarding artifact: reusable Engineering
Companion prompts that let an engineer start real AAOE-governed
engineering work in their first conversation, rather than reading
documentation first. Includes the Recipe Structure Standard (Metadata,
Reference, Context, Project, Responsibilities, Handoff, Expected
Outcome), the complete Recipe 0001 ("Start a New Software Project")
prompt as specified, nine placeholder entries for future recipes, and
a Usage Guidance flow from conversational AI through to Implementation
Agent.

Four decisions made during this work, each recorded directly in the
Guide itself so a future reader doesn't have to reconstruct the
reasoning:

1. **Numbering.** The Work Item's own label, "GUIDE-0001," collides
   with the existing GUIDE-0001 (Thinking in Specifications). The new
   Guide is registered as **GUIDE-0011**, the next available
   identifier, with the collision noted at the top of the document
   itself — the same resolution pattern used for ERS-0001/STD-0013.
2. **Epistemic honesty about Engineering Companion.** This Guide's
   entire premise rests on the Engineering Companion pattern, which
   the [WI-0002 Discovery Assessment](2026-08-01-discovery-assessment-candidate-concepts.md)
   — this Curator's own prior, still-standing finding — evaluated and
   found not sufficiently evidenced, in tension with existing evidence
   (ARCH-0002's stateless Agent boundary). Rather than silently
   presenting Engineering Companion as settled practice, the Guide
   opens with an explicit status note, cites the Discovery Assessment
   by name, and frames the pattern as a recommended practice to try,
   not a validated body of knowledge — consistent with GUIDE-0000's own
   position that Guides are instructional and forward-looking, not
   normative, but without overstating what's actually been shown.
3. **Terminology reconciliation.** The Work Item's Usage Guidance flow
   used "Work Items" and "Implementation Prompt," neither of which is
   an existing canonical term. The Guide uses "Work Order" (OM-0002)
   and describes the implementation handoff informally, cross-
   referencing the Canonical Index Reference Architecture's discussion
   of a future "AI Execution Package" rather than asserting a new,
   unreconciled synonym — consistent with GV-0000's terminology-
   consistency principle and the terminology risks flagged in the
   original Architecture Impact Assessment.
4. **The website reference.** Recipe 0001 includes `https://aaoe.io`
   exactly as directed. Because the AAOE website does not yet exist
   (ROADMAP Phase 3; explicitly deferred by ADR-0002 and ADR-0005), the
   Guide states this plainly rather than presenting the reference as
   already live — the reference is included as instructed, framed
   honestly as forward-looking.
5. **The "five minutes" claim.** Framed throughout as this Guide's
   design goal, not a measured outcome — no timed onboarding session
   has been documented anywhere in the corpus (Architecture Impact
   Assessment, Gap G5; WI-0002 Discovery Assessment, Developer
   Experience finding).

---

## Files Created

- `docs/06-guides/0011-engineering-recipes.md`
- `reports/2026-08-01-guide-0001-engineering-recipes-implementation-report.md` (this report)

## Files Modified

- `docs/06-guides/README.md` — added the GUIDE-0011 register entry.

## Files Deleted

None.

---

## Pull Request

https://github.com/AI-Agent-Orchestrated-Engineering/aaoe/pull/64 (feature/GUIDE-0001-engineering-recipes → release/v1.1)

---

## Notes

- No specific AI model or vendor is named anywhere in the Guide or its
  recipe, consistent with the model-independence constraint.
- Recipe 0001's prompt text is reproduced verbatim as specified in the
  Work Item, with the "Continue the recipe using AAOE philosophy"
  instruction completed using existing canonical concepts (intent
  before design, the Specification "two-agents" test from GUIDE-0001,
  human governance per STD-0008/ARCH-0002) rather than newly invented
  ones.
- The Recipe Structure Standard explicitly requires Responsibilities to
  state a boundary (what the Companion shall never do), applying
  STD-0013's Non-Responsibilities discipline informally to Guide-level
  content, even though STD-0013 itself governs formal Engineering Role
  Specifications, not Guides.

## Questions

- Should Future Recipes (RECIPE-0002 through RECIPE-0009) be tracked as
  their own Work Items once evidence/priority supports writing them, or
  batched?
- Should this Guide's status note be revisited once/if the WI-0002
  Discovery Assessment's candidates are re-evaluated with new evidence?

## Known Limitations

- Recipe 0001 has not been used in a real conversation; its Handoff
  and Expected Outcome are designed, not yet observed in practice.
- The website reference is forward-looking; it will not resolve to a
  live page until Phase 3 of the Roadmap is activated.

---

## Repository Record

- **Branch:** `feature/GUIDE-0001-engineering-recipes` (created from `release/v1.1`)
- **Files created:** `docs/06-guides/0011-engineering-recipes.md`, `reports/2026-08-01-guide-0001-engineering-recipes-implementation-report.md`
- **Files modified:** `docs/06-guides/README.md`
- **Commit:** `bb071557af8a48afceb3a7fa1fda86b0394523c4` — "docs(guides): introduce engineering recipes (GUIDE-0011)"
- **Timestamp:** 2026-08-01T23:42:30Z
- **Pull Request:** https://github.com/AI-Agent-Orchestrated-Engineering/aaoe/pull/64 (feature/GUIDE-0001-engineering-recipes → release/v1.1)
