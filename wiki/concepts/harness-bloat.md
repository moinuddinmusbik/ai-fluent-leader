---
title: "Harness Bloat"
type: concept
created: 2026-07-15
updated: 2026-07-15
introduced_by: "[[nate-b-jones]]"
source: "[[2026-07-15-nate-b-jones-daily]]"
tags: [context-engineering, ai-strategy, harness, anti-pattern]
---

# Harness Bloat

**Phenomenon named by [[nate-b-jones]]** (2026-07-15): the gradual accumulation of AI harness instructions added one correction at a time, until the total setup becomes invisible to the user and starts degrading model delivery performance.

## Mechanism

Each added rule fixes a real problem. Over time, the sum of all those fixes becomes a system the user can no longer see or reason about. The model then spends cognitive capacity processing accumulated context rather than executing the actual task.

## Evidence

- Nate's own writing route loaded **18,384 words** before reaching the platform guide — no single rule caused this; each was individually justified
- Adding **~5,000 high-quality instruction words** to Fable 5 improved analysis scores but caused **delivery failure 2 of 3 runs**; compact brief passed all 3

## Counter-measure

Run the [[ai-harness-audit]] using the Six Rules framework.

## Related

- [[ai-harness-audit]]
- [[nate-b-jones]]
- [[2026-07-15-nate-b-jones-daily]]
