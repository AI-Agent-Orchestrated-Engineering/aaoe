# Engineering Role Specification Standard

## Specification Metadata

**Specification ID:** STD-0013

**Domain:** Standards

**Version:** 1.0

**Status:** Draft

**Work Item:** ERS-0001

---

# Purpose

This Standard defines how Engineering Role Specifications (ERS) are
authored.

An Engineering Role Specification documents a recurring engineering
role — human or AI — in behavioral, architecture-level terms:
what it is responsible for, what it is never permitted to do, what it
consumes and produces, and how its work is governed. It exists so that
every future role documented within AAOE (an Engineering Companion, a
Curator, an Architecture Reviewer, a Backend Engineer, and any role
after them) is defined the same way — structurally consistent,
technology-independent, and compatible with AAOE's existing governance
model — rather than each role being described in whatever shape its
author happened to choose.

This Standard does not define any specific engineering role. It
defines the template and normative structure every Engineering Role
Specification must follow.

---

# Standard

Every Engineering Role Specification shall conform to the structure,
normative language, and conformance model defined by this Standard.

An Engineering Role Specification describes a role. It does not itself
grant that role architectural authority, approval authority, or
Accepted status — a role's specification being well-formed under this
Standard is a necessary, not sufficient, condition for that role to be
recognized within AAOE (see Governance, below).

---

# Scope

## What an ERS Defines

- The role's mission and engineering stance, stated testably.
- What the role is responsible for.
- What the role explicitly must never do — its governance boundary.
- What the role consumes (Inputs) and produces (Outputs).
- The behavioral rules that apply to the role regardless of who or
  what fills it.
- Where the role's work sits in the Engineering Lifecycle (OM-0001).
- How the role's output is judged complete and ready to hand off.
- How the role's conformance is evaluated.

## What an ERS Does NOT Define

- Prompts, model selection, or any specific AI system. An ERS
  describes a role; it is filled by whatever human or AI a project
  chooses, consistent with the System Boundary Vision's principle that
  AAOE governs roles, not the actors who occupy them.
- Implementation details, technology choices, or tooling.
- Whether the role it describes is currently evidenced, validated, or
  accepted. That determination belongs to Governance (GV-0005, GV-0006,
  GV-0007), not to this Standard or to the ERS document itself.
- Authority for the role to approve architecture, specifications, or
  releases. No Engineering Role Specification may grant an AI-filled
  role approval authority; ARCH-0002's boundary applies to every ERS
  without exception.

---

# Document Structure

An Engineering Role Specification shall contain the following
sections, in this order. The list of candidate sections considered for
this Standard included Introduction, Philosophy, Mission,
Responsibilities, Non-Responsibilities, Inputs, Outputs, Behavioral
Principles, Engineering Workflow, Human Governance, Handoff Criteria,
Quality Attributes, Conformance, and Future Evolution. Two adjustments
were made deliberately, not by default:

- **Philosophy was folded into Mission.** Kept separate, Philosophy and
  Mission tend to restate the same "why does this role exist" content
  twice, inviting aspirational prose that duplicates rather than
  clarifies. Mission now states both purpose and engineering stance,
  in testable terms.
- **Quality Attributes is scoped to behavioral and output qualities
  only** (traceability, reproducibility, consistency of judgment) —
  never performance, scalability, or technology qualities, which would
  violate this Standard's technology-independence requirement.

The resulting required sections:

1. **Specification Metadata** — Identifier, Domain, Version, Status,
   consistent with every other governed AAOE artifact.
2. **Introduction** — one paragraph situating the role within AAOE's
   engineering lifecycle.
3. **Mission** — the role's purpose and engineering stance, stated
   testably (a reader should be able to say whether a given action is
   or is not consistent with the stated mission).
4. **Responsibilities** — what the role does.
5. **Non-Responsibilities** — what the role shall never do, stated
   using SHALL NOT (see Normative Language). This section shall
   precede any ambiguity about approval or architectural authority.
6. **Inputs** — what context, artifacts, or authority the role
   receives before it can act.
7. **Outputs** — what artifacts or decisions the role produces.
8. **Behavioral Principles** — the rules that govern how the role
   behaves, independent of who or what fills it.
9. **Engineering Workflow** — where this role's activity sits in the
   Engineering Lifecycle (OM-0001).
10. **Human Governance** — a mandatory, non-optional restatement of
    STD-0008's invariant as it applies specifically to this role: what
    a human must approve before this role's output has effect.
11. **Handoff Criteria** — when this role's work is complete and ready
    to pass to the next stage or role.
12. **Quality Attributes** — the behavioral and output qualities this
    role's work must exhibit (e.g., traceability, reproducibility),
    never technology or performance qualities.
13. **Conformance** — how this specific role's conformance is
    evaluated, consistent with the Conformance Model below.
