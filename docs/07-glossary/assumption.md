# Assumption

## Definition

**Note:** "Assumption" is used consistently across AAOE documentation (Specifications, ADRs, Evidence Standard) but does not yet have a single canonical definition as a standalone term. This entry is a candidate for future refinement.

Provisionally: an assumption is something taken as true without direct verification, which a Specification or Architecture Decision Record should state explicitly so it can later be checked or revisited.

## Why It Matters

Hidden assumptions are one of the most common causes of poor engineering outcomes: they aren't wrong when a decision is made, but they can quietly stop being true later. Stating assumptions explicitly — in a Specification or an ADR — gives future engineers a chance to notice when one no longer holds.

## Related Concepts

- Specification
- Architecture Decision Record
- Evidence
- Trade-off

## References

- STD-0001 — Specification Lifecycle
- GV-0005 — Evidence Standard
- GUIDE-0001 — Thinking in Specifications
- GUIDE-0009 — Architecture Decision Records
