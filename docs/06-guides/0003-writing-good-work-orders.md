# Writing Good Work Orders

## Guide Metadata

**Guide ID:** GUIDE-0003

**Domain:** Guides

---

## Why Work Orders Matter

A Work Order is not a project management ticket. It's easy to treat it
that way — a short line of text, an assignee, a due date — but that's not
what it's for in AAOE. A Work Order is an engineering contract: a
document that communicates intent clearly enough that whoever executes
it, human or AI, doesn't have to guess.

A good Work Order reduces ambiguity before implementation begins. Without
one, both humans and AI are forced to fill the gaps with assumptions —
and assumptions made silently are the ones that come back to bite you
later.

## Work Orders Organize Engineering

Here's where a Work Order sits in the bigger picture:

```text
Discovery
        ↓
Specification
        ↓
Architecture Review
        ↓
Work Order
        ↓
Implementation
        ↓
Implementation Report
```

Everything upstream of the Work Order is about deciding what should be
built and why. Everything downstream is about building it. The Work
Order is the bridge — it takes engineering intent that's already been
thought through and turns it into something executable.

## What Makes a Good Work Order?

A good Work Order has:

- a clear objective
- a defined scope
- explicit constraints
- measurable deliverables
- validation criteria
- references to supporting artifacts

If you can't answer "what exactly are we trying to accomplish?" after
reading it, it isn't ready yet — no matter how much text is on the page.

## Bad vs Good Examples

Here's a Work Order that looks like a task but isn't one yet:

```text
Implement authentication.
```

And here's the same intent, actually specified:

```text
Objective

Implement backend authentication for desktop users using the
shared authentication specification.

Scope

- Authentication only
- No authorization
- No MFA

Constraints

- Follow the Authentication Specification
- Follow the Separation of Identity and Authorization Standard

Deliverables

- Authentication endpoint
- Unit tests
- Documentation

Validation

Authentication scenarios pass.
```

The second version is dramatically easier to execute — not because it's
longer, but because every question an implementer would otherwise have to
guess at has already been answered.

## Think in Outcomes

Define outcomes, not tasks.

Weak:

```text
Write code.
```

Better:

```text
Enable secure desktop authentication according to the
shared authentication specification.
```

The first tells someone what to type. The second tells them what needs
to be true when they're done — which is the thing you actually care
about.

## Reference Existing Knowledge

A Work Order should rarely stand entirely on its own. Point to what
already exists:

- Specifications
- Standards
- ADRs
- Architecture Reviews
- Previous Implementation Reports

Good Work Orders connect knowledge instead of duplicating it. If a
constraint is already written down somewhere else, reference it — don't
re-explain it from scratch and risk the copy drifting out of sync with
the original.

## Keep Scope Small

Smaller Work Orders:

- reduce ambiguity
- simplify reviews
- improve AI collaboration
- increase traceability

One Work Order should accomplish one coherent engineering objective. If
you find yourself using "and" a lot while describing the objective,
that's usually a sign it should be two Work Orders.

## Common Mistakes

Patterns worth watching for:

- vague objectives
- oversized scope
- missing references
- hidden assumptions
- mixing architecture decisions with implementation
- no validation criteria

Each of these pushes a decision that should have been made explicitly
onto whoever executes the Work Order — and they'll make it implicitly,
which is exactly what you were trying to avoid.

## Practical Exercise

Take this Work Order:

```text
Improve reporting.
```

Rewrite it with:

- Objective
- Scope
- Constraints
- Deliverables
- Validation

As you fill each section in, notice what information was simply missing
from the original one-liner — and how much of it you had to invent from
nothing.

## Key Takeaways

- Work Orders communicate engineering intent, not just tasks.
- Small, focused Work Orders improve execution.
- Good references reduce duplication and drift.
- Validation criteria are what actually define "done."
- AI performs better when Work Orders are explicit.

## What Comes Next

Once implementation is complete, that work needs to be reviewed before it
becomes part of the organization's engineering knowledge. That's
**GUIDE-0004 — Architecture Reviews**.
