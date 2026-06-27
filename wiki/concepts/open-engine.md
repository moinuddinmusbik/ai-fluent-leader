---
title: "Open Engine"
type: concept
created: 2026-06-26
updated: 2026-06-26
tags: [framework, multi-agent, agent-coordination, shared-queue, handoff-protocol]
sources: [2026-06-26-nate-b-jones-daily.md]
---

# Open Engine

**Introduced by:** [[nate-b-jones]]  
**First source:** [[2026-06-26-nate-b-jones-daily]]  
**Date:** 2026-06-26

---

## Definition

Open Engine is a coordination framework — and a practical build — for enabling AI agents from different tools (Claude, Codex, ChatGPT, local agents) to pass work to each other without a human acting as the integration layer. Its core artifact is a **shared task queue** that both humans and agents can read and write, combined with a **seven-part task record** that carries context, sources, limits, and receipts across agent boundaries.

---

## The Problem It Solves

When a job crosses multiple AI tools, someone has to carry the state: what was decided, what source mattered, what changed, what the next tool is allowed to do. Currently, that someone is the user. Open Engine replaces that person-as-hallway with a structured handoff protocol embedded in a shared record.

---

## Key Concepts

- **Shared queue:** Any system both humans and agents can access (Linear, Jira, Notion, a spreadsheet). Work lives here between agents, not in private chat windows.
- **Seven-part task record:** The structured artifact that travels with each piece of work across agent boundaries.
- **Prompt mode vs. work mode:** Prompt mode asks for an answer; work mode gives the agent a task record and asks for a documented result.
- **"Can the work leave your chat?" test:** The forcing function for whether a workflow needs Open Engine. If work cannot survive a handoff without human intervention, it is not in work mode.
- **Needs-input state:** When an agent hits ambiguity, it does not guess — it moves the task to a structured escalation state and surfaces the exact blocking question.

---

## Five Components (Build)

1. Setup skill — written instructions telling agents how to use the queue
2. Status skill — agents report task state (claimed, in-progress, needs-input, done)
3. Task schemas — seven-part structured records
4. Handoff protocol — rules for passing work with sources attached
5. Shared record — the queue itself

---

## Relationship to Other Concepts

- Successor / complement to [[open-brain]] (Nate's earlier memory framework)
- Addresses the [[bottleneck-migration]] pattern: the bottleneck has moved from execution to coordination
- Enables the transition from prompt mode to work mode (see [[prompt-vs-work-mode]])

---

## Sources

- [[2026-06-26-nate-b-jones-daily]] — the episode that introduced this framework
