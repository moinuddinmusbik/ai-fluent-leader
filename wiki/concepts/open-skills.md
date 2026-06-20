---
title: "Open Skills"
type: concept
created: 2026-06-19
updated: 2026-06-19
tags: [ai-strategy, framework, nate-b-jones, ai-agents]
sources: [2026-06-19-nate-b-jones-daily.md]
---

# Open Skills

A framework introduced by [[nate-b-jones]] arguing that agent skills — the procedures, standards, taste, and recovery judgment that used to live in a person's hands — are migrating into software, and should belong to the person or team that built them, not to whichever AI tool happened to host them.

## Definition

For most of human history a skill lived in a person: how to research, write, code, test, review work, and recover when something broke. AI is turning that into software — prompts, `SKILL.md` files, runbooks, scripts, MCP configs, permission boundaries, and agent workflows. Open Skills is Nate's claim that this newly-externalized procedural knowledge should be visible, movable, inspectable, testable, and available wherever you work — not rented back to you by whichever vendor's tool you happened to build it in.

## The Prompt / Memory / Skill Distinction

Nate separates three things people collapse into one:
- **Prompt** — a one-off instruction; copies over between tools but carries no durable structure.
- **Memory** — the context an agent has access to (the subject of his earlier [[open-brain]] framework).
- **Skill** — a portable, structured procedure (`SKILL.md`, runbook, etc.) that is the only one of the three that survives a model or tool change intact.

## Components

- `SKILL.md` files
- Runbooks (composed from multiple skills as primitives)
- Scripts
- MCP configs
- Permission boundaries
- Agent workflows
- A verification step that produces a checkable proof trail before output counts as "done"

## Why It Matters

Every tool switch becomes a rebuild, every new hire starts from scratch, and every improvement risks dying as one person's private habit when skills aren't portable. If agents are part of how you do your job, the skills you build with them are career capital — and right now most of that capital is rented back to you by whichever vendor's tool it happened to get built in.

## Related Concepts

- [[open-brain]] — the precursor framework (memory ownership); Open Skills is "the same fight, one level up, and more urgent."
- [[agent-harness]] / [[the-harness]] — Open Skills lives inside the harness layer; skills are the procedural component of it.

## Linked Pages

- [[nate-b-jones]] — introduced the framework
- [[2026-06-19-nate-b-jones-daily]] — introduction episode
