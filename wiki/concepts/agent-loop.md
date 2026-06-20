---
title: "Agent Loop"
type: concept
created: 2026-06-19
updated: 2026-06-19
tags: [implementation, claude-code, agentic-ai]
sources: [2026-06-19-nate-herk-daily.md]
---

# Agent Loop

A reason -> act -> observe -> repeat cycle an AI agent runs against a task until a checkable "done" condition is met. Equivalent to the academic **ReAct** (Reason+Act) pattern, applied in practice inside agentic coding tools like [[claude-code]].

## Key aspects
- The verification step (the "done" check) matters more than the loop's architecture — a loop without a real check just iterates blind.
- Loops are about getting closer to the right output on the first try, not about brute-forcing perfection through repetition.
- Doesn't require running multiple parallel agents — a single well-verified loop on one task is a legitimate, accessible pattern, per [[nate-herk]]'s framing in his 2026-06-19 video.
- Example "done" checks: a numeric score (thumbnail scoring), a visual/functional render check (three.js build), a match-to-reference (Abbey Road recreation).

## Connections
- Related to [[agentic-ai]] and [[claude-code-skills]] (the "/loop" slash-command pattern referenced by viewers).
- Contrast with [[ai-agents-vs-workflows]] — deterministic workflows vs. probabilistic agent loops.

## Sources
- [[2026-06-19-nate-herk-daily]] — "Finally. Agent Loops Clearly Explained." (DEEP-DIVE)
