# Separation of Identity and Authorization

## Specification Metadata

**Specification ID:** STD-0007

**Domain:** Standards

**Version:** 1.0

**Status:** Draft

---

# Purpose

This Standard defines Separation of Identity and Authorization as the
preferred architectural approach for systems requiring controlled access.

Identity establishes who or what is requesting access. Authorization
determines what actions are permitted. These concerns should evolve
independently whenever practical.

---

# Standard

Engineering teams shall separate identity verification from authorization
decisions.

Identity mechanisms shall not embed authorization policies.

Authorization services shall operate independently of identity providers
whenever practical.

---

# Principles

This Standard shall:

- improve architectural separation of concerns
- reduce security coupling
- improve maintainability
- enable policy evolution
- improve auditability
- improve interoperability
- improve AI-agent authorization models

---

# Responsibilities

Identity is responsible for:

- Authentication
- Identity Proof
- Session Establishment
- Credential Validation

Authorization is responsible for:

- Permission Evaluation
- Policy Enforcement
- Role Evaluation
- Attribute Evaluation
- Resource Access Decisions

---

# Engineering Workflow

The preferred sequence is:

```text
Identity Verification
        ↓
Context Establishment
        ↓
Authorization Evaluation
        ↓
Policy Decision
        ↓
Resource Access
```

Identity should never directly determine permissions.

---

# Traceability

Security implementations should remain traceable to:

- Identity Specifications
- Authorization Specifications
- Security Policies
- Standards
- Discoveries

---

# Exceptions

Small systems may combine these responsibilities when complexity does not
justify separation.

Long-lived systems should separate identity from authorization.

---

# Relationship to Discoveries

This Standard operationalizes
[DISC-0007 — Authentication and Authorization Separation](../02-discoveries/0007-authentication-authorization-separation.md).

The Discovery explains why this architectural approach emerged. This
Standard defines how engineering teams apply it.

---

# Relationship to the Operating Model

The Operating Model applies this Standard through:

- Security Specifications
- Architecture Reviews
- Work Orders
- Implementation Reports

---

# Compliance

Engineering work conforms to this Standard when:

- Identity and authorization remain independent.
- Authorization policies evolve independently.
- Permission decisions remain traceable.
- Exceptions are explicitly documented.

---

# Future Evolution

Future Standards may define:

- Policy Decision Points
- Policy Enforcement Points
- Agent Identity
- Workload Identity
- Fine-Grained Authorization
- Zero Trust Authorization
