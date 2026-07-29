# Multi-Agent Engineering

## Guide Metadata

**Guide ID:** GUIDE-0007

**Domain:** Guides

---

## Why Multiple Agents?

No engineer is equally specialized in every discipline. You wouldn't
expect your best backend engineer to also be your strongest security
reviewer, your sharpest QA mind, and your most careful technical writer,
all at once. The same principle applies to AI.

Instead of one general-purpose AI attempting everything, organizations
benefit from multiple specialized collaborators, each doing the thing
they're best suited for:

- Architecture
- Backend
- Frontend
- Security
- QA
- Documentation
- Database
- DevOps

Specialization improves engineering quality — for AI collaborators for
the same reasons it does for human ones.

## Think in Roles, Not Models

AAOE organizes work around engineering roles, not AI products. Think in
terms of:

- Architecture Agent
- Backend Agent
- Testing Agent
- Documentation Agent
- Review Agent
- Security Agent

The role is what matters. The underlying implementation behind any given
role may change over time — that's fine, and shouldn't require rethinking
how the work itself is organized.

## Every Agent Needs Clear Responsibilities

Each agent should have:

- objectives
- responsibilities
- inputs
- outputs
- boundaries

Avoid overlapping ownership. When two roles could plausibly own the same
decision, that ambiguity doesn't resolve itself — it just shows up later
as a conflict, or worse, as something nobody actually owned. Specialization
only reduces ambiguity if the boundaries between roles are actually clear.

## Shared Context

Multiple agents should collaborate using the same engineering context:

- Specifications
- Standards
- ADRs
- Work Orders
- Architecture Reviews
- Implementation Reports

Context is what synchronizes the collaboration. Without shared context,
specialization stops being a strength and turns into fragmentation —
each agent working from a different, partial picture of the same system.

## Humans Orchestrate

Humans remain responsible for:

- defining objectives
- assigning work
- approving architecture
- resolving conflicts
- accepting trade-offs
- approving releases

AI agents execute specialized engineering work within that structure.
Adding more agents to the picture doesn't dilute human governance — if
anything, it makes clear human orchestration more important, not less.

## Collaboration Between Agents

Agents should review one another's work, not just hand off to the next
step blindly:

```text
Architecture Agent
        ↓
Backend Agent
        ↓
Security Agent
        ↓
QA Agent
        ↓
Documentation Agent
        ↓
Review Agent
```

Each agent contributes its expertise before the work ever reaches the
human reviewer — which means the human reviewer is looking at something
that's already been through several specialized passes, not a first
draft.

## Orchestration Is About Flow

Orchestration isn't simply routing tasks to the right agent. It's about
organizing:

- dependencies
- sequencing
- feedback
- review
- traceability

Good orchestration reduces unnecessary coordination overhead — it's the
difference between a team that trips over itself constantly checking in,
and one that knows exactly when and how work needs to change hands.

## Common Multi-Agent Mistakes

Watch for:

- overlapping responsibilities
- duplicated work
- isolated context
- agents making architectural decisions independently
- no human governance
- optimizing for automation instead of engineering quality

Each of these tends to look like progress in the short term — more agents
running, more work happening in parallel — while quietly eroding the
thing that made specialization valuable in the first place.

## Practical Exercise

Take an existing engineering project. Identify:

- required engineering roles
- which roles AI could perform
- which responsibilities remain human
- what shared context everyone needs

Reflect honestly on whether those responsibilities are actually clear and
traceable today, or whether they're implicit and would only surface as a
problem once something went wrong.

## Key Takeaways

- Specialization improves quality — for AI collaborators just as much as
  for human ones.
- Roles matter more than which AI product happens to fill them.
- Shared context is what enables specialized collaboration instead of
  fragmentation.
- Humans orchestrate engineering, regardless of how many agents are
  involved.
- AI agents execute specialized responsibilities within that structure.

## What Comes Next

Once multiple collaborators — human and AI — contribute to the same
engineering work, capturing what was implemented and why becomes
essential organizational knowledge. That's
**GUIDE-0008 — Implementation Reports**.
