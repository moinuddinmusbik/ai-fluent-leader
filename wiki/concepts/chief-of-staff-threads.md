---
title: "Chief-of-Staff Threads"
type: concept
created: 2026-06-12
updated: 2026-06-12
tags: [framework, codex, agent, delegation]
sources: [2026-06-12-nate-b-jones-daily.md]
---

# Chief-of-Staff Threads

A thread pattern within the [[codex-operating-model]], named by [[nate-b-jones]] in the [[2026-06-12-nate-b-jones-daily]] episode. Chief-of-staff threads turn AI chat into delegated automation by giving each thread a specific finish line — a defined output to inspect and approve.

## What Makes It Distinct

- **Finish line, not conversation:** Each thread has a defined deliverable. The agent runs until the output exists; you review and approve or reject.
- **Delegation framing:** You are not prompting. You are assigning a job to a capable subordinate who returns the work with a receipt.
- **Encodes into Skills:** Recurring chief-of-staff threads are converted into Codex Skills — reusable procedures that run automatically and survive model upgrades.

## Contrast

- **Open-ended chat** = steering in real time, appropriate for uncertain problems (Claude Code territory per [[steer-or-dispatch]])
- **Chief-of-staff thread** = dispatching a defined assignment, appropriate when the job can be written down (Codex territory)

## Related Concepts

- [[codex-operating-model]] — the framework this pattern is component 3 of
- [[steer-or-dispatch]] — the interface-trains-behavior framing that contextualizes this pattern
- [[agent-literacy]] — managing the thread lifecycle (assign → receipt → approve/reject)
