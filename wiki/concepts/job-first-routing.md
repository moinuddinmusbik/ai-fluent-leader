---
title: "Job-First Routing"
type: concept
created: "2026-07-02"
updated: "2026-07-02"
introduced_by: "[[nate-b-jones]]"
introduced_in: "[[2026-07-02-nate-b-jones-daily]]"
tags: [framework, model-routing, ai-strategy]
---

# Job-First Routing

A model-selection framework introduced by [[nate-b-jones]] on 2026-07-02. The core move: **define the job before picking the model**. The job's shape (familiar vs. novel, known-output vs. discovery) determines which intelligence tier is appropriate.

## The Three Tiers + Specialists

| Tier | When | Example models |
|------|------|----------------|
| **Daily Driver** | Pre-task-defined; messy, mixed, judgment-heavy work | Codex, Claude Code |
| **Cheap Workhorse** | Familiar shapes, repeatable, easy to review (center-of-distribution) | GLM 5.2, Z.AI |
| **Frontier Model** | Fable-style problems; unclear shape; novel domain; judgment load-bearing | Claude, ChatGPT 5.5/5.6 |
| **Specialists** | Job needs a specific sense or action | Flux/Zimage/Grok Image · LTX/Seed Dance/Grok Video · Grok (live web) |

## Key Principle

The harness (surrounding system of prompts, memory, routing, tool calls) is not separable from the model. A strong model with a weak harness (Gemini, per Nate) loses to a weaker model with a great harness. Build around a harness you control.

## Relation to Other Concepts

- Extends [[center-edge-distribution]] (introduced 2026-06-28) with a 4-tier explicit routing structure
- Pairs with [[ai-harness]] — harness portability is what makes routing resilient when a model disappears
- Describes the antidote to [[fable-style-problem]] escalation: default to Cheap Workhorse for familiar work, only escalate to Frontier when the job genuinely demands it

## Five Rules of the Road (Nate's)

1. Don't copy what someone else is doing (including Nate).
2. Ask how *hard* the work is, not just how *much* work you need done.
3. Know how to tell if the output is good — eval or sniff test.
4. Make model choice itself not be work.
5. Don't pick too many models.
