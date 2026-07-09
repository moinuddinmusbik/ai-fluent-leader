---
title: "Verified Agent Swarm"
type: concept
created: 2026-07-08
updated: 2026-07-08
tags: [multi-agent, agent-design, hallucination, routing, verification]
sources: [2026-07-08-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Verified Agent Swarm

An architectural pattern for multi-agent AI systems introduced by [[nate-b-jones]] in the 2026-07-08 episode. The core move: replace the "trust the agent" question with a system design that makes trust unnecessary.

## Structure

- **Boss model** (frontier, e.g. Claude Fable 5): writes specs, designs the system, reviews work, rules on disputes. Never executes the deliverable.
- **Worker models** (cheap, e.g. GLM 5.2): execute all tasks from clear specs. Expected to hallucinate and cut corners.
- **Checking agents**: one per task. Re-execute the work independently (compile builds, re-fetch URLs, re-compare quotes character-by-character, run a real browser for accessibility). Do not read the worker's self-report. The worker can claim "done"; the checker decides.

## Key Principles

1. **No rank is exempt from verification.** The boss model (Fable 5) also hallucinated — caught by the checking agent and the boss's own review pass.
2. **Failures are investigated in both directions.** Checkers can be wrong too; workers can escalate to the boss, who can reverse a checker.
3. **The system does the watching, not the human.** 12 of 34 tasks were caught and reworked in Nate's live run with zero human involvement.
4. **Economics make this work now.** 10x+ price gap between frontier and commodity models (Fable 5 at $50/M vs. GLM 5.2 at pennies). Same job: $8 all-in vs. $85–$105 frontier-only.

## Companion Framework: Agent Constitution

Paired with the [[agent-constitution]] pattern: a written standard ("done right" definition) produced before any task starts, enforced by the orchestrator on every round. Fable 5 produced a 14-point accessibility constitution from a 5-word prompt. See [[2026-07-08-nate-b-jones-daily]].

## Sources

- [[2026-07-08-nate-b-jones-daily]] — introduced with live 34-task/$8 build of Elsa Hunison's website
