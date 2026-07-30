---
title: "Clean Desk Framework"
type: concept
created: 2026-07-29
updated: 2026-07-29
introduced_by: "[[nate-b-jones]]"
source: "[[2026-07-29-nate-b-jones-daily]]"
tags: [token-management, framework, ai-tools]
---

# Clean Desk Framework

A three-level mental model introduced by [[nate-b-jones]] for managing AI token limits by treating the AI workspace as a physical desk that must be actively kept clean.

## Core Premise

Every message sent to an LLM re-sends the full conversation history (reused input). By message 30, what you typed just now is "a tiny rounding error" in total token cost. The framework is built around actively reducing reused input at three levels of investment and automation.

## The Three Levels

**Level 1 — Clean Your Own Desk (9 manual habits):**
No installation required. Works on any AI. Key habits: edit-don't-retry, batch questions, start fresh tasks when jobs change, carry artifacts not arguments, request minimal output formats, excerpt files instead of sending whole documents, send text not PDFs, connect only needed tools, maintain an answers database.

**Level 2 — Token Saver Skill:**
One-command install into Claude Code or Codex. Automates the tedious parts of Level 1: search-before-open, excerpt-not-full-file, output length discipline, no pointless retries, model selection guidance. Available via Nate's Substack.

**Level 3 — Ringer:**
A local multi-agent intermediary that runs between the AI client and the model provider. Intercepts requests before the envelope is sealed, enabling: zero-call cached answer retrieval, fixed local recipe execution, passage selection, hard packet-size limits, and model routing. Integrates with OpenBrain or any answers database.

## Key Insight

The Token Saver Skill (Level 2) can only act once invoked — by which point conversation history and tool definitions are already in the request envelope. Ringer (Level 3) intercepts before that envelope is sealed.

## Related

- [[nate-b-jones]]
- [[2026-07-29-nate-b-jones-daily]]
- [[job-first-model-routing]] — adjacent framework from Nate covering model selection rather than token hygiene
