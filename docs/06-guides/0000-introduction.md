# Introduction

## Guide Metadata

**Guide ID:** GUIDE-0000

**Domain:** Guides

---

## Purpose

This Guide teaches you how to apply AI-Agent-Orchestrated Engineering
(AAOE) in day-to-day engineering work. Where the Standards tell you what
is required, this Guide walks you through how to actually do it: the
habits, the sequencing, the judgment calls you'll run into the first time
you try this for real.

Read it alongside the Standards, the Operating Model, Governance, and the
Reference Architectures. Those define the system. This Guide is about
practicing inside it.

---

## Why This Guide Exists

Something fundamental has shifted in how software gets built. AI has
changed software engineering, and not in a small way. Writing code is no
longer the bottleneck it used to be — a capable engineer working with a
capable AI agent can produce implementation faster than most teams can
review it. That sounds like good news, and mostly it is. But it moves the
hard part somewhere else.

The bottleneck now is organizing engineering work: deciding what should be
built, specifying it clearly enough that an AI agent (or a human) can
build it correctly, and reviewing what comes back with the same rigor you
always should have applied. Governance matters more, not less, as AI
capability increases — because AI amplifies whatever engineering
discipline is already in place. Good practices scale beautifully. So do
bad ones.

This Guide exists to help you build the discipline that AI amplification
rewards.

---

## Standards vs Guide

It's worth being explicit about the difference, because you'll bump into
both constantly.

Standards define the rules: principles, requirements, governance,
engineering constraints. They're normative — written to be complied with,
not just read.

The Guide explains the practice: workflows, techniques, recommended
approaches, worked examples, lessons other engineers learned the hard way
so you don't have to. It's instructional, not normative.

The Guide doesn't replace the Standards. It explains how to apply them
without getting lost.

---

## Intended Audience

This Guide is written for:

- Software Engineers
- Software Architects
- Technical Leads
- Engineering Managers
- AI Engineers
- Platform Engineers
- Organizations adopting AAOE

No prior knowledge of AAOE is assumed. If this is your first exposure to
any of it, you're in the right place.

---

## How to Read This Guide

The chapters build on each other, but each one is written to stand on its
own — if you already know how to write a Work Order, skip ahead. Here's
the order we'd recommend if you're starting from zero:

1. Introduction
2. Thinking in Specifications
3. Working with AI
4. Writing Work Orders
5. Architecture Reviews
6. Context Engineering
7. Human–AI Collaboration
8. Multi-Agent Engineering
9. Implementation Reports
10. Architecture Decision Records
11. Complete End-to-End Example

---

## Learning Philosophy

You won't learn AAOE by reading it once. You'll learn it by trying it,
watching where it breaks, and adjusting. That's true of most engineering
disciplines, and it's especially true here, because a lot of what makes
this work is judgment: how much to specify up front, when to trust an
agent's output, when to push back.

So: read, experiment, build, review, iterate. Mastery here comes from
repetition, not memorization.

---

## Relationship to the Repository

A quick map of how the Guide sits next to everything else:

- **Governance** defines how engineering knowledge is decided and evolves.
- **Standards** define the normative rules engineering work must follow.
- **Discoveries** capture the observations that eventually become
  Standards.
- **Operating Model** defines the lifecycle work moves through.
- **Reference Architectures** describe the systems that support all of
  this.
- **Case Studies** show AAOE applied to a real engineering initiative.

The Guide is the practical bridge across all of it — the place where
those domains turn into something you can actually do on a Tuesday
afternoon.

---

## What Comes Next

The next chapter, **GUIDE-0001 — Thinking in Specifications**, covers the
first real mindset shift AAOE asks of you: learning to think in
specifications before you think in implementation. It's a small change
that turns out to matter more than almost anything else in this Guide.
