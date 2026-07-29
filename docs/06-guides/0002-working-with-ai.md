# Working with AI

## Guide Metadata

**Guide ID:** GUIDE-0002

**Domain:** Guides

---

## AI Is Your Engineering Collaborator

Let's get one thing clear up front: AI is not a replacement for engineers.
It's a collaborator, and a genuinely capable one — but the relationship
only works if you're honest about what belongs to whom.

AI contributes:

- implementation
- exploration
- analysis
- documentation
- review
- brainstorming

Humans remain responsible for:

- engineering intent
- architecture
- governance
- trade-offs
- approval

AI accelerates engineering. It does not replace engineering judgment. If
you find yourself deferring judgment calls to the AI instead of
accelerating your own, something in the collaboration has gone sideways.

## Start With Intent, Not Prompts

This follows directly from [GUIDE-0001](0001-thinking-in-specifications.md),
and it's worth restating here because it changes how the conversation
itself should sound.

A poor interaction starts with a bare request:

```text
Build me a login screen.
```

A better interaction starts with intent, and asks for engagement before
implementation:

```text
Here is the specification.

Review it.

Identify ambiguities.

Suggest improvements.

Only after review should we discuss implementation.
```

The difference isn't stylistic. The first prompt hands the AI a blank
canvas and hopes for the best. The second gives it something to push back
on — and pushing back is where the value is.

## Treat AI Like a Senior Collaborator

Think of the AI as an experienced teammate, not a code vending machine.
Don't ask:

```text
Write code.
```

Ask the questions you'd ask a sharp colleague reviewing your plan:

- What assumptions are missing?
- What edge cases do you see?
- What would concern you in production?
- How could this specification fail?

Good engineering conversations produce better software — that was true
before AI, and it's still true now. The medium changed. The principle
didn't.

## Engineering Is Iterative

Productive collaboration with AI looks like a loop, not a single
transaction:

```text
Specification
        ↓
AI Feedback
        ↓
Human Refinement
        ↓
AI Draft
        ↓
Human Review
        ↓
Improved Solution
```

A handful of small iterations will consistently beat one enormous prompt
that tries to specify everything at once. Small loops surface problems
while they're still cheap to fix. Giant prompts hide them until you're
staring at a thousand lines of implementation built on a shaky
assumption.

## Ask Different Kinds of Questions

One thing that's easy to forget: the same AI can adopt very different
engineering perspectives depending on what you ask it to focus on.

**Architect**

```text
Challenge this design.
```

**Reviewer**

```text
Identify risks.
```

**QA**

```text
Find missing scenarios.
```

**Security**

```text
Look for vulnerabilities.
```

**Performance**

```text
What scalability concerns exist?
```

**Documentation**

```text
Explain this for another engineer.
```

Rotating through these lenses on the same specification will surface far
more than asking a single generic "does this look good?"

## Recognize AI's Limits

Part of working well with AI is knowing where it tends to fall short:

- Hallucinations
- Missing business context
- False confidence
- Hidden assumptions
- Outdated knowledge
- Inconsistent reasoning across sessions

None of this means you should distrust every output. It means you should
verify. Treat AI output the way you'd treat a draft from a new team
member you haven't calibrated with yet — probably good, worth checking,
not worth rubber-stamping.

## Keep Humans Accountable

This is worth repeating because it's easy to erode gradually: humans
remain accountable for architecture, governance, engineering decisions,
and production releases. That responsibility is never delegated to an AI,
no matter how good the output looks or how many times it's been right
before.

## Common Collaboration Mistakes

Patterns that quietly degrade engineering quality:

- Treating AI like a search engine.
- Treating AI like an oracle.
- Skipping reviews.
- Accepting first drafts.
- Writing giant prompts.
- Working without specifications.
- Asking implementation questions before understanding the problem.

Each of these trades a little short-term convenience for a larger
long-term cost — usually paid later, by someone doing a much harder
review than the one that got skipped.

## Practical Exercise

Take an existing specification you have lying around. Instead of asking
AI to implement it, ask it to:

- review it
- challenge assumptions
- identify ambiguity
- propose improvements

Watch how the specification changes before a single line of
implementation gets written. That shift — from "build this" to "help me
make sure this is right first" — is most of what this chapter is about.

## Key Takeaways

- AI is an engineering collaborator, not a replacement for engineering
  judgment.
- Specifications create productive conversations; bare prompts don't.
- Small iterative reviews outperform giant, all-at-once prompts.
- Verification is part of the collaboration, not a lack of trust in it.
- Human accountability never changes, regardless of how good the AI gets.

## What Comes Next

Once you know how to collaborate with AI productively, the next skill is
organizing that collaboration into clear, reviewable, executable work:
**GUIDE-0003 — Writing Good Work Orders**.
