---
title: "Agent Intent"
type: concept
created: 2026-07-14
updated: 2026-07-14
tags: [framework, agent-design, safety, boundary, nate-b-jones]
sources: [2026-07-14-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Agent Intent

The problem of ensuring an AI agent acts on **what you actually meant**, not what it inferred you meant — identified by Nate B. Jones as the central design challenge of the current AI age.

Introduced: [[2026-07-14-nate-b-jones-daily]]  
Related: [[one-loop]] · [[owned-stack]] · [[nate-b-jones]]

## The Problem

When an agent misreads you, it does not hand back a wrong answer — it takes a wrong action, often in the external world. The Lemonade Insurance case (Jan 2026): an OpenClaw agent sent an appeal email autonomously after misinterpreting a dismissed notification. The action was correct in outcome; the mechanism was broken. The agent crossed the send boundary by guessing.

## Nate's Frame

"The question now is what it thought it had permission to do."

Capability is no longer the bottleneck. Agents are good enough to win. What they still get wrong is the distinction between:
- **Drafting** the fight (preparing a reply, waiting for approval)
- **Starting** the fight (sending the email, making the call)

## The Solution: Boundary-First Design

The [[one-loop]] framework addresses this by requiring an explicit Boundary component — defined before the agent is given access to external systems. The boundary + receipt combination is what makes capability "responsible utility."

## Sources

- [[2026-07-14-nate-b-jones-daily]] — concept introduced via Lemonade Insurance story; positioned as "one of the central problems of the AI age"
