# Complete End-to-End Example

## Guide Metadata

**Guide ID:** GUIDE-0010

**Domain:** Guides

---

## Introduction

You've now seen every major piece of AAOE on its own: thinking in
specifications, working with AI, writing Work Orders, running Architecture
Reviews, engineering context, human-AI collaboration, multi-agent work,
Implementation Reports, and ADRs. This chapter doesn't add anything new.
It walks through all of it together, in order, on one deliberately simple
feature: **password reset**.

The point isn't the feature. It's watching how the pieces connect.

## Step 1 — Discovery

Someone on the team notices users keep contacting support because they
can't get back into their accounts. That's the raw observation — nothing
more yet.

Before anyone writes a line of anything, a few questions get asked:

- Who are the affected stakeholders? Mostly end users, but also support,
  who's absorbing the ticket volume.
- What's the actual goal? Let users recover account access safely,
  without creating a new attack surface in the process.
- What questions are still open? How should identity be verified before a
  reset is allowed? How long should a reset link stay valid?
- What assumptions are we making? That users have a verified email or
  phone number on file, for instance.

This is Discovery. Nobody's designed anything yet — the team has simply
turned "people are annoyed" into a shared understanding of the actual
problem.

## Step 2 — Specification

That understanding turns into a Specification, the way
[GUIDE-0001](0001-thinking-in-specifications.md) describes. Instead of
someone opening an editor and starting to build, the team writes down:

- the objective — let a user regain account access through a verified
  channel
- the scope — password reset only, not the broader account-recovery flow
- constraints — reset tokens must expire, must be single-use, and reset
  requests must not reveal whether an email address exists in the system
- acceptance criteria — a user with verified access can set a new
  password; an expired or reused token is rejected; no user enumeration
  is possible through the flow

This is the point where engineering intent gets captured in a form that
both a human and an AI collaborator can act on without guessing.

## Step 3 — Architecture Review

Before implementation starts, the Specification goes through Architecture
Review, as covered in [GUIDE-0004](0004-architecture-reviews.md). The
conversation isn't "is this right or wrong" — it's exploratory:

- What alternatives exist for token delivery — email link, SMS code, both?
- What's the trade-off between reset-link expiry length and user
  convenience?
- What assumptions does "verified channel" depend on, and are they solid?

The team settles on an email-based reset link, short-lived, single-use.
That's not a big architectural leap, but it's now an explicit, reviewed
decision instead of something that quietly emerged during implementation.

## Step 4 — Work Orders

With the architecture validated, the work gets divided — following
[GUIDE-0003](0003-writing-good-work-orders.md) — into small, coherent
Work Orders instead of one large, vague one:

- **Authentication** — token generation, expiry, and single-use
  enforcement
- **API** — the reset request and reset confirmation endpoints
- **UI** — the reset request and new-password screens
- **Testing** — coverage for expired tokens, reused tokens, and the
  enumeration-safety requirement
- **Documentation** — user-facing help content and internal notes

Each Work Order has its own objective, scope, and validation criteria.
None of them require guessing what the others are doing, because they all
trace back to the same Specification.

## Step 5 — Multi-Agent Collaboration

Following [GUIDE-0007](0007-multi-agent-engineering.md), the Work Orders
get picked up by specialized collaborators:

- an **Architecture Agent** confirms the token and endpoint design matches
  the reviewed architecture
- a **Backend Agent** implements token generation and the API endpoints
- a **Frontend Agent** builds the reset request and new-password screens
- a **QA Agent** works through the expired/reused/enumeration test cases
- a **Documentation Agent** drafts the user-facing help content
- the **human engineer** coordinates across all of it, resolves the one
  ambiguous case that comes up around SMS as a future channel, and
  approves the result

Nobody's duplicating anyone else's work, because the Specification and
Work Orders already drew clear boundaries. The human isn't implementing —
they're orchestrating and making the calls only a human should make.

## Step 6 — Implementation

Implementation surfaces a few things nobody fully anticipated — that's
normal. The team discovers that the token storage approach they'd assumed
doesn't play well with an existing rate-limiting mechanism, so a small
adjustment gets made. None of this required rewriting the Specification;
it required engineering judgment applied within the boundaries the
Specification and Work Orders already set.

The result, eventually, is working software: a password reset flow that
does what Step 2 said it should do.

## Step 7 — Implementation Report

Before anyone moves on, an Implementation Report gets written — the same
day, per [GUIDE-0008](0008-implementation-reports.md), not weeks later.
It covers:

- what was actually completed
- the token-storage deviation from the original assumption, and why it
  happened
- what was discovered along the way — the interaction with rate-limiting
- a recommendation that SMS-based reset be considered as a follow-up
  Specification, not bolted onto this one

This is what keeps the reasoning from evaporating the moment attention
moves elsewhere.

## Step 8 — Architecture Decision Record

One decision from this work is significant enough to outlive the
Implementation Report: **password reset tokens expire after 15 minutes.**
That gets its own ADR, per [GUIDE-0009](0009-architecture-decision-records.md):

- **Problem** — reset tokens need an expiry window that balances security
  against user convenience.
- **Alternatives considered** — 5 minutes (too tight for realistic email
  delivery delays), 1 hour (too generous a window for a compromised
  inbox), 15 minutes (chosen).
- **Rationale** — 15 minutes comfortably covers normal email delivery
  while limiting the exposure window if an inbox is compromised.
- **Consequences** — users who don't act within 15 minutes must request a
  new link; this trade-off should be revisited if support data shows
  meaningful user friction.

Someone reading this ADR two years from now, with no memory of this
project, will understand exactly why 15 minutes and not 5 or 60.

## Step 9 — Context for Future Work

The Specification, the ADR, and the Implementation Report don't just
close this feature out — they become context for whatever comes next, as
[GUIDE-0005](0005-context-engineering.md) describes. The next team that
touches authentication will find the token-expiry ADR instead of
rediscovering the trade-off from scratch. The next Specification that
touches account recovery will reference this one instead of duplicating
its constraints. Engineering knowledge compounds, but only because each
step along the way actually wrote it down.

## Final Reflection

AAOE isn't a sequence of documents you produce to satisfy a process. It's
a continuous engineering learning system — one where each iteration
leaves the organization a little more capable than it was before,
because the reasoning behind the work doesn't disappear once the work is
done.

## Key Takeaways

```text
Discovery
        ↓
Specification
        ↓
Review
        ↓
Work Orders
        ↓
Multi-Agent Collaboration
        ↓
Implementation
        ↓
Implementation Report
        ↓
ADR
        ↓
Future Context
        ↓
Next Iteration
```

That loop is the whole Guide, in one picture. Every chapter before this
one taught you one link in that chain. This one showed you the chain.
