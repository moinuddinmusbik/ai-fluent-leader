---
title: "Center / Edge of Distribution (Task Framework)"
type: concept
created: 2026-06-28
updated: 2026-06-28
tags: [ai-strategy, task-design, model-selection, framework]
introduced_by: "[[2026-06-28-nate-b-jones-daily]]"
---

# Center / Edge of Distribution

Nate B. Jones's framework for categorising AI tasks to determine which model tier is appropriate and whether open-source models can substitute for frontier models.

## The Split

| Tier | Definition | Characteristics | Best Model |
|------|-----------|-----------------|-----------|
| **Center of distribution** | Tasks the world has tried millions of times with AI; common patterns; familiar shapes | Brochure sites, standard decks, first-pass copy, routine synthesis, familiar coding problems; easy-to-inspect outputs; lots of training examples | GLM 5.2-class open-source (often *better* than Claude here) |
| **Edge of distribution** | Novel, high-stakes, context-dense, ambiguous tasks | Requires judgement, cross-domain reasoning, proprietary context, nuanced tone; outputs harder to inspect quickly | Frontier models (Claude, GPT-4o) still lead |

## Why It Matters

Most companies have never measured which tier their task load lives in. Without this analysis, they default to frontier pricing for everything — paying frontier costs for work that open-source handles better. Nate argues that measuring your center/edge split is the prerequisite for any serious model strategy in 2026.

## Nate's Quote

> "The nerdier phrase for this is that this is the middle of the distribution work for AI. In other words, what you are getting is what someone has tried with models millions of times before, where the answer pattern is pretty normal, and the output is pretty easy to inspect." — Nate B. Jones, 2026-06-28

## Related Concepts

- [[context-lock-in]] — even if you identify center tasks, lock-in may prevent switching
- [[ai-harness]] — center tasks still need a tuned harness for open-source models
- [[open-engine]] — model-agnostic task record to route across tiers

## Sources

- [[2026-06-28-nate-b-jones-daily]] — introduced; GLM 5.2 context
