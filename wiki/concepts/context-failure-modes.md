---
title: "Context Failure Modes"
type: concept
introduced: 2026-07-24
creator: [[nate-herk]]
tags: [ai-os, context, hallucination, accuracy]
---

# Context Failure Modes

Framework introduced by [[nate-herk]] for diagnosing why an AI agent gives wrong answers. Four modes, each with a distinct root cause and fix.

## The Four Modes

| Mode | Root Cause | How It Feels | Fix |
|------|-----------|-------------|-----|
| **Poisoning** | False fact in the context | Agent confidently delivers wrong info | Verification: web search, DB cross-check, human-in-the-loop |
| **Bloat** | Too much data loaded | Agent bleeds in irrelevant material | Expertise/situational split; segment knowledge |
| **Confusion** | Missing or irrelevant facts | Classic hallucination — agent fills the gap | Add missing routing; remove irrelevant context |
| **Clash** | Conflicting data sources | Agent picks one randomly or makes something up | Freshness checks; timestamp policies; single source of truth |

## Two Context Types (Nate's Framework)

- **Expertise context** (always-loaded): identity, policies, goals — the principal who knows how classrooms run. Treat as the system prompt equivalent.
- **Situational context** (just-in-time): specific data needed for this particular request — the teacher who knows which students have bad vision. Load only when the situation arises.

## Related

- [[2026-07-24-nate-herk-daily]] — introduced in this video
- [[os-audit-skill]] — checks for all four modes
- [[nate-herk]]
