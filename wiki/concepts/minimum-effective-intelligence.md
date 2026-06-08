---
title: "Minimum Effective Intelligence"
type: concept
created: 2026-06-07
updated: 2026-06-07
tags: [framework, ai-strategy, token-management, routing, operating-model]
sources: [2026-06-07-nate-b-jones-daily.md]
---

# Minimum Effective Intelligence (MEI)

A routing framework for AI workload assignment, named by Nate B. Jones in his June 2026 executive briefing on Uber's AI token budget blowup.

## Definition

Assign every AI workload to the **minimum intelligence tier** that actually satisfies the task's requirement. The three tiers:

| Tier | When to use |
|------|-------------|
| **Frontier model** | The task genuinely requires leading-edge reasoning, code generation, or nuanced judgment that only top-tier models deliver |
| **Open / smaller model** | The task is well-specified, repeatable, and does not need frontier capability — open models handle ~80% of enterprise tasks at a fraction of the cost |
| **No model** | The task is deterministic, rule-based, or lookup-style — AI adds latency and cost without adding value |

## Why it matters

The AI cost curve looks counterintuitive: per-call prices for frontier models keep dropping, yet the total spend for "work you actually want" from frontier models keeps rising. This is because the work that needs frontier capability is expanding faster than the per-call price falls. MEI is the routing rule that stops commodity tasks from consuming frontier-model budget.

## The broader argument

MEI is not a cost-cutting heuristic. It is a legibility tool: when workloads are routed correctly, spend becomes traceable to outcomes. The companies that cannot connect their token bill to customer value (cf. Uber 2026) are usually routing all work through the same intelligence tier — making the bill a single undifferentiated number rather than a readable signal.

## Sources

- [[2026-06-07-nate-b-jones-daily]] — Named and defined in the context of Uber's AI budget blowup analysis
