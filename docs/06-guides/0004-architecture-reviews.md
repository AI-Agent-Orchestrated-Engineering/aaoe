# Architecture Reviews

## Guide Metadata

**Guide ID:** GUIDE-0004

**Domain:** Guides

---

## Why Reviews Exist

Architecture Reviews are not about finding fault. If that's how they feel
in practice, something about the culture around them has drifted from
what they're actually for.

They exist to improve engineering decisions before those decisions become
organizational knowledge — before other people, and other AI agents,
start building on top of them. Catching a bad assumption during review
costs a conversation. Catching it three months later costs a migration.
Good reviews reduce future engineering cost, and that's the entire point.

## Reviews Are Collaborative

Think of an Architecture Review as an engineering conversation, not an
inspection. Participants work together to answer:

- Is the intent clear?
- Is the architecture coherent?
- Are trade-offs explicit?
- Are assumptions documented?
- Can future engineers understand these decisions?

The goal is shared understanding — not a scorecard, not a gate you
squeeze through, a genuine check that everyone involved actually
understands what's being decided and why.

## What Gets Reviewed?

Reviews focus on engineering artifacts, not people. That distinction
matters more than it sounds like it should. Typical review subjects:

- Specifications
- ADRs
- Work Orders
- Implementations
- Implementation Reports

The review evaluates the artifact. It never evaluates the person who
wrote it.

## Asking Better Questions

The single highest-leverage skill in a good review is asking questions
instead of stating verdicts.

Instead of:

```text
This is wrong.
```

Ask:

```text
What assumptions led to this decision?
```

Instead of:

```text
Use another framework.
```

Ask:

```text
What alternatives were considered?
```

Instead of:

```text
This won't scale.
```

Ask:

```text
What scalability assumptions were made?
```

Notice the pattern: every "better" version explores reasoning instead of
asserting an opinion. Opinions end conversations. Questions open them —
and it's in that open conversation that the actual improvement happens.

## Architecture Reviews with AI

AI can participate in reviews, and often should. It's good at:

- identifying risks
- detecting inconsistencies
- comparing alternatives
- reviewing traceability
- identifying missing references

AI contributes analysis. Humans approve decisions. That division doesn't
bend just because the AI's analysis happens to be excellent — analysis
and approval remain different responsibilities, held by different
parties, for reasons that have nothing to do with how good the analysis
is.

## Disagreement Is Valuable

Don't treat disagreement in a review as a problem to smooth over quickly.
Healthy Architecture Reviews surface:

- assumptions
- constraints
- trade-offs
- unknowns

Consensus is desirable, when it's earned. Learning is mandatory, whether
consensus arrives quickly or not. A review that ends in quick, easy
agreement without anyone's thinking having changed probably wasn't
looking hard enough.

## Common Review Mistakes

Patterns worth catching yourself doing:

- reviewing people instead of artifacts
- debating implementation instead of architecture
- introducing new requirements mid-review
- reviewing without context
- treating reviews as approvals only

Each of these turns a conversation meant to build shared understanding
into something narrower and less useful — a rubber stamp, a personal
critique, or a scope negotiation happening at the wrong time.

## Practical Exercise

Take an existing specification. Without changing the implementation, ask:

- What assumptions are missing?
- What alternatives exist?
- What risks remain?
- What references are absent?
- Would another team understand this six months from now?

Notice how the document itself starts to improve just from asking these
questions honestly — before a single line changes.

## Key Takeaways

- Reviews improve engineering knowledge, not just gate merges.
- Artifacts are reviewed — never people.
- Questions are more valuable than opinions.
- AI strengthens analysis; it doesn't replace approval.
- Humans approve architecture, full stop.

## What Comes Next

Reviews are only as good as the context available to the reviewer. If the
right information isn't accessible, even a well-run review will miss
things. That's what **GUIDE-0005 — Context Engineering** covers next.
