# ADR-0004: Human Governance of AI Contributions

- **Status:** Accepted
- **Date:** 2026-07-28
- **Deciders:** AAOE Maintainers

## Context

AAOE uses AI agents to accelerate research, organization, drafting, analysis,
and publishing preparation. These capabilities can increase throughput, but an
AI agent cannot hold project accountability or independently determine what is
official AAOE knowledge.

## Decision

AAOE adopts a human-governed contribution model.

AI agents may inspect material, identify patterns, propose classifications,
draft documents, and prepare repository changes. A human maintainer reviews
and approves decisions before they become accepted, merged, released, or
published as AAOE.

The governing workflow is:

```text
AI proposal → Human review → Approval → Merge → Publication
```

Human reviewers retain authority to amend, reject, defer, or request further
evidence for every AI-assisted proposal.

## Consequences

- AI assistance is transparent and accountable to human review.
- Accepted decisions and published material have an identifiable human
  approval path.
- Agents must distinguish proposals from approved content.
- Repository workflows should preserve review context and decision history.
- Human judgment remains responsible for scope, quality, ethics, and strategic
  direction.

## Scope

This decision defines governance for AI-assisted AAOE contributions. It does
not prohibit human-authored contributions or require a specific AI model,
tool, or hosting platform.
