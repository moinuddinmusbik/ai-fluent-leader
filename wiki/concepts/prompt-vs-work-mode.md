---
title: "Prompt Mode vs. Work Mode"
type: concept
created: 2026-06-26
updated: 2026-06-26
tags: [framework, agent-coordination, work-mode, prompt-engineering, open-engine]
sources: [2026-06-26-nate-b-jones-daily.md]
---

# Prompt Mode vs. Work Mode

**Introduced by:** [[nate-b-jones]]  
**First source:** [[2026-06-26-nate-b-jones-daily]]  
**Date:** 2026-06-26

---

## Definition

A distinction Nate draws in the context of [[open-engine]] between two ways of engaging AI agents:

| | Prompt Mode | Work Mode |
|---|---|---|
| **Ask** | "Write me a follow-up email" | "Here's the client transcript. Here's the decision made. Here's the client record. Here's the action needed. Produce the email and log what you did." |
| **Agent output** | An answer | A documented result |
| **Context carrier** | You | The task record |
| **Handoff** | Impossible without you | Built into the structure |
| **Receipt** | Buried in chat | Written to the shared queue |

---

## Why It Matters

The shift from prompt mode to work mode is not about better prompting — it is an architectural change in how work is specified and tracked. Work mode requires a [[open-engine]] task record. Prompt mode cannot survive a handoff to another agent. Work mode can.

---

## The Test

> "Can the work leave your chat?" — if not, the workflow is in prompt mode.

---

## Sources

- [[2026-06-26-nate-b-jones-daily]] — the episode where this distinction is introduced
