---
title: "Job-First Model Routing"
type: concept
created: 2026-07-28
updated: 2026-07-28
tags: [framework, model-selection, ai-strategy, routing, model-tiers]
sources: [2026-07-28-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Job-First Model Routing

A decision framework introduced by [[nate-b-jones]] (2026-07-28) for matching AI tasks to the right model tier by starting with the work, not the model name or benchmark ranking.

## Core Principle

Most people pick an AI model backward — they check the leaderboard, take the top name, and apply it to everything. The correct inversion: **describe what the task requires first, then choose the model tier.** Model selection follows job classification.

## The Four Tiers

| Tier | When to Use | Characteristic |
|------|-------------|----------------|
| **Daily Driver** (Breadth) | Complex, novel, undefined, high-stakes work | Must be strong across everything; you reach for it before the job scope is clean |
| **Cheap Workhorse** (Familiar/Repeatable) | Routine decks, memos, CRM cleanups, landing pages, familiar code patterns | The majority of professional work; Nate names GLM 5.2 as a named example |
| **Frontier** (Edge) | Genuinely novel reasoning, high-ambiguity synthesis, capabilities unavailable at lower tiers | Not the default; reserved strictly for tasks that cannot be done at lower cost |
| **Specialists** (Sensory/Action) | Vision, live-data retrieval, agent/action tasks | Routing shifts to harness design (which interface), not benchmark score |

## Key Routing Questions

1. Is this work **familiar and repeatable**? → Workhorse tier
2. Is this work **complex, ambiguous, or undefined**? → Daily Driver
3. Does this work **genuinely require frontier intelligence**? → Frontier
4. Does this work **need eyes, live data, or hands**? → Specialist harness

## Operationalization

Nate provides a **model-picker prompt** (available via Substack) — a copy-paste artifact that takes a task description and routes it to the correct tier: the deck, the repo, or the call.

## Strategic Context

The framework emerged from the structural lesson of the Fable 5 ~18-day outage (summer 2026): when your primary model can be throttled, repriced, or pulled behind a policy line overnight, routing discipline is the resilience strategy. Companies like Coinbase and Cursor already made this move at scale.

## Related Concepts

- [[ai-model-selection]]
- [[ai-cost-optimization]]

## Sources

- [[2026-07-28-nate-b-jones-daily]]
