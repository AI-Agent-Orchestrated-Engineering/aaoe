# ADR-0005: Canonical Repository Taxonomy

- **Status:** Accepted
- **Date:** 2026-07-28
- **Deciders:** AAOE Maintainers

## Context

The `aaoe` repository is the canonical entry point for the AAOE ecosystem.
Without a durable taxonomy, early content will accumulate by file type or by
when it was created, making navigation and later publication difficult.

The taxonomy must give each knowledge area a clear home without duplicating
the specifications owned by `aaoe-specifications`.

## Decision

The `aaoe` repository uses the following top-level taxonomy as knowledge areas
are added:

```text
docs/
  00-governance/              # ADRs, policies, and project direction
  01-standards/               # Standard catalogue and links; not standard source files
  02-discoveries/             # Validated and emerging engineering discoveries
  03-operating-model/         # AAOE roles, workflows, and lifecycle guidance
  04-reference-architectures/ # Reusable architectural patterns and models
  05-case-studies/            # Evidence from applied AAOE work
  06-guides/                  # Practical adoption and contribution guidance
  07-glossary/                # Shared terminology
  assets/                     # Documentation assets used by canonical content

agents/                       # Model-agnostic agent roles, workflows, and checklists
research/                     # Source research and material awaiting curation
archive/                      # Retained, superseded, or historical material
```

Repository-level files such as `README.md`, `CONTRIBUTING.md`, `ROADMAP.md`,
and `CHANGELOG.md` provide the project's public entry points and operational
guidance when introduced.

The `aaoe-specifications` repository remains the canonical home for AAOE
standard and specification source files. `docs/01-standards/` in `aaoe` may
contain an index, summaries, and links, but must not duplicate canonical
standard text.

Website source, reusable templates, and public examples remain outside this
taxonomy until their lifecycle justifies dedicated repositories under ADR-0002.

## Consequences

- Contributors classify material by its knowledge purpose, not file format.
- The repository retains a navigable structure as it grows.
- Standards have one canonical home and can be referenced without duplication.
- Incoming working material is first assessed in `research/` or through the
  curation workflow; it is not placed directly into a canonical area by default.
- New top-level areas require an explicit governance decision.

## Scope

This ADR defines the intended taxonomy. It does not create every listed folder,
move existing source material, or establish a website implementation.
