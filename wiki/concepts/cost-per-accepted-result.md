---
title: "Cost Per Accepted Result"
type: concept
created: 2026-07-27
updated: 2026-07-27
tags: [model-selection, evaluation, economics, nate-b-jones]
sources: [2026-07-27-nate-b-jones-daily.md]
---

# Cost Per Accepted Result

## Definition

The metric that replaces token price when evaluating AI model economics: what you actually pay to produce **one output that clears your quality bar**, factoring in token cost, review time, rejection rates, and rework.

Introduced by [[nate-b-jones]] in his 2026-07-27 episode "US AI Dominance Is Over: Here's Why" as the decisive counter-argument to naive token-price comparisons.

## Why It Matters

Token price and finished-work cost point in opposite directions. A model at one-fifth the price that:
- Requires double the review time
- Produces a 30% rejection rate on your quality check
- Generates rework cycles

...may be *more expensive* in total than a frontier model at 5× the token price.

## The Formula (conceptual)

> Cost per accepted result = (token cost + reviewer time cost + rework cost) ÷ (accepted outputs)

The model with the lowest cost per accepted result wins, regardless of per-token price.

## Context: Chinese Model Bakeoff

Nate introduced this metric specifically in the context of evaluating Chinese AI models (DeepSeek, Qwen, GLM, Kimi, MiniMax) against frontier models. His empirical evidence:
- The CAISI evaluation of DeepSeek V4 Pro showed cost-per-accepted-result diverging significantly from the token-price headline.
- His Ringer run (34-task job, ~$8 total) revealed GLM-5.2 fabricating 13 of 213 reported citations — a high rejection rate that dramatically changes the economics.

## Related Concepts

- [[model-fit]] — selection diagnostic using work patterns
- [[verified-agent-swarm]] — architecture that uses checking agents to enforce quality bar
- [[center-edge-distribution]] — center/edge task taxonomy relevant to where Chinese models earn their cost advantage

## Sources

- [[2026-07-27-nate-b-jones-daily]] — introduced 2026-07-27
