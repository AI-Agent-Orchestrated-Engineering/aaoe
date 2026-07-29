# AI-Agent-Orchestrated Engineering

**AAOE** is an engineering operating model for AI-first software development.
It treats AI agents as specialized contributors within a human-governed system
of knowledge, specifications, review, and delivery.

This repository is the canonical entry point for the AAOE ecosystem.

## Start Here

- Read the [founding decisions](docs/00-governance/decisions/README.md) that
  govern the repository and publishing model.
- Explore the [AAOE specifications repository](https://github.com/AI-Agent-Orchestrated-Engineering/aaoe-specifications),
  the canonical library for standards and specifications.

## How AAOE Works

AAOE follows a knowledge-first, human-governed workflow:

```text
Knowledge → Review → Approval → Publication
```

AI agents may research, organize, analyze, and propose. Human maintainers
review and approve what becomes official AAOE knowledge.

## Repository Map

```text
docs/
  00-governance/              Decisions, policies, and project direction
  01-standards/               Standard catalogue and links
  02-discoveries/             Engineering discoveries
  03-operating-model/         Roles, workflows, and lifecycle guidance
  04-reference-architectures/ Reusable architectural models
  05-case-studies/            Evidence from applied work
  06-guides/                  Adoption and contribution guidance
  07-glossary/                Shared terminology
  assets/                     Documentation assets

agents/                       Model-agnostic agent definitions
research/                     Material awaiting curation
archive/                      Historical and superseded material
```

The `aaoe-specifications` repository owns the canonical text of AAOE standards.
This repository provides the ecosystem context, governance, and navigation that
connect those standards to the wider operating model.

## Project Status

AAOE is being established in the open. The current focus is governance,
taxonomy, and curation of the existing body of work.
