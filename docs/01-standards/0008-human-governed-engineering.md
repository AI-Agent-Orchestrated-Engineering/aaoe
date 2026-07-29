# Human-Governed Engineering

## Specification Metadata

**Specification ID:** STD-0008

**Domain:** Standards

**Version:** 1.0

**Status:** Draft

---

# Purpose

This Standard defines Human-Governed Engineering as the governing
principle for all engineering activities involving artificial
intelligence.

Engineering decisions remain under human governance regardless of the
degree of AI assistance.

---

# Standard

Engineering teams shall ensure that governance of engineering work
remains a human responsibility.

AI systems may generate, analyze, review, or recommend engineering
artifacts.

Humans shall retain responsibility for engineering approval, architectural
decisions, governance, and accountability.

Authority may be delegated to AI for execution, but never for governance.

---

# Principles

Human-Governed Engineering shall:

- preserve human accountability
- maintain engineering governance
- improve engineering quality
- improve decision traceability
- encourage effective AI collaboration
- preserve organizational responsibility
- enable responsible engineering automation

---

# Responsibilities

Humans are responsible for:

- Engineering Governance
- Architecture Decisions
- Standard Approval
- Architecture Reviews
- Risk Acceptance
- Compliance Decisions
- Final Approval

AI systems may assist with:

- Specification Drafting
- Design Proposals
- Code Generation
- Documentation
- Testing
- Analysis
- Implementation Support

AI recommendations remain subject to human review.

---

# Engineering Workflow

The preferred engineering sequence is:

```text
Engineering Intent
        ↓
AI-Assisted Draft
        ↓
Human Review
        ↓
Architecture Review
        ↓
Approval
        ↓
Implementation
        ↓
Validation
```

Governance decisions shall require human approval.

---

# Traceability

Governed engineering should remain traceable to:

- Specifications
- Standards
- Architecture Reviews
- Implementation Reports
- Decision Records

Human approvals should remain auditable.

---

# Exceptions

Routine automation may execute previously approved engineering work.

Governance decisions shall not be fully delegated to autonomous systems.

Any exception shall be explicitly documented and approved.

---

# Relationship to ADR-0004

This Standard operationalizes
[ADR-0004 — Human Governance of AI Contributions](../00-governance/decisions/ADR-0004-human-governance-of-ai-contributions.md),
the accepted decision establishing that AI agents may propose, draft, and
prepare engineering work, while a human maintainer reviews and approves
decisions before they become accepted, merged, released, or published as
AAOE.

This Standard defines how engineering teams apply that principle in
day-to-day engineering work.

---

# Relationship to the Operating Model

The Operating Model applies this Standard through:

- Work Orders
- Architecture Reviews
- Implementation Reports
- Human Approval Gates
- Engineering Governance

---

# Compliance

Engineering work conforms to this Standard when:

- Human governance is preserved.
- Engineering decisions remain accountable.
- AI-generated artifacts are reviewable.
- Human approvals are documented.
- Governance decisions remain traceable.

---

# Future Evolution

Future Standards may define:

- Multi-Agent Governance
- Autonomous Engineering Boundaries
- AI Review Policies
- Engineering Approval Workflows
- Governance Metrics
- Agent Accountability Models
