---
title: "How I Make Opus Think Like Fable (5 easy steps)"
date: 2026-07-07
creator: "[[nate-herk]]"
url: https://www.youtube.com/watch?v=XTBWVVcF3Pk
duration: 10:00
type: BUILD
lane: implementation
tags: [model-routing, fable-mode, claude-code, skill-files, effort-levels, opus]
related: [[fable-mode-skill]], [[model-routing-table]], [[2026-07-07-nate-herk-daily-transcript]]
---

# How I Make Opus Think Like Fable (5 easy steps)

[[nate-herk]] · BUILD · 2026-07-07 · 10:00 · [Watch](https://www.youtube.com/watch?v=XTBWVVcF3Pk)

---

## Stack
- [[Claude Code]] · [[Opus 4.8]] · [[Fable 5]] · Sonnet · Haiku · Claude Code Skills

## What He Builds
- **[[fable-mode-skill]]** — Claude Code skill file encoding Fable 5's five-gate working discipline; any model activates it via `/fable-mode`; free on Skool
- **[[model-routing-table]]** — Text table (model × cost score × intelligence × taste) given to an orchestrator to auto-delegate to cheapest capable model
- **Benchmark:** Opus orchestrator + Haiku scouts = same quality as all-Opus, ~3× cheaper

## How It Works (Architecture)
- **Core thesis:** "you can't keep the model's intelligence, but you can keep its process." (1:12)
- Fable orchestrating Opus sub-agents ≈ all-Fable dynamic workflow results — cost exponentially lower
- **Leaked Fable 5 system prompt insights:** (1) verify existence before assuming; (2) attempt ambiguous queries first, one clarifying question max; (3) calibrate effort — 1/3–5/5–10 passes by task depth
- **Effort-level finding:** Fable 5 LOW ≈ Opus 4.8 HIGH; xhigh/max can cause overthinking and worse output than high
- **Fable Mode 5 gates:** Scoping · Evidence · Attacking · Verifying · Calibrating

## Build It Yourself
1. Find best Fable deliverable → have Opus extract the reasoning chain ("What did you think to get here?")
2. Prompt: "Write a complete installable skill file that makes Opus 4.8 operate with your judgment, your planning, verification and reasoning habits and activated on something like fable mode."
3. Wire in 5 gates: Scope / Evidence / Attack / Verify / Calibrate
4. Add standing habits: verify existence · answer-first · acknowledge errors · stay on problem
5. Build model routing table (Cost/Intelligence/Taste) → paste into CLAUDE.md → test Opus orchestrator + Haiku scouts

## Prompts, Commands & Configs
```
# Skill generation prompt:
"Write a complete installable skill file that makes Opus 4.8
operate with your judgment, your planning, verification and
reasoning habits and activated on something like fable mode."

/fable-mode    # activation command once skill file is installed

# Model routing table (paste into CLAUDE.md):
| Model    | Cost Score | Intelligence | Taste |
|----------|-----------|--------------|-------|
| Fable 5  |     2     |      10      |  10   |
| Opus 4.8 |     4     |       9      |   8   |
| Sonnet   |     7     |       7      |   7   |
| Haiku    |     9     |       5      |   5   |
```

## Gotchas & Watch-Outs
- xhigh/max effort → overthinking → worse output than high; calibrate deliberately
- Don't couple workflows to a specific model name — encode behavior in skill files (model-portable)
- Benchmark routing with all-Opus baseline before claiming cost savings

## Steal This For Your Org
1. Run "Fable extraction" on your best AI deliverable → encode reasoning as a skill file
2. Rate every model your team uses (cost/intelligence/taste) → model routing table in CLAUDE.md
3. Effort-level audit on top 3 prompts — most routine tasks don't benefit from max effort
4. Model-independence test: if your main model disappeared, which workflows break? Fix those to skill files

## Mistake to Avoid
Treating model selection as the primary quality lever. Process and skill files are the real moat — not the frontier model itself.

## In His Words
> "you can't keep the model's intelligence, but you can keep its process." — 1:12

> "Kind of like a senior engineer that is about to retire and it's trying to package up everything that it knows to hand over to the new cohort of junior engineers that's going to come over or come in and take its place." — 2:23

## Source & Resources
- **Video:** [How I Make Opus Think Like Fable (5 easy steps)](https://www.youtube.com/watch?v=XTBWVVcF3Pk) · 10:00 · 50,369 views
- **Chapters:** 0:00 The Model Isn't the Moat · 1:15 Turning Opus Into Fable · 2:33 Leaked Fable System Prompt · 3:18 Effort Levels · 4:25 Building the Fable Mode Skill · 7:30 Model Routing Table · 9:15 Final Thoughts
- **Free skill:** [AI Automation Society Skool](https://www.skool.com/ai-automation-society/about) → Classroom → All YouTube Resources
