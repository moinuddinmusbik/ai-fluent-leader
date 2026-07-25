---
title: "5 Hacks to Instantly Level Up Your AI OS"
type: source
lane: implementation
creator: [[nate-herk]]
date: 2026-07-24
video_id: Ek1NBfnnTH0
video_url: https://www.youtube.com/watch?v=Ek1NBfnnTH0
video_type: DEEP-DIVE
duration: 25:04
stack: [claude-code, opus-4-8, claude-md, os-audit-skill, github, hyperagent]
tags: [ai-os, context-management, routing, audit, segmentation, cron-automation]
---

# 5 Hacks to Instantly Level Up Your AI OS

**Creator:** [[nate-herk]]  
**Date:** 2026-07-24  
**Type:** DEEP-DIVE  
**URL:** https://www.youtube.com/watch?v=Ek1NBfnnTH0  
**Duration:** 25:04  
**Transcript:** [[2026-07-24-nate-herk-daily-transcript]]

---

## What It Is

Five specific hacks Nate runs on his Herk 2 project to keep his AI OS accurate as data grows, grounded in a live [[os-audit-skill]] he built and gives away free. The core diagnostic framework: four context failure modes (poisoning, bloat, confusion, clash) and two context types (expertise vs. situational).

## How It Works — The 4 Failure Modes + 2 Context Types

| Mode | What Happens | Fix |
|------|-------------|-----|
| **Poisoning** | False fact in context → confidently delivered | Verification loop: web search, DB cross-check, human-in-the-loop |
| **Bloat** | Too much data → needle-in-haystack | Expertise/situational split; segment knowledge |
| **Confusion** | Missing/irrelevant facts → hallucination fill | Add missing routing; prune irrelevant context |
| **Clash** | Conflicting sources → agent guesses | Freshness checks; timestamp policies; single source of truth |

**Expertise context** (always-loaded rulebook): identity, goals, policies — like the principal who knows how classrooms run.

**Situational context** (just-in-time): specific customer ticket, yesterday's meeting — like the teacher who knows which students need special seating. Load only when the situation demands it.

## Set It Up — The 5 Hacks

1. **CLAUDE.md as a Router** — top-level CLAUDE.md is a pure routing table: "If you need X, go to [path]." Sub-folders get their own CLAUDE.mds. Background/goals can live in a referenced file.
2. **Have AI Audit Itself** — download free [[os-audit-skill]] from Skool, or prompt: "Read everything, check routing rules, tell me what's wrong, wait for my approval." Run end of week or after major data additions.
3. **Build Automations to Update Data** — recurring data pulls (meeting notes, Q&A transcripts, Fireflies) become crons. Natural language: "Set up a weekly cron to pull in my Fireflies transcripts into my meetings wiki."
4. **Segment Knowledge** — split growing, distinct knowledge bases into separate wikis. Nate has a YouTube transcripts wiki + a meetings transcripts wiki (Claude Code suggested the split when performance degraded). Client work: internal knowledge in AIOS, deliverables in separate external repo.
5. **Backtrack** — when Claude says "I don't have access to that" but it does: "Go look through what you did, where you searched, figure out why you didn't find that right away. Then fix the routing."

## Prompts & Configs

```
/os-audit
# "Is your AIOS still true? This is your operating manual.
# Indexes and wikis are claims about what exists and what's current.
# Read only — never fix, rename, or delete. Just report."

# Backtrack prompt (verbatim, from transcript 23:12):
"You told me you didn't have access to [X], but I know you do.
Go look through what you did, where you searched, and help me figure out
why you didn't find that data right away. Then update the routing."

# CLAUDE.md routing entry pattern:
# "If you need [X], go to [path]"
# Standard entries: wiki path, hot cache, index, GP fallback,
#   memory system, API keys, skills/agents, decisions log,
#   templates, references, projects, other worlds

# Cron (natural language):
"Set up a weekly cron to pull [data source] into [target wiki]."
```

## Gotchas & Watch-Outs

- **Team syncing is a people problem, not a tech problem** (24:16) — habit change and permissioning are the blockers. Master your own OS before bringing it to team level.
- **Don't mix Obsidian Sync + Git on same vault from multiple machines** — conflicts and duplicate changes (community note from @johnnydalvi3978).
- **Clash is sneaky** — you may not know conflicting policies exist in context until a customer gets the wrong answer.
- **Audit ≠ cron** — audit catches drift after it happens; crons prevent it. Use both.

## In His Words

> "My cloudmd is essentially just a master routing file, just a master table of context." — [14:02]

> "There's the only way that you're doing this wrong is if you're constantly getting wrong answers and you're not doing anything about it." — [18:23]

## Steal This For Your Org

1. Run the free [[os-audit-skill]] this week — routing integrity + index truth + freshness in ~2 min.
2. Rewrite your CLAUDE.md as a routing table: "If you need [X], go to [path]."
3. Set up one automated data pipeline this sprint for your most common manual pull.
4. Introduce the Backtrack habit: when AI can't find data, have it trace what it tried, update the routing.

## Mistake to Avoid

Treating top-level CLAUDE.md as a system prompt. As the project grows, misrouting and bloat compound. Make it almost purely a routing table.

## Source & Resources

- **Video:** [5 Hacks to Instantly Level Up Your AI OS](https://www.youtube.com/watch?v=Ek1NBfnnTH0) · 25:04
- **Chapters:** 0:00 Intro · 0:39 Running the OS Audit Skill · 1:38 The 4 Context Failure Modes · 4:34 Expertise vs Situational Context · 6:57 Sponsor · 7:58 Audit Results & Skill Walkthrough · 11:56 Tip 1 · 16:53 Tip 2 · 19:09 Tip 3 · 20:15 Tip 4 · 22:50 Tip 5 · 23:48 Team Syncing & Final Thoughts
- [Hyperagent — Nate's Council Skill ($1,000 free credits)](https://hyperagent.com/marketplace/s/ccs01KWCXR3W4_XRNS6AAXVZBT0617)
- Free [[os-audit-skill]] on Skool (link in video description)
