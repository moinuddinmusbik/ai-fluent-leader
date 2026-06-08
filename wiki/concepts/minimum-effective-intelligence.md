---
title: "Minimum Effective Intelligence"
type: concept
created: 2026-06-07
updated: 2026-06-07
abbreviation: MEI
source: "[[2026-06-07-nate-b-jones-daily]]"
tags: [ai-strategy, cost-management, routing, agentic-ai, framework]
---

# Minimum Effective Intelligence (MEI)

A **routing rule** for AI workloads introduced by [[nate-b-jones]] in his June 7, 2026 executive briefing on Uber's AI token cost crisis.

## Definition

Assign every AI workload to the **minimum intelligence tier** that meets the task's actual need:

- **Frontier model** — when the task genuinely requires cutting-edge reasoning, creativity, or multi-step agency
- **Open / smaller model** — when the task is well-specified and frontier capability is not needed
- **No model** — when the task should not involve AI at all

## Core Insight

Even as price-per-call falls on frontier models, agentic tasks (planning, retrying, running for hours) keep getting more expensive in absolute terms. Reflexively routing all work to frontier models inflates the token bill for work that does not require it. MEI is the front-load question: *does this genuinely need the most capable model?*

## Why It Matters

Nate frames MEI as "the fastest correctable item on any token bill." Unlike redesigning the full operating model (which takes quarters), applying MEI is a routing decision you can implement at the workflow level today. It also surfaces the distinction between tuition spend (exploratory, builds capability) and waste (over-specced models on routine tasks).

## Context of Origin

Introduced in response to Uber's May 2026 AI budget blowup — where 95% of engineers used AI monthly but the COO could not connect token spend to customer features. MEI is one component of the larger operating model redesign Nate argues companies like Uber need.

## Related

- [[2026-06-07-nate-b-jones-daily]] — source brief
- [[nate-b-jones]] — creator
