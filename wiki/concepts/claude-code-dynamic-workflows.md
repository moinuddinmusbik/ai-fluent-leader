---
title: "Claude Code Dynamic Workflows"
type: concept
created: 2026-05-30
updated: 2026-05-30
tags: [implementation, claude-code, agents, automation]
sources: [2026-05-30-nate-herk-daily.md]
routine: "Nate Herk Daily Implementation Playbook"
---

# Claude Code Dynamic Workflows

A Claude Code feature (introduced with Opus 4.8) enabling runtime-adaptive tool-use sequencing — Claude decides which tools to call and in what order based on what it observes during execution, without a pre-defined pipeline.

## Disambiguation

| Pattern | What it is | Use when |
|---------|-----------|----------|
| **Dynamic workflows** | Runtime tool chain Claude generates adaptively | Unpredictable execution path; Claude needs to observe before deciding |
| **Slash commands / skills** | Fixed sequences you pre-define | Known, repeatable process; speed and auditability matter |
| **Subagents** | Separate Claude instances with own context | Genuinely parallel workstreams |
| **/goal** | Open objective with static pre-written plan | Open-ended task; path unknown at start but plan is fixed once set |

## Practical Rules

- Use dynamic workflows for genuine novelty, not as a default.
- Constrain with a max tool-call budget to prevent over-iteration.
- For daily known-path processes, prefer slash commands — faster, predictable, auditable.

## Connections

- [[2026-05-30-nate-herk-daily]] — source
- [[ai-operating-system]] — dynamic workflows as a Capabilities layer
- [[nate-herk]] — creator
