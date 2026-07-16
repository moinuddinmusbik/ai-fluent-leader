---
title: "AI Harness Audit"
type: concept
created: 2026-07-15
updated: 2026-07-15
introduced_by: "[[nate-b-jones]]"
source: "[[2026-07-15-nate-b-jones-daily]]"
tags: [framework, context-engineering, ai-strategy, harness]
---

# AI Harness Audit

A **framework introduced by [[nate-b-jones]]** (2026-07-15) for making the hidden instruction setup around an AI model visible, clean, and maintainable across model upgrades.

## Definition

The **harness** is everything you or your product can configure around a model: custom instructions, project files, saved prompts, memory, skills, tools, permissions, examples, and checks. It shapes every answer before you type your next prompt. It does *not* include model internals you can't inspect.

**Harness bloat** ([[harness-bloat]]) is the accumulation of instructions added one correction at a time until the system becomes invisible and starts dragging model performance.

## The Six Rules

1. **Map Before You Clean** — audit the full harness before removing anything
2. **Blame the Right Layer** — distinguish model failure from harness failure
3. **One Rule, One Home, One Owner** — each constraint in exactly one location
4. **Load It When You Need It** — compact base context; lazy-load specialist instructions
5. **Hard Rules Need Hard Checks** — critical constraints need enforcement, not just text
6. **Build for the Model and Product** — revisit harness after every significant model upgrade

## Tools

- Clean My AI Harness — Claude Edition (runnable skill for Claude projects)
- Clean My AI Harness — Codex Edition (runnable skill for Codex workspaces)

## Key Evidence

- 18,384 words loading in one writing route before the platform guide (Nate's own setup)
- 66 skill routes / 172 instruction files found in his audited Claude setup
- Compact brief outperformed enriched (+5,000 words) brief on delivery: 3/3 vs 1/3

## Related

- [[harness-bloat]]
- [[nate-b-jones]]
- [[2026-07-15-nate-b-jones-daily]]