14. **Future Evolution** — anticipated extensions to this role's
    specification.

No Engineering Role Specification shall omit Non-Responsibilities or
Human Governance. These two sections carry AAOE's core governance
invariant and are the two sections every other AAOE reference document
(ARCH-0002, STD-0008) treats as non-negotiable.

---

# Normative Language

Every Engineering Role Specification shall use the following terms
with these specific meanings. This adapts the normative-language
convention already used informally throughout existing Standards
(e.g., STD-0011, STD-0012) into an explicit, consistent rule for every
future ERS.

- **SHALL** — an absolute requirement. Absence of the described
  behavior means the role is not conformant.
- **SHALL NOT** — an absolute prohibition. Reserved specifically for
  governance and authority boundaries (approval, architectural
  authority, scope expansion). Every Non-Responsibilities section
  shall use SHALL NOT exclusively — never SHOULD NOT — because a
  governance boundary that is merely discouraged rather than
  prohibited is not a boundary.
- **SHOULD** — a strong recommendation. Deviation is permitted but
  should be documented and justified.
- **SHOULD NOT** — a strong discouragement, distinct from SHALL NOT.
  Used for practice guidance, never for governance or authority
  boundaries.
- **MAY** — optional latitude. Used for implementation choices,
  technology choices, or optional elaboration that does not affect
  conformance.

---

# Writing Principles

Every Engineering Role Specification shall be:

- **Behavior-focused** — describing what the role does and does not
  do, not how it is implemented.
- **Technology-independent** — test: could every sentence be read
  correctly with any AI model, tool, or vendor name substituted, or
  removed entirely, without changing its meaning? If not, it is not
  technology-independent.
- **Model-independent** — the specification shall hold regardless of
  which specific AI system, if any, fills the role.
- **Implementation-independent** — no programming language, framework,
  storage mechanism, or API is named.
- **Concise** — a Behavioral Principle that takes a paragraph to state
  usually contains more than one principle.
- **Testable** — test: given a description of an action taken by
  something filling this role, can a reader determine, from the ERS
  alone, whether that action was consistent with the role? If not, the
  relevant section needs to be more specific.
- **Architecture-oriented** — describing the role's place in AAOE's
  governance and lifecycle, not its day-to-day operating instructions.

---

# Conformance Model

Conformance to an Engineering Role Specification has two distinct
tiers, and they shall not be conflated:

- **Structural Conformance** — the ERS *document itself* follows the
  Document Structure and Normative Language rules defined by this
  Standard. This is evaluated the same way any Standard's Required
  Contents are evaluated, through Architecture Review.
- **Behavioral Conformance** — a *specific instance* filling that role
  (a human, an AI agent, a team) behaves consistent with the ERS's
  Responsibilities, Non-Responsibilities, and Behavioral Principles.
  This is evaluated the same way any other engineering work is
  evaluated — through Implementation Reports and Architecture Review
  observing actual behavior — never asserted from the ERS document
  alone.

An ERS document can be structurally conformant while no instance of
that role has yet demonstrated behavioral conformance. The two are
independent, and a role is not "proven" simply because its
specification is well-written.

---

# Engineering Workflow

```text
Role Need Identified
        ↓
Draft Engineering Role Specification Authored
        ↓
Architecture Review (Structural Conformance to this Standard)
        ↓
Accepted Engineering Role Specification
        ↓
Instance Fills the Role (human or AI)
        ↓
Behavior Observed (Implementation Reports, Architecture Reviews)
        ↓
Behavioral Conformance Evaluated
```

Acceptance of the specification and evidence of the role performing as
specified are separate gates. Neither substitutes for the other.

---

# Traceability

Every Engineering Role Specification should reference:

- The Discovery, Standard, or ADR that justifies the role's existence,
  where one exists — the same expectation every other Standard in this
  domain already carries (e.g., STD-0002 traces to DISC-0002).
- Related Engineering Role Specifications, where responsibilities
  border one another.
- Related Reference Architectures — in particular ARCH-0002 (AI Agent
  Reference Architecture) for any role that may be filled by an AI.

A role documented as an ERS without a traceable justification is not
thereby invalid, but it should be treated as a proposal awaiting
evidence, not as settled practice — the same standard this domain
already applies to every other Specification (GV-0005, GV-0006).

---

# Relationship to Human-Governed Engineering

Every Engineering Role Specification's Human Governance section shall
be consistent with [STD-0008 — Human-Governed Engineering](0008-human-governed-engineering.md):
authority may be delegated to a role for execution, but never for
governance. No Engineering Role Specification may state or imply that
an AI-filled role holds architecture, specification, or release
approval authority.

# Relationship to AI-Assisted Engineering and the AI Agent Reference Architecture

