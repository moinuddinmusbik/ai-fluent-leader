---
title: "One-Minute Agent Test"
type: concept
created: 2026-07-10
updated: 2026-07-10
tags: [framework, agents, dispatch, ai-strategy]
introduced_by: [[nate-b-jones]]
introduced_in: [[2026-07-10-nate-b-jones-daily]]
---

# One-Minute Agent Test

A dispatch framework by [[nate-b-jones]] for classifying any task into one of four verdicts — Chat, Single Agent, Team of Agents, or Don't Bother — using four estimates that take roughly one minute to run.

## The Four Estimates

1. **Size** — Is the task large enough to justify agent setup and run cost?
2. **Independence** — Can the task run without constant human input mid-execution?
3. **Separation** — Can the work be handed off cleanly, with the output evaluable independently from the doing? (Fails → verification wedge)
4. **Checkability** — Can the output be verified mechanically or by sampling? (Fails at scale → context ceiling)

## The Four Verdicts

| Verdict | Meaning |
|---------|---------|
| **Chat** | Small or judgment-heavy; use a conversational session |
| **Single Agent** | Large + independent; one agent can hold the full problem |
| **Team of Agents** | Exceeds context ceiling; requires verifiable handoffs between agents |
| **Don't Bother** | Perfectly agent-shaped but economics (build + run cost) don't justify it, or human judgment is the irreplaceable output |

## Key Insight

The "Don't Bother" verdict is the one the market never sells. A task can score well on the first three estimates and still fail on economics. The two structural limits — the **verification wedge** and the **context ceiling** — sort every multi-agent pitch you'll ever hear.

## Evidence

- Stanford: brute-forcing a cheap model from 15.9% to 56% by spending more tokens (not switching models)
- Anthropic: token spend explained 80% of performance variance between strong and weak agent runs
- 1.6M agents registered on OpenClaw and never dispatched — the failure mode the test is designed to prevent

## Related Concepts

- [[verification-wedge]] (implicit — the structural limit where separation fails)
- [[context-ceiling]] (implicit — the structural limit where checkability fails at scale)
- [[nate-b-jones]] — creator
- [[2026-07-10-nate-b-jones-daily]] — source episode
