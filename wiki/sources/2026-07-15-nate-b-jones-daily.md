---
title: "Nate B Jones Daily — 2026-07-15"
date: 2026-07-15
type: source
creator: "[[nate-b-jones]]"
lens: FRAMEWORK
video: "https://www.youtube.com/watch?v=PDJfciNhyHU"
duration: "15:51"
substack: "https://natesnewsletter.substack.com/p/ai-harness-audit"
transcript_available: false
tags: [ai-strategy, harness, context-engineering, framework]
---

# Nate B Jones Daily — 2026-07-15

**[[nate-b-jones]]** · FRAMEWORK lens · 15:51 · 2026-07-15

Video: [Every Prompt You Send Drags 18,384 Words Of Junk. Here's How I Cut It.](https://www.youtube.com/watch?v=PDJfciNhyHU)  
Substack: [AI Harness Audit](https://natesnewsletter.substack.com/p/ai-harness-audit) (preview; full post paid)  
Transcript: unavailable (caption API blocked; brief grounded on Substack preview + video description)

---

## The Big Idea

Nate's AI setup was loading 18,384 words in one writing route before reaching the platform guide he actually needed — accumulated one correction at a time over months. His thesis: the model gets smarter with each upgrade, but the harness doesn't, creating invisible drag that makes your upgraded AI feel *worse* than a fresh chat. The fix is a systematic [[ai-harness-audit]] — make the hidden setup visible, then apply six rules to keep it clean for the next model generation.

## The Framework: [[ai-harness-audit]]

A **harness** = custom instructions + project files + saved prompts + memory + skills + tools + permissions + examples + checks. Everything you can configure around the model. Excludes hidden model internals you can't inspect.

Nate released two runnable skills:
- **Clean My AI Harness — Claude Edition** (maps Claude project setup)
- **Clean My AI Harness — Codex Edition** (maps Codex workspace)

Each produces a visibility report and cleanup plan; user approves changes before anything moves.

## How It Works: The Six Rules

- **Rule 1 — Map Before You Clean:** Audit first; 66 skill routes and 172 instruction files found in his own setup.
- **Rule 2 — Blame the Right Layer:** Distinguish model failure from harness failure before acting.
- **Rule 3 — One Rule, One Home, One Owner:** Each constraint in exactly one place; scattered rules create silent contradictions.
- **Rule 4 — Load It When You Need It:** Compact base context; lazy-load specialized instructions per task.
- **Rule 5 — Hard Rules Need Hard Checks:** Critical constraints need enforcement mechanisms, not just instruction text.
- **Rule 6 — Build for the Model and Product:** Revisit the harness after every significant model upgrade.

## Where It Applies

- Claude power users with accumulated instructions/skills/memory
- Codex/developer workspaces with layered local files
- Enterprise AI teams (every system prompt, permission, and tool schema is harness)
- Leaders evaluating vendor switches (underperformance may be in the harness you own)

## Receipts

- **18,384 words** loading in one route before the platform guide (Substack preview, exact figure)
- **66 skill routes / 172 instruction files** in his own audited Claude setup
- **Compact brief 3/3, enriched brief 1/3 on delivery** — ~5,000 extra instruction words improved analysis but failed delivery 2 of 3 runs
- **Fable 5 vs. ChatGPT 5.6** fail differently on harness-heavy tasks (12:17 in video)

## Contrarian Edge

Consensus says better model = better output. Nate's finding inverts this: on a harness-bloated setup, upgrading the model can make delivery *worse* — the new model engages with more of the accumulated context and gets stuck. The fix is harness surgery, not model shopping.

## What It Means For You

1. Audit before any model upgrade — you can't attribute performance changes without a clean harness baseline.
2. Run the Blame-the-Right-Layer test: same prompt, clean chat, no system prompt — works there = harness problem.
3. One Rule, One Home, One Owner: collapse your most critical instruction to one canonical file this week.
4. Compact base brief + lazy-loaded skills: Nate's data shows delivery improves even when reasoning depth appears to drop.

## Mistake to Avoid

Richer instructions ≠ better output. More instruction words add cognitive load without adding execution reliability. Every rule is a cost; audit before adding the next one.

## Linked Pages

- [[nate-b-jones]]
- [[ai-harness-audit]] (framework introduced)
- [[harness-bloat]] (phenomenon named)