Where an Engineering Role Specification describes a role that may be
filled by an AI, it shall remain consistent with
[STD-0011 — AI-Assisted Engineering](0011-ai-assisted-engineering.md)
and [ARCH-0002 — AI Agent Reference Architecture](../04-reference-architectures/0002-ai-agent-reference-architecture.md):
the role may produce, draft, and propose; it may not approve.

---

# Governance

- **Versioning** follows the same semantic model as every other
  Specification (GV-0008): a Major version change alters a
  Non-Responsibility or governance boundary; a Minor version adds
  compatible guidance; a Patch clarifies without changing meaning.
- **Status lifecycle** for Engineering Role Specifications follows the
  Standards register's existing convention: Draft → Accepted →
  Revised → Superseded → Archived.
- **Breaking changes** — any change that narrows or removes a
  Non-Responsibility, or that would grant a role new authority — shall
  be treated as a Major version change and shall require Architecture
  Review before taking effect, regardless of how the change is framed.
- **Deprecated behaviors** are marked Superseded or Archived, never
  deleted, consistent with GV-0000's history-preservation principle.
- **An ERS document's existence, and even its acceptance under this
  Standard, is not itself evidence that the role it describes should
  exist.** Each Engineering Role Specification's underlying role must
  independently satisfy AAOE's evidence and Discovery Acceptance
  requirements (GV-0005, GV-0006) before it is treated as validated
  engineering practice rather than a proposal. This matters concretely
  today: ERS-1000 (Engineering Companion), named as a future
  Engineering Role Specification in this Work Item's context, was
  separately evaluated in the WI-0002 Discovery Assessment and found
  not yet sufficiently evidenced to proceed past proposal status. This
  Standard makes it possible to author ERS-1000 in a structurally
  conformant way whenever the Architecture Team chooses to; it does
  not make ERS-1000 accepted practice, and authoring it under this
  Standard does not change that assessment.

---

# Compliance

An Engineering Role Specification conforms to this Standard when:

- All required sections in Document Structure are present, in order.
- Non-Responsibilities and Human Governance are both present and use
  SHALL / SHALL NOT language exclusively for governance boundaries.
- No sentence names a specific AI model, vendor, or implementation
  technology.
- Every Behavioral Principle is testable per the heuristic in Writing
  Principles.
- The document does not assert its own acceptance, evidentiary status,
  or approval authority — those remain external, governed
  determinations.

---

# Recommendations

- Write Non-Responsibilities before Responsibilities. Defining the
  boundary first keeps the Responsibilities section from drifting into
  authority the role does not have.
- Do not author a full Engineering Role Specification for a role whose
  existence has not yet cleared AAOE's evidence bar (GV-0005, GV-0006).
  A short proposal referencing the relevant Discovery Assessment is
  more honest than a fully-structured specification that implies
  settled practice.
- Reuse existing Glossary terms rather than introducing new
  near-synonyms; where a role's terminology is genuinely new, resolve
  it through the Glossary's existing candidate-term process rather
  than asserting a definition inside the ERS itself.
- Cite the specific Discovery, Standard, or ADR that justifies a role's
  existence, the same way STD-0002 through STD-0007 each cite an
  originating Discovery.
- Treat a well-formed ERS document as a necessary but not sufficient
  condition for a role's acceptance — Behavioral Conformance evidence
  is what ultimately justifies moving a role from Draft to Accepted.

---

# Future Evolution

- **Repository location for ERS instances.** This Standard places
  itself within the existing Standards domain (`01-standards/`),
  consistent with current practice for artifact-template Standards
  (STD-0010, STD-0012). Individual Engineering Role Specifications
  (ERS-1000 and beyond) were described in this Work Item's context
  using a distinct ERS-numbered identifier family, separate from
  STD-numbering. Whether that family warrants its own top-level
  Canonical domain (a candidate `08-engineering-roles/`) is a
  legitimate future question — but per
  [ADR-0005](../00-governance/decisions/ADR-0005-canonical-repository-taxonomy.md),
  "new top-level areas require an explicit governance decision." No
  such decision has yet been made, so this Standard recommends it as
  future work rather than creating that domain now.
- **A related, already-flagged inconsistency.** ADR-0005 also states
  that `01-standards/` should contain only "an index, summaries, and
  links," with canonical standard text owned by `aaoe-specifications`.
  In current practice, STD-0001 through STD-0012 — and now this
  Standard — contain full text directly in this repository. This is
  the same repository-boundary ambiguity flagged in the Information
  Architecture Assessment and the Canonical Index Reference
  Architecture; this Standard follows actual current practice rather
  than ADR-0005's stated-but-unexecuted intent, and notes the
  discrepancy rather than silently deepening it.
- May define: Automated Structural Conformance Checking, Cross-Role
  Dependency Mapping, Role Composition (where one role's Outputs are
  another's Inputs), Role Retirement Criteria.
