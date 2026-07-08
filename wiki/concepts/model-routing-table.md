---
title: "Model Routing Table"
type: concept
created: 2026-07-07
updated: 2026-07-07
tags: [model-routing, claude-code, orchestration, cost-optimization, dynamic-workflows]
sources: [[2026-07-07-nate-herk-daily]]
---

# Model Routing Table

A structured table given to an AI orchestrator that maps each available model to its cost score, intelligence rating, and taste/creativity rating — enabling automatic delegation to the cheapest capable model for any task. Introduced by [[nate-herk]] on 2026-07-07.

## Structure

| Model    | Cost Score | Intelligence | Taste |
|----------|-----------|--------------|-------|
| Fable 5  |     2     |      10      |  10   |
| Opus 4.8 |     4     |       9      |   8   |
| Sonnet   |     7     |       7      |   7   |
| Haiku    |     9     |       5      |   5   |

*Cost Score: higher = cheaper. Ratings are subjective — customize to your workflow and usage patterns.*

## How to Use It

Paste the table into `CLAUDE.md` or an orchestrator skill file. The orchestrator model reads it when designing dynamic workflows and assigns Haiku/Sonnet for simple recon/execution tasks and Opus/Fable only for planning, judgment, and verification.

## Benchmark Result

Nate ran an Opus orchestrator with Haiku scouts vs. all-Opus dynamic workflows: same output quality, ~3× cost reduction on the Haiku-heavy configuration.

## Why It Matters

As AI budgets tighten and teams scale, model routing determines the unit economics of AI workflows. "That is going to be a very important skill to master as we head into the next years of AI." (Nate Herk, 1:40)

## Related
- [[fable-mode-skill]]
- [[2026-07-07-nate-herk-daily]]
- [[cheap-engine-frontier-steering]]
- [[nate-herk]]
