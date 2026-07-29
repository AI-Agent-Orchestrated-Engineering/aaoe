# Implementation Reports

## Guide Metadata

**Guide ID:** GUIDE-0008

**Domain:** Guides

---

## Why Implementation Reports Matter

Engineering knowledge shouldn't disappear the moment code gets merged.
Future engineers should be able to understand:

- what changed
- why it changed
- what assumptions were made
- what remains unfinished

Implementation Reports preserve that knowledge, instead of letting it
evaporate the moment everyone's attention moves to the next task.

## Reports Capture Engineering Knowledge

An Implementation Report describes the engineering decisions made during
implementation. Typical topics include:

- completed scope
- implementation approach
- deviations
- discovered constraints
- unresolved issues
- recommendations

The goal is understanding, not status reporting. "Done" is not the
interesting part of the report. The interesting part is everything that
led there.

## Specifications vs Reality

Implementation sometimes differs from the original specification, for
reasons like:

- technical limitations
- better architectural discoveries made along the way
- clarified requirements
- performance improvements

None of that is a failure of planning — it's normal. What matters is that
the Implementation Report documents the difference, so the gap between
what was specified and what was actually built doesn't become invisible.

## Capture Decisions While They're Fresh

Write the report immediately after implementation, not weeks later.
Waiting leads to:

- forgotten trade-offs
- missing rationale
- undocumented discoveries
- inaccurate history

Knowledge decays fast. The reasoning behind a decision is sharpest in
your head the day you made it, and gets fuzzier every day after that —
usually right up until someone actually needs it.

## Reports Benefit Everyone

A good Implementation Report helps:

- future engineers
- Architecture Reviews
- maintenance work
- new team members
- AI collaborators
- future modernization efforts

Knowledge compounds over time — but only if it's actually written down
somewhere someone can find it later.

## Reports Strengthen Context

This connects directly back to
[GUIDE-0005 — Context Engineering](0005-context-engineering.md).
Implementation Reports become part of the engineering context available
to future work. Tomorrow's Work Orders benefit from today's reports — the
same way today's Work Orders benefited from yesterday's. Knowledge
becomes reusable precisely because someone bothered to write it down when
it was fresh.

## Common Reporting Mistakes

Watch for:

- describing commits instead of engineering
- omitting decisions
- hiding problems
- documenting only success
- writing reports months later
- focusing only on implementation details

Each of these produces a report that technically exists but doesn't
actually preserve anything useful — which quietly defeats the entire
point of writing one.

## Practical Exercise

Choose an existing implementation. Write a report answering:

- What was implemented?
- Why was it implemented this way?
- What changed from the specification?
- What remains unresolved?
- What should future engineers know?

Pay attention to how much of that knowledge simply isn't visible in the
source code itself — and how much of it would have been lost if nobody
wrote it down.

## Key Takeaways

- Reports preserve engineering knowledge that would otherwise be lost.
- They explain decisions, not commits.
- Implementation differing from specification is normal — documenting the
  difference is what matters.
- Context grows after implementation, not just before it.
- Future engineering benefits directly from today's reports.

## What Comes Next

Implementation Reports describe what happened during implementation.
Architecture Decision Records preserve the architectural decisions that
guide future engineering more broadly. That's
**GUIDE-0009 — Architecture Decision Records**.
