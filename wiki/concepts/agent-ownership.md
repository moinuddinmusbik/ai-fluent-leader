---
title: "Agent Ownership"
type: concept
created: 2026-06-21
updated: 2026-06-21
tags: [strategy, framework, agents]
sources: [2026-06-21-nate-b-jones-daily.md]
---

# Agent Ownership

Nate B. Jones's framework for the 2026 skill most teams skip: every AI agent that does real, depended-on work needs exactly **one named human owner** — not a committee, not "the AI team" by default.

## Definition

The fastest way to make an AI agent dangerous is to let everybody use it and nobody own it. The moment an agent starts reading real files, drafting real messages, and changing things other people rely on, it stops being a tool people use and becomes work someone is responsible for. Unowned agents don't fail loudly — they keep running on stale inputs while output keeps arriving and value quietly drains out (Nate's "haunted house" metaphor: a company full of automated systems still moving long after the reason for them disappeared).

## The one-sentence ownership test

The rule for exactly when an agent crosses from convenient to consequential, and therefore needs an owner: once it reads real files, drafts real messages, or changes things other people depend on. Whoever is closest enough to know whether the agent is helping, drifting, or just adding polished noise is the owner — never a default committee.

## Key aspects

- **Job, diet, boundaries, review loop** — the four fields that define an owned agent: what job it's doing, what inputs/data it consumes ("diet"), what it's not allowed to touch, and the cadence at which a human checks its work.
- **The Agent Owner's Card** — a one-page, human-readable artifact that makes an agent's ownership visible, positioned as the counterpart to the machine-readable "agent cards" agents already exchange with each other in multi-agent systems. Paired with a prompt you point an existing agent at to draft the fields it can see, handing the ownership questions back to a human to answer and review.
- **Ownership scales unevenly** — a personal agent (owner is obvious), a shared team agent (ownership diffuses fast), and a multi-agent pipeline (failures compound silently across handoffs) each break in a different way.
- **Not IT governance** — a governance committee can set rules for "the road"; it cannot substitute for one accountable person owning each individual agent doing the work.

## Named failure modes (receipts)

- A support agent that keeps answering from a policy that changed last quarter — wrong, but not loudly wrong.
- A planning agent that keeps turning noisy tickets into priorities that look clean and decisive but are quietly mis-ranked.

## Connections to other concepts

- [[agent-maintenance]] — Nate's prior (2026-06-17) framework on the seven parts of an agent harness that go stale; ownership is the accountability layer on top of maintenance ("maintenance is the 2026 skill").
- [[the-harness]] — the company-layer infrastructure (context, permissions, memory, standards, decision rights) that agent ownership sits inside of.
- [[agentic-ai]] — the broader category of autonomous systems this framework governs.

## Sources

- [[2026-06-21-nate-b-jones-daily]] — introduced 2026-06-21, FRAMEWORK lens
