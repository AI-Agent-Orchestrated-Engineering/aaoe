# Roles & Responsibilities

**Specification ID:** OM-0003

**Domain:** Operating Model

**Version:** 1.0

**Status:** Draft

**Last Updated:** 2026-07-28

## Purpose

AAOE defines explicit roles so that participation in the
[Engineering Lifecycle](0001-engineering-lifecycle.md) is traceable rather than
assumed. Explicit responsibilities, authority, and accountability let the
lifecycle scale to more contributors and more agents without losing
governance: anyone reviewing a Task can identify who was responsible for
each part of it and on what authority.

## Design Principles

- Roles represent responsibilities, not people.
- One person may perform multiple roles.
- One role may be performed by multiple people or agents.
- Responsibilities are explicit.
- Authority is explicit.
- Accountability is explicit.
- Human governance remains authoritative.

# Core Roles

## Human Architect

**Purpose**
Establishes and maintains architectural intent, and translates it into
scoped work.

**Responsibilities**
Defines architecture, approves the creation of Work Orders, and sets the
scope and constraints a Task must respect.

**Authority**
Approves architectural direction. No Work Order is created without a Human
Architect's approval.

**Inputs**
Approved canonical knowledge and prior architectural decisions.

**Outputs**
Work Orders.

**Lifecycle Participation**
Originates the Architecture stage and authors the Work Order stage.

## Implementation Agent

**Purpose**
Carries out an approved Work Order within its stated scope.

**Responsibilities**
Executes the Work Order, stays within its scope and constraints, and
produces an Implementation Report.

**Authority**
Acts only within the boundaries of an approved Work Order. Cannot approve
its own work or expand its own scope.

**Inputs**
An approved Work Order.

**Outputs**
Implementation output and an Implementation Report.

**Lifecycle Participation**
Executes the Implementation stage and produces the Implementation Report
stage.

## Human Reviewer

**Purpose**
Evaluates implementation output against architectural intent.

**Responsibilities**
Performs Architecture Review, and approves, rejects, or requests revision
of an Implementation Report.

**Authority**
Approves or declines a Task's result. No Task advances to Merge without a
Human Reviewer's approval.

**Inputs**
An Implementation Report and the architectural intent it responds to.

**Outputs**
An approval decision.

**Lifecycle Participation**
Performs the Architecture Review stage and the Approval stage.

## Release Manager

**Purpose**
Integrates approved work into the canonical release state.

**Responsibilities**
Merges approved Pull Requests into the release branch and maintains the
integrity of the release history.

**Authority**
Integrates only work that has already been approved. Cannot alter approved
content as a condition of merging.

**Inputs**
An approved Pull Request.

**Outputs**
A merged, canonical change.

**Lifecycle Participation**
Performs the Merge stage.

## Future Specialized Roles

As AAOE matures, specialized roles are expected to emerge within the
Implementation Agent responsibility, without changing the lifecycle itself.
Examples include:

- UX Agent
- Backend Agent
- Database Agent
- Frontend Agent
- Documentation Agent
- Security Agent
- Testing Agent
- DevOps Agent

These roles specialize *how* implementation is carried out. They do not
introduce new lifecycle stages, new approval authority, or exceptions to
the governance rules defined below.

## Role Interaction

```text
Human Architect
        │
        ▼
Work Order
        │
        ▼
Implementation Agent
        │
        ▼
Implementation Report
        │
        ▼
Human Reviewer
        │
        ▼
Release Manager
```

- The Human Architect hands off a Work Order once architecture is approved.
- The Implementation Agent hands off an Implementation Report once its
  Work Order is fulfilled.
- The Human Reviewer hands off an approval decision once the report has
  been evaluated against architectural intent.
- The Release Manager integrates the approved result, closing the Task and
  setting the starting point for the next Work Order.

## Governance

- Implementation Agents never approve their own work.
- Reviewers never redefine architecture.
- Release Managers integrate approved work but do not change it.
- Human Architects remain accountable for architectural intent.

## Future Evolution

Additional roles may be introduced as AAOE evolves. New roles are expected
to fit within the existing Engineering Lifecycle rather than change it.
