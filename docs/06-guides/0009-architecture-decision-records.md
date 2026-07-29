# Architecture Decision Records

## Guide Metadata

**Guide ID:** GUIDE-0009

**Domain:** Guides

---

## Why ADRs Matter

Architectural decisions often outlive the engineers who made them. The
person who decided why the system is shaped the way it is may be long
gone by the time someone else needs to understand — or reconsider — that
decision. Without preserved reasoning, future teams are forced to guess,
usually incorrectly, and often at exactly the moment it matters most.

ADRs prevent institutional amnesia.

## Decisions Are Different From Implementations

It's worth being precise about the distinction, because the two
documents serve different purposes entirely.

Implementation Reports answer: *"What happened?"*

ADRs answer: *"Why?"*

Both are necessary, but they're not interchangeable. A report full of
implementation history without any decision rationale leaves the same gap
an ADR full of rationale without any implementation history would leave
in the other direction.

## What Belongs in an ADR?

A good ADR captures:

- the architectural decision itself
- the problem being solved
- alternatives considered
- rationale
- consequences
- trade-offs
- future implications

Leave implementation details out. They belong in the Implementation
Report, and they age far worse than the reasoning does.

## Good ADRs Age Well

A good ADR should still be valuable years later, long after the specific
technology it was written about has changed or disappeared entirely.
Focus on:

- engineering intent
- decision rationale
- assumptions
- consequences

Avoid anchoring the document to temporary technology details. The
reasoning is what survives. The implementation details are what expire.

## ADRs Improve Future Decisions

A future engineer reading an old ADR should come away understanding:

- why the decision exists
- when it should be reconsidered
- what assumptions it depends on

That last one matters more than it might seem. Most decisions aren't
wrong when they're made — they become wrong when an assumption they
depended on quietly stops being true. An ADR that states its assumptions
explicitly gives someone a chance to notice that shift. ADRs also reduce
repeated debates: if the reasoning is already written down, nobody has to
relitigate it from scratch every time it comes up again.

## ADRs Strengthen Context

This connects directly to
[GUIDE-0005 — Context Engineering](0005-context-engineering.md). ADRs
become permanent engineering context — the kind that doesn't get stale
the way implementation notes eventually do. Future Specifications and
Architecture Reviews benefit directly from decisions made long before
them, provided those decisions were actually written down.

## Common ADR Mistakes

Watch for:

- documenting implementation
- documenting meetings
- documenting opinions
- recording decisions without rationale
- failing to revisit outdated ADRs
- creating ADRs for insignificant choices

Each of these either buries the reasoning under noise, or produces a
record with nothing worth preserving in it — which weakens the
organizational knowledge an ADR is supposed to build.

## Practical Exercise

Choose one important architectural decision from your own work. Write an
ADR explaining:

- the problem
- alternatives
- chosen solution
- trade-offs
- expected consequences

Then imagine reading it five years from now, with no memory of writing
it. Would you understand why the decision was made? If not, that's the
gap the exercise just found for you.

## Key Takeaways

- ADRs preserve architectural intent, not implementation history.
- They explain why, not how.
- Long-lived decisions deserve long-lived documentation.
- ADRs strengthen engineering context for everyone who comes after.
- Good architecture, properly recorded, becomes organizational memory.

## What Comes Next

You've now seen every major piece of the AAOE workflow individually. The
next Guide brings them together: **GUIDE-0010 — Complete End-to-End
Example** walks through how specifications, implementation reports, and
ADRs all fit together in a single, complete engineering workflow.
