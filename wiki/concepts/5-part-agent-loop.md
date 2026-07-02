---
title: "5-Part Agent Loop"
type: concept
created: 2026-07-01
updated: 2026-07-01
tags: [ai-agents, framework, memory, intent, safety]
sources: [2026-07-01-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# 5-Part Agent Loop

**Introduced by:** [[nate-b-jones]], 2026-07-01
**Source:** [[2026-07-01-nate-b-jones-daily]]

## Definition

Nate B. Jones's framework for the smallest unit of [[responsible-utility]] — the minimum structure required for an agent to act for you without guessing. Five required components:

| Component | Role |
|-----------|------|
| **Memory** | What the agent knows about you — context, preferences, history. Stored in [[open-brain]]. |
| **Method** | How you want work done — runbooks, procedures, style. Stored in Open Skills. |
| **Boundary** | Where the agent stops. The explicit line between "draft for my review" and "execute." |
| **Receipt** | Proof of what the agent did: what action, on what data, under what authorization, at what time. Enables auditing and trust. |
| **Judgment** | The signal to stop and ask. Where the agent pauses for human approval rather than acting autonomously. |

Build all five or the loop can't be trusted. Missing the boundary means the agent guesses when to act (the Lemonade story). Missing the receipt means you can't audit. Missing judgment means the agent can't distinguish drafting from starting.

## Context

Introduced in the "Build Your Own AI Memory" episode (2026-07-01). Part of the [[open-stack]] architecture (Open Brain + Open Skills + [[open-engine]]). The 5-part loop is the *recurring job unit* that sits inside a larger loop-of-loops architecture.

## Related Concepts

- [[responsible-utility]]
- [[open-brain]]
- [[open-engine]]
- [[agent-ownership]]
- [[loop-of-loops]] (from 2026-06-24 episode)
