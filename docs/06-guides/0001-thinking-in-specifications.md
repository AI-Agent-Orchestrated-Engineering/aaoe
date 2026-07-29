# Thinking in Specifications

## Guide Metadata

**Guide ID:** GUIDE-0001

**Domain:** Guides

---

## Why This Matters

Most of us learned to build software the same way: you get a problem, you
open your IDE, and you start writing code.

```text
Problem
    ↓
Open IDE
    ↓
Write Code
```

For a long time this worked fine, because the bottleneck was always
implementation. You, the human, were the only one who could turn an idea
into working software, so it made sense to get to code as fast as
possible and iterate from there. Thinking happened *in* the code — you'd
discover the real requirements by hitting edge cases, refactor, and
converge on something reasonable.

That approach breaks down the moment AI agents start doing meaningful
implementation work. If you hand an AI agent a vague idea, it will
confidently build the wrong thing — fast. The old failure mode was "I
wrote the wrong code and found out in code review." The new failure mode
is "I wrote the wrong code, an AI agent wrote a thousand more lines
consistent with it, and now I have a much bigger wrong thing to undo."
Skipping the thinking step doesn't just cost you time anymore. It costs
you *leverage*.

## The AAOE Mindset

AAOE asks you to move the thinking earlier:

```text
Problem
    ↓
Understand
    ↓
Specify
    ↓
Review
    ↓
Implement
    ↓
Validate
```

Implementation stops being the starting point and becomes a consequence —
something that falls naturally out of a specification that's actually
been thought through. This isn't about writing more documentation for its
own sake. It's about doing the hard part (deciding what should exist) in
a form that's cheap to review and correct, before you do the expensive
part (building it).

## Specifications Are Engineering Intent

A specification isn't a formality you write after you already know the
answer. It's where you work out the answer. A good one captures:

- objectives — what outcome are we actually after?
- constraints — what are we not allowed to do?
- assumptions — what are we taking for granted?
- expected behavior — what should the system do, concretely?
- acceptance criteria — how will we know it's done, and done right?

The test of a good specification is simple: could two different
engineers — or two different AI agents — read it and produce compatible
implementations? If the answer is no, the specification hasn't done its
job yet, no matter how much prose it contains.

## Thinking Before Building

Experienced engineers have always spent a disproportionate amount of time
just understanding the problem before touching a keyboard. That instinct
was always correct — it's just that AI makes it more valuable, not less.
Implementation used to be the expensive step, so unclear thinking got
naturally rate-limited by how slowly you could type. Now implementation is
comparatively cheap. Unclear thinking no longer gets rate-limited by
anything. It scales exactly as fast as your AI agents can produce output
from it — which is to say, very fast.

## From Conversation to Specification

Here's what this looks like in practice. Someone hands you:

```text
Build a login screen.
```

That's a request, not a specification. An engineer thinking in
specifications turns it into a set of real questions before writing
anything:

- Who are the users?
- Mobile or desktop?
- Authentication only, or authorization too?
- What does error handling need to cover?
- Any accessibility requirements?
- How should sessions be managed?

Answering those — even roughly — turns "build a login screen" into
something an implementer, human or AI, can actually act on without
guessing.

## Human + AI Collaboration

Specifications become the shared language you and an AI agent use to
converge on the same thing:

```text
Engineer
        ↓
Specification
        ↓
AI Draft
        ↓
Human Review
        ↓
Improved Specification
        ↓
Implementation
```

The AI is good at expanding a specification into implementation quickly,
and often good at surfacing gaps in the specification itself when it
tries. But engineering intent — what should this system actually do, and
why — stays with you. That division doesn't change no matter how capable
the AI gets.

## Common Mistakes

A few patterns worth watching for, because they show up constantly:

- **Starting with code.** The oldest habit is the hardest to break.
- **Vague prompts.** "Make it better" isn't a specification, it's a wish.
- **Missing acceptance criteria.** Without them, "done" is a matter of
  opinion.
- **Hidden assumptions.** The ones you don't write down are the ones that
  bite you.
- **Mixing requirements with implementation.** "Use a dropdown" is an
  implementation choice hiding inside what should be a behavioral
  requirement.

Each of these seems small in isolation. Multiplied across an AI agent's
implementation speed, they stop being small.

## Practical Exercise

Take this request:

```text
Add notifications.
```

Before writing any code, rewrite it as a one-page engineering
specification.

As you do, sit with these questions rather than rushing past them:

- What are you assuming about who receives a notification, and why?
- What would "done" look like to someone who didn't write the spec?
- If you handed this page to someone else, could they build the same
  thing you're picturing?
- What did you almost leave out?

## Key Takeaways

- Think before you implement — the thinking is the expensive, valuable
  part now.
- Specifications reduce ambiguity for whoever implements next, human or
  AI.
- AI amplifies whatever you feed it, including a bad specification.
- Engineering intent, clearly captured, is the foundation everything else
  in AI-assisted engineering builds on.

## What Comes Next

Once you've made the shift to thinking in specifications, the natural
next question is how to actually work with AI day to day — how to hand
off a specification, review what comes back, and keep the collaboration
productive. That's **GUIDE-0002 — Working with AI**.
