---
title: "Agent Constitution"
type: concept
created: 2026-07-08
updated: 2026-07-08
tags: [multi-agent, prompting, agent-design, standards, big-work]
sources: [2026-07-08-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Agent Constitution

A prompting pattern introduced by [[nate-b-jones]] for large-scale AI work: define what "done right" means in a written standard — once, before any task starts — and let the orchestrating model enforce it on every round.

## The Pattern

> "You name what done right means for you one time at the top and the system enforces it on every single round while you do something else."

In the 2026-07-08 live build:
- Before a single page existed, the research phase produced a 14-point accessibility constitution for Elsa Hunison's website.
- Every build round was tested against it in a real browser, both light and dark themes, every route.
- Fable 5 produced this constitution from a 5-word prompt — then enforced it across all 34 tasks.

## Why It Beats Task-by-Task Prompting

Task-by-task prompting requires the human to re-inject quality standards on every turn. A constitution externalizes the standard into the system — the orchestrator becomes the enforcer, not the human. The "persona" model is especially powerful: naming a specific user whose experience must win (e.g., Maya, a blind reader on VoiceOver with a braille display) gives the orchestrator a concrete adjudicator for design conflicts.

## Sources

- [[2026-07-08-nate-b-jones-daily]] — introduced alongside [[verified-agent-swarm]] in $8 website build
