---
title: "Enforcement Ladder"
type: concept
created: 2026-07-12
updated: 2026-07-12
tags: [framework, agent-design, organizational-change]
sources: [2026-07-12-nate-b-jones-daily.md]
---

# Enforcement Ladder

A five-rung model introduced by Nate B. Jones for turning organizational rules into software-enforced behavior. Introduced in [[2026-07-12-nate-b-jones-daily]].

## Definition

The ladder determines how hard a rule is allowed to bite. Five rungs in ascending enforcement strength:

1. **Value** — a stated principle; no enforcement mechanism
2. **Instruction** — a written directive; agents can read it
3. **Reminder** — automated nudge (e.g., Slack message); still human-override
4. **Hard block** — automated rejection; requires explicit escalation
5. **Human-owned decision** — the judgment call that stays with a person

No rung six: there is always a human at the top who can override the system.

## Practical Implementation

Nate has built the Meeting Challenger as a working example: a calendar-scanning agent (instruction + reminder + deadline) that escalates to a human appeal (human-owned decision) — the machine asks the question, the person keeps the judgment.

## Key Insight

A rule that lives only in the head of your longest-tenured director does not exist as far as your agent stack is concerned. The enforcement ladder makes rules legible to agents by encoding them at the appropriate rung.

## Sources

- [[2026-07-12-nate-b-jones-daily]] — Introduced July 12, 2026
