# Contributing to AAOE

Thank you for contributing to AI-Agent-Orchestrated Engineering (AAOE).
AAOE is developed as an open, human-governed knowledge system. Contributions
may be human-authored, AI-assisted, or both; every contribution is subject to
human review before it becomes official.

## Core Principles

- Create or update knowledge in its canonical repository before publishing it
  elsewhere.
- Keep one change focused on one purpose.
- Preserve sources, rationale, and uncertainty; do not present a proposal as
  accepted AAOE knowledge.
- Do not delete, overwrite, or reclassify existing material without explicit
  maintainer approval.
- Respect the boundaries defined in the [ADRs](docs/00-governance/decisions/README.md).

## Choose the Right Repository

- Use `aaoe` for governance, operating-model guidance, discoveries, case
  studies, reference architectures, and ecosystem navigation.
- Use `aaoe-specifications` for the canonical text of AAOE standards and
  specifications.
- Do not duplicate standard text in `aaoe`; link to its canonical location.

## Contribution Workflow

1. Identify the canonical repository and destination for the proposed material.
2. Create a clearly scoped draft with its sources or rationale.
3. Mark unapproved decisions and emerging ideas as proposals.
4. Submit the change for maintainer review.
5. Address review feedback.
6. A human maintainer approves and merges the contribution.
7. Publish derivative materials only after the canonical content is approved.

## AI-Assisted Contributions

AI agents may research, organize, analyze, and draft content. They must:

- distinguish source material, inference, and recommendation;
- preserve human review points;
- avoid making irreversible changes without explicit approval; and
- identify files created or materially revised by the agent in the proposed
  change.

The human reviewer remains accountable for accepting, rejecting, or revising an
AI-assisted contribution.

## Content and Naming

- Write documentation in Markdown unless a format has a specific purpose.
- Use descriptive, lowercase, hyphen-separated filenames.
- Prefer links to canonical material over duplicated text.
- Keep related decision records, sources, and examples close to the content
  they support.

## Questions and Proposals

If the proper destination or status is unclear, open a discussion or submit a
proposal rather than treating an assumption as an accepted decision.
