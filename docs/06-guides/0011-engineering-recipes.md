# Engineering Recipes

**Guide ID:** GUIDE-0011

**Work Item:** GUIDE-0001 (Engineering Recipes) — the Work Item that produced this
Guide used the identifier GUIDE-0001, which collides with the existing
[GUIDE-0001 — Thinking in Specifications](0001-thinking-in-specifications.md).
This document is registered as **GUIDE-0011**, the next available
identifier in the Guide Register.

---

## A note on status, read before anything else

This Guide describes a practical entry point into AAOE built around an
**Engineering Companion** — a conversational AI acting as a continuous
engineering collaborator across a project's early lifecycle. Guides in
this domain are instructional, not normative (GUIDE-0000), and are
allowed to be forward-looking in a way Standards are not. In that
spirit, this Guide is written as a usable, working recipe.

But it should not be read as evidence that "Engineering Companion" or
"Engineering Conversation" are accepted AAOE concepts. They are not,
today. The [WI-0002 Discovery Assessment](../../reports/2026-08-01-discovery-assessment-candidate-concepts.md)
evaluated both against AAOE's Evidence Standard (GV-0005) and Discovery
Acceptance Process (GV-0006) and found no documented Observation
supporting either — and found that the corpus's existing evidence
(ARCH-0002's stateless, no-inherited-context Agent boundary) points the
opposite direction from a "continuous companion." Where this Guide uses
those terms, it is describing an emerging practice pattern this
Architecture Team recommends trying, not a validated or Accepted body
of knowledge. Everywhere this Guide's flow diagram uses a term that
already has an accepted canonical definition (Work Order, Architecture
Review, Implementation Agent), that canonical term is used, not a
new synonym.

This distinction matters in practice, not just in principle: if this
recipe works well enough, in enough real projects, to become dated,
attributable Observations, that evidence is exactly what would let
Engineering Companion and Engineering Conversation graduate from
"recipe language" to an accepted Discovery — the same evidence-first
path every other concept in this corpus took.

---

# 1. Introduction

## What Engineering Recipes are

An Engineering Recipe is a reusable, self-contained conversation
starter: a prompt an engineer gives to a conversational AI to begin a
specific kind of engineering work the AAOE way, from the first message.
A Recipe is not a code sample and not a demonstration of prompt
engineering technique — it is a standardized onboarding artifact,
structured the same way every time, so that starting an AAOE project
feels the same regardless of which recipe an engineer picks or which
AI system they're using.

## Why they exist

Per the Information Architecture Assessment (IA-0001), a first-time
engineer's need is narrow and specific: understand AAOE, start a
project, deliver the first Work Order — not read the full Canonical
first. Recipes exist to serve that need directly. Rather than routing
a newcomer through Guides, Standards, and the Operating Model in
sequence before they write anything, a Recipe lets them start a real
conversation immediately, with AAOE's philosophy embedded in the first
message rather than explained in advance.

## Why AAOE recommends beginning with a recipe instead of reading documentation

Reading GUIDE-0000 through GUIDE-0010 first is a legitimate path — it
is the "First-Time Engineer" path IA-0001 already describes — but it
asks for narrative reading before any engineering happens. A recipe
inverts that: the AAOE mindset (specifications before code, human
governance, architecture before implementation) is carried inside the
first prompt itself, so an engineer learns the discipline by
practicing it in a real conversation about their real project, not by
reading about it first. This is a design goal this Guide is built
toward — a target for how fast a first conversation can start, not a
measured result, since no timed onboarding session has yet been
documented (see the Architecture Impact Assessment's Gap G5, and the
WI-0002 Discovery Assessment's finding that Developer Experience
remains unevidenced).

## How recipes relate to the Engineering Companion

A recipe's prompt instructs the AI the engineer is already using to
adopt the Engineering Companion pattern described above: propose,
question, draft, and structure — never approve, and never write
production code directly. The recipe is the *starting message*; the
Engineering Companion pattern is the *behavior* the recipe asks the AI
to sustain for the rest of the conversation.

---

# 2. Recipe Structure Standard

Every Engineering Recipe shall follow this structure. The candidate
fields considered were Metadata, Reference, Context, Project,
Responsibilities, Handoff, and Expected Outcome — all seven are kept,
with Responsibilities required to state an explicit boundary
(consistent with [STD-0013](../01-standards/0013-engineering-role-specification-standard.md)'s
rule that any role-like behavior description must state what it shall
never do, not only what it does):

1. **Metadata** — Recipe ID, Title, and the kind of engineering
   situation it addresses.
2. **Reference** — a pointer to the canonical source this recipe is
   derived from, so the AI grounds its behavior in AAOE rather than in
   a generic assistant persona.
3. **Context** — the fixed framing every recipe embeds: AAOE's
   philosophy and the Engineering Companion pattern, stated once so
   the engineer doesn't have to explain it.
4. **Project** — the variable the engineer supplies: what they are
   actually trying to build. Everything before this field is the same
   across every use of the recipe; this field is not.
5. **Responsibilities** — what the Companion does during this recipe,
   and, mandatorily, what it shall never do (approve architecture,
   write production code directly, or proceed past a Handoff without
   the human's review).
6. **Handoff** — the explicit condition under which this recipe's
   conversation is considered complete and ready to become a real
   engineering artifact (a Specification, a Work Order) — never
   left implicit.
7. **Expected Outcome** — what the engineer should have in hand at the
   end: not code, but engineering knowledge in a governable form.

---

# 3. Recipe 0001 — Start a New Software Project

**Metadata:** Recipe ID `RECIPE-0001`. Applies when an engineer is
beginning a new software project with no existing specification,
architecture, or codebase.

**Reference:** this recipe is derived from AAOE's Canonical
(`aaoe`/`aaoe-specifications`) and, once published, the canonical AAOE
website. As of this Guide's writing, the website does not yet exist —
its introduction remains Phase 3 of AAOE's Roadmap (ROADMAP.md) and is
explicitly deferred by ADR-0002 and ADR-0005 until its own lifecycle
warrants a dedicated repository. The reference below is written as the
canonical entry point this recipe is designed to point to; until the
website exists, treat it as a forward reference, not a live resource.

Complete prompt:

```
Reference:
https://aaoe.io

Use the AI-Agent-Orchestrated Engineering (AAOE) discipline as the
governing engineering methodology for this conversation.

Act as an AAOE Engineering Companion.

Your responsibility is to transform engineering conversations into
explicit engineering knowledge.

The objective is not to generate code.

The objective is to produce high-quality engineering artifacts that
can later be executed by specialized AI implementation agents.

Continue the recipe using AAOE philosophy:

You shall begin by understanding, not by building. Ask me what I am
trying to build, who it is for, and what constraints already exist —
budget, timeline, existing systems, team, and anything I already know
I need. Do not propose a technical design until you understand my
intent.

Once you understand my intent, help me turn it into a Specification:
objectives, constraints, assumptions, expected behavior, and
acceptance criteria — the same test a good Specification must pass in
AAOE: could two different engineers, or two different AI agents, read
it and produce compatible implementations?

You shall surface trade-offs and ask clarifying questions rather than
silently deciding for me. Where more than one reasonable approach
exists, name them and explain the trade-off; do not pick one without
telling me you did.

You shall not write production code in this conversation, and you
shall not treat any decision we reach here as final until I have
reviewed it. Everything you produce is a proposal for me to accept,
revise, or reject — architecture and specification authority stay with
me, not with you, for the whole of this conversation.

When we have a Specification I'm satisfied with, help me shape it into
a Work Order: a single, scoped objective, explicit constraints, what
"done" looks like, and a stop condition — ready to hand to an
implementation agent. Tell me clearly when you believe we've reached
that point; don't drift past it into implementation details yourself.

Engineering leads. Knowledge is the foundation. You participate. I
govern.
```

**Context:** everything above the `Project` line is fixed and reused
unchanged across every invocation of this recipe. It establishes AAOE
as the governing discipline and the Engineering Companion pattern as
the AI's behavior for the conversation, before any project-specific
detail is introduced.

**Project:** supplied by the engineer immediately after pasting the
prompt above — typically one or two sentences describing what they
want to build. The recipe deliberately does not script this part; it
is the one field that must vary.

**Responsibilities:** the Companion shall elicit intent before
proposing design; shall produce a Specification meeting the
two-engineers-or-two-agents test (GUIDE-0001, Thinking in
Specifications); shall surface trade-offs explicitly rather than
resolve them silently; and shall never write production code or treat
any output as final without the engineer's explicit review, per
[STD-0008 — Human-Governed Engineering](../01-standards/0008-human-governed-engineering.md)
and [ARCH-0002 — AI Agent Reference Architecture](../04-reference-architectures/0002-ai-agent-reference-architecture.md).

**Handoff:** this recipe's conversation is complete when the engineer
has a Specification they're satisfied with and a scoped Work Order
ready to hand to an implementation agent — not before. The Companion
should say so explicitly rather than let the conversation drift past
that point into implementation.

**Expected Outcome:** a Specification and a first Work Order, both
produced through conversation rather than written alone by the
engineer from a blank page — engineering knowledge in a form the rest
of AAOE's lifecycle (OM-0001) can already consume.

---

# 4. Future Recipes

The following are recommended as future recipes, not yet written.
Each would follow the same Recipe Structure Standard defined above,
adapted to its situation:

| ID | Title | Situation it would address |
|---|---|---|
| RECIPE-0002 | Modernize an Existing System | Beginning modernization of a legacy system with an existing codebase — the situation CS-0001 (SolOh) was itself drawn from. |
| RECIPE-0003 | Add a New Feature | Introducing a bounded feature into an existing, already-specified system. |
| RECIPE-0004 | Build an API | Starting from an API contract rather than a full application. |
| RECIPE-0005 | Mobile Application | Project-specific variations relevant to mobile platforms, within the same Engineering Companion pattern. |
| RECIPE-0006 | SaaS Product | Multi-tenant, subscription, and identity considerations from the outset (see STD-0007, Separation of Identity and Authorization). |
| RECIPE-0007 | AI Product | A project whose product surface itself involves AI behavior, distinct from AAOE's use of AI in building it. |
| RECIPE-0008 | Production Incident | Beginning from an incident rather than a greenfield project — evidence-gathering framed around GV-0005's inclusion of "operational incidents" and "postmortems" as valid evidence sources. |
| RECIPE-0009 | Architecture Review | Preparing for or conducting a Review (STD-0009, OM-0004) conversationally rather than starting a new project. |

None of these should be authored by copying Recipe 0001's prompt and
substituting a noun. Each situation has a different starting question
(a legacy system starts with "what exists and what constrains it,"
not "what are we trying to build") and should be drafted with that
difference in mind.

---

# 5. Usage Guidance

```
Conversational AI
        ↓
Engineering Companion pattern       (proposed practice — see status note above)
        ↓
Engineering Conversation            (informal; not yet a governed artifact)
        ↓
Architecture
        ↓
Specification
        ↓
Work Order                          (OM-0002 — canonical)
        ↓
Implementation handoff              (informally described here; not yet a
                                      distinct canonical artifact — see the
                                      Canonical Index Reference Architecture's
                                      discussion of a future "AI Execution
                                      Package")
        ↓
Implementation Agent                (ARCH-0002 — canonical)
```

The first three steps describe a practice this Guide recommends. The
last four are already-governed AAOE stages (OM-0001) that this practice
leads into — a recipe's job is to get an engineer from the top of this
diagram into the bottom, already-canonical half, as directly as
possible.

---

## Compliance with this Guide's constraints

- **Model-independent, technology-independent, implementation-independent:**
  no specific AI system, vendor, programming language, or framework is
  named anywhere in this Guide or its recipe.
- **References the canonical AAOE website:** Recipe 0001 references
  `https://aaoe.io` as instructed, with the status caveat above — the
  website does not yet exist, and this reference is forward-looking
  until it does.
- **Reinforces the governing invariant:** "Engineering leads. Knowledge
  is the foundation. AI participates. Humans govern." appears verbatim
  at the close of Recipe 0001's prompt, and is restated architecturally
  throughout this Guide's Responsibilities and status sections.
