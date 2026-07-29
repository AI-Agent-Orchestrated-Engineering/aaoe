# Shared Specification

## Definition

A Shared Specification is a Specification used as the canonical mechanism for coordinating multiple implementations — across teams, repositories, or specialized AI agents — instead of coordinating through shared implementation code. Implementations built against a Shared Specification may differ, but the Specification itself remains the consistent, authoritative reference.

## Why It Matters

During the SolOh ERP Modernization, specialized AI agents rarely depended on each other's implementation history; they coordinated through shared specifications instead. This scaled better than shared source code: it allowed independent, parallel implementation while preserving consistency, and it reduced the need for agents to inspect one another's work before proceeding.

## Related Concepts

- Specification
- Context Engineering
- Multi-Agent Engineering
- Traceability

## References

- STD-0004 — Shared Specifications
- DISC-0006 — Shared Specifications Over Shared Code
- CS-0001 — SolOh ERP Modernization
