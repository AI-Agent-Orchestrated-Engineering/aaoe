# Context Engineering

## Guide Metadata

**Guide ID:** GUIDE-0005

**Domain:** Guides

---

## Why Context Matters

Every engineering decision is only as good as the information available
when it was made. That's true whether the decision is made by a human or
an AI agent — neither can reason well about what it doesn't know.

Poor context leads to:

- incorrect assumptions
- duplicated work
- inconsistent implementations
- architecture drift
- AI hallucinations
- unnecessary rework

Better context produces better engineering decisions. That sounds almost
too obvious to write down, but most engineering organizations don't
actually treat context as something worth deliberately building. It just
accumulates, unmanaged, and everyone works around the gaps.

## Context Is More Than Prompts

It's easy to think of "context" as whatever text you paste into a prompt.
That's a small, transient slice of something much bigger. Engineering
context includes:

- Specifications
- Standards
- ADRs
- Work Orders
- Architecture Reviews
- Implementation Reports
- Existing source code
- Domain knowledge
- Business rules

Prompt text is just the transport mechanism — the pipe context happens to
flow through in a given conversation. The context itself, the accumulated
body of decisions and knowledge behind it, is the actual engineering
asset.

## Building Context Incrementally

Context isn't something you assemble once. It grows as engineering work
moves forward:

```text
Discovery
        ↓
Specification
        ↓
Architecture
        ↓
Implementation
        ↓
Implementation Report
        ↓
Knowledge
```

Each step enriches what's available for the next piece of work. A
Discovery becomes context for a Specification. A Specification becomes
context for an Architecture Review. An Implementation Report becomes
context for the next engineer — or the next AI agent — who touches that
part of the system.

## Good Context Is Curated

More context is not automatically better context. Dumping everything you
have at a problem tends to bury the signal that actually matters. Aim
for context that's:

- relevant
- current
- trustworthy
- traceable

And actively avoid:

- outdated documents
- duplicated information
- conflicting references
- unnecessary detail

Context quality matters more than context quantity. A single accurate,
current specification beats ten stale documents that all say slightly
different things.

## Context for Humans and AI

Humans and AI consume context differently — a human skims and infers, an
AI processes what it's given more literally — but both need the same
underlying engineering intent to work well. A well-structured repository
serves both. Good context reduces onboarding time for a new engineer and
improves the quality of AI collaboration, for the same underlying reason:
neither one has to guess at what's already been decided.

## Context Is a Competitive Advantage

Organizations accumulate engineering knowledge whether they mean to or
not. The question is what shape it takes.

Without Context Engineering, knowledge tends to become:

- tribal
- fragmented
- forgotten

With Context Engineering, the same knowledge becomes:

- searchable
- reusable
- reviewable
- improvable

That difference compounds. An organization that's deliberately engineered
its context gets faster and more consistent over time. One that hasn't
just keeps rediscovering the same things. Context, treated well, becomes
organizational capital — not a nice-to-have, but one of the more durable
assets an engineering organization can build.

## Common Context Mistakes

Patterns worth watching for:

- relying on memory
- undocumented decisions
- outdated specifications
- duplicated knowledge
- missing traceability
- providing everything instead of the right things

Each of these leaves the next person — human or AI — reconstructing
context that should have already been available, usually by guessing.

## Practical Exercise

Choose an existing feature. List every artifact someone would need to
understand before modifying it safely. Then go back through that list and
remove anything unnecessary.

When you're done, ask yourself honestly:

"Would another engineer — or another AI collaborator — have enough
context here to make good decisions?"

If the answer is no, you've just found exactly what's missing.

## Key Takeaways

- Context is an engineering asset, not an afterthought.
- Better context produces better decisions, for humans and AI alike.
- Context evolves continuously across the engineering lifecycle.
- Curated context outperforms massive context.
- Good context benefits both humans and AI, for the same reasons.

## What Comes Next

Once you know how to build good context, the next step is organizing
*how* humans and AI collaborate around it, deliberately, throughout the
engineering lifecycle. That's **GUIDE-0006 — Human–AI Collaboration**.
