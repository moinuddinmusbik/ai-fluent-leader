---
title: "Nate B Jones Daily Leader Briefing — 2026-07-15"
date: 2026-07-15
routine: nate-b-jones-daily
lens: FRAMEWORK
video_id: PDJfciNhyHU
---

# Nate B Jones Daily Leader Briefing — 2026-07-15

**Lens:** FRAMEWORK  
**Title:** Every Prompt You Send Drags 18,384 Words Of Junk. Here's How I Cut It.  
**Video:** https://www.youtube.com/watch?v=PDJfciNhyHU (15:51)  
**Substack:** https://natesnewsletter.substack.com/p/ai-harness-audit (preview; full post paid)

---

## The Big Idea

Nate discovered that one common writing route in his AI setup was loading **18,384 words** before reaching the guide for the platform he was actually writing for. He never typed those words in a single session — he accumulated them, one correction at a time, every time his AI missed something. The engine (the model) got smarter with each upgrade. The harness didn't. His core argument: most leaders are running a harness built for a model they no longer use, and that invisible drag means your upgraded AI can feel *worse* than a fresh chat. The fix is not a better model — it's a systematic audit of the instructions wrapped around the one you already have.

## The Framework: The AI Harness Audit

A **harness** is everything wrapped around the model that you or your product can actually configure: custom instructions, project files, saved prompts, memory, skills, tools, permissions, examples, and checks. It shapes the answer before you type your next prompt — and it does *not* include hidden internals inside Anthropic or OpenAI, only what you can actually inspect and change.

Nate built two runnable skills: **Clean My AI Harness — Claude Edition** and **Clean My AI Harness — Codex Edition**. Each maps the setup, identifies what's dragging, and produces a cleanup plan with user approval required before anything moves.

## How It Works: The Six Rules

- **Rule 1 — Map Before You Clean:** Run the audit skill first. Nate found 66 skill routes and 172 instruction files in his own setup.
- **Rule 2 — Blame the Right Layer:** Test whether failure is the model or the harness before concluding anything.
- **Rule 3 — One Rule, One Home, One Owner:** Each constraint lives in exactly one place. Scattered rules create contradictions the model silently resolves — usually wrong.
- **Rule 4 — Load It When You Need It:** Strip base context to a compact brief. Load specialized instructions only when needed.
- **Rule 5 — Hard Rules Need Hard Checks:** Important constraints need enforcement mechanisms, not just instruction text.
- **Rule 6 — Build for the Model and Product:** Rules tuned for the last model may hurt the current one. Revisit the harness after every significant model upgrade.

## Where It Applies

- Claude power users with accumulated custom instructions, skills, or memory files
- Codex / developer workspaces with layered local instruction files
- Enterprise AI teams deploying agents (every system prompt, permission, and tool schema is part of the harness)
- Leaders evaluating AI vendor switches (underperformance may be in your harness, not the model)

## Receipts

- **18,384 words** loading in one writing route before reaching the platform guide
- **66 skill routes / 172 instruction files** found in Nate's own Claude setup
- **Compact brief 3-for-3:** ~5,000 extra words of instructions made the model a better analyst — but it failed delivery 2 out of 3 runs. The compact brief passed all three.
- **Fable 5 vs. ChatGPT 5.6** fail for different reasons on the same harness-heavy task (breakdown at 12:17 in video)

## What It Means For You

1. **Audit before your next model upgrade.** Schedule a harness review before switching model versions — without it you can't tell whether the model change helped.
2. **Run the Blame-the-Right-Layer test first.** Test the same prompt in a clean chat with no system prompt. If it works there, the problem is your harness.
3. **Apply One Rule, One Home, One Owner this week.** Collapse your most important instruction into one canonical file. Delete the rest.
4. **Switch your base context to a compact brief.** Load specialist contexts only when needed. Track delivery — Nate's data says it improves.

## Mistake to Avoid

Equating richer instructions with better output. Adding 5,000 words improved Fable 5's reasoning scores but caused it to fail delivery two out of three times. Every rule is a cost, not just a feature.

## Source

- Video: [Every Prompt You Send Drags 18,384 Words Of Junk. Here's How I Cut It.](https://www.youtube.com/watch?v=PDJfciNhyHU) — 15:51
- Substack: [AI Harness Audit](https://natesnewsletter.substack.com/p/ai-harness-audit) (preview; full post paid)
- Chapters: 00:00 I Overbuilt My AI Harness · 01:58 The Hidden Cost of Harness Bloat · 04:54 Rule 2 · 06:06 Rule 3 · 07:27 Rule 4 · 08:25 Rule 5 · 08:58 Rule 6 · 10:58 Codex Audit Results · 12:17 Fable 5 vs. ChatGPT 5.6 · 12:54 A Clean Harness Without the Barnacles · 14:17 Own the System Around Your AI
