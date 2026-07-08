---
title: "Nate Herk Daily Implementation Playbook — 2026-07-07"
date: 2026-07-07
routine: nate-herk-daily
type: email-archive
---

# Nate Herk Daily Implementation Playbook — 2026-07-07

**Video:** [How I Make Opus Think Like Fable (5 easy steps)](https://www.youtube.com/watch?v=XTBWVVcF3Pk) · 10:00 · BUILD  
**Published:** 2026-07-07 · 50,369 views

---

## Stack
Claude Code · Opus 4.8 · Fable 5 · Sonnet · Haiku · Claude Code Skills

## What He Builds
- **Fable Mode Skill** — Claude Code installable skill file encoding Fable 5's 5-gate working discipline (Scope → Evidence → Attack → Verify → Calibrate); activates on `/fable-mode`; free on Skool
- **Model Routing Table** — Structured table (model × cost score × intelligence × taste) for orchestrators to auto-delegate tasks to the cheapest capable model
- **Benchmark test** — Opus orchestrator + Haiku scouts: same quality as all-Opus, ~3× cheaper

## How It Works (Architecture)
- **Core insight:** Fable orchestrating Opus sub-agents ≈ all-Fable workflows at a fraction of cost — process beats model
- **Leaked Fable system prompt:** (1) partial memory ≠ current knowledge; (2) attempt ambiguous queries, then one question max; (3) calibrate effort — 1 pass for signal facts, 3–5 medium, 5–10 deep research
- **Effort levels:** Fable 5 LOW ≈ Opus 4.8 HIGH in quality; xhigh/max can cause overthinking and worse output
- **5 gates:** Scoping before you work · Evidence before reasoning · Reasoning adversarially · Verifying before declaring done · Calibrating
- **Routing table columns:** Cost score (higher = cheaper) · Intelligence · Taste/creativity

## Build It Yourself
1. Pick your best Fable output; have Opus analyze the session: "What did you think to get here? How did you verify it?"
2. Prompt: "Write a complete installable skill file that makes Opus 4.8 operate with your judgment, your planning, verification and reasoning habits and activated on something like fable mode."
3. Wire in the 5 gates: Scope/Evidence/Attack/Verify/Calibrate
4. Add standing habits from leaked Fable prompt: verify existence, answer-first, acknowledge errors
5. Build the model routing table (Cost/Intelligence/Taste columns) and paste into CLAUDE.md; test with Opus orchestrator + Haiku scouts

## Prompts, Commands & Configs

```
# Skill generation prompt:
"Write a complete installable skill file that makes Opus 4.8
operate with your judgment, your planning, verification and
reasoning habits and activated on something like fable mode."

# Activation:
/fable-mode

# 5 Gates (encode in skill file):
Gate 1 — SCOPING:   Scope the work; play devil's advocate on plan
Gate 2 — EVIDENCE:  Evidence before any reasoning step
Gate 3 — ATTACKING: Reason adversarially; explore every unknown
Gate 4 — VERIFYING: Verify before declaring done
Gate 5 — CALIBRATE: Match effort level to task size

# Model routing table:
| Model    | Cost Score | Intelligence | Taste |
|----------|-----------|--------------|-------|
| Fable 5  |     2     |      10      |  10   |
| Opus 4.8 |     4     |       9      |   8   |
| Sonnet   |     7     |       7      |   7   |
| Haiku    |     9     |       5      |   5   |
```

## Gotchas & Watch-Outs
- Higher effort ≠ better: xhigh/max caused Nate's models to overthink and produce worse results than high
- Don't couple to a specific model — process and skill files should be model-portable
- Benchmark routing with a baseline (all-Opus first) before claiming cost savings

## Steal This For Your Org
1. **Fable extraction** — have Opus analyze your best AI deliverable, extract the reasoning chain, encode as a skill file
2. **Map the routing table** — rate every model your team uses (cost/intelligence/taste); paste into CLAUDE.md
3. **Effort-level audit** — run top 3 prompts at high vs. xhigh; most routine tasks won't benefit from max effort
4. **Model-independence test** — would your workflows survive if your main model disappeared? Fix anything that breaks to a skill/system-prompt, not a model name

## Mistake to Avoid
Treating model selection as the primary quality lever. Fable orchestrating Opus ≈ all-Fable results at a fraction of the cost — upgrading your model without auditing instructions and routing logic wastes the premium.

## In His Words
> "you can't keep the model's intelligence, but you can keep its process." — 1:12

> "Kind of like a senior engineer that is about to retire and it's trying to package up everything that it knows to hand over to the new cohort of junior engineers that's going to come over or come in and take its place." — 2:23

## Source & Resources
- **Video:** [How I Make Opus Think Like Fable (5 easy steps)](https://www.youtube.com/watch?v=XTBWVVcF3Pk) · 10:00 · 50,369 views
- **Chapters:** 0:00 The Model Isn't the Moat · 1:15 Turning Opus Into Fable · 2:33 Leaked Fable System Prompt · 3:18 Effort Levels · 4:25 Building the Fable Mode Skill · 7:30 Model Routing Table · 9:15 Final Thoughts
- **Linked:** Free Fable Mode skill in [AI Automation Society Skool](https://www.skool.com/ai-automation-society/about) (free tier → Classroom → All YouTube Resources)
- **Transcript:** [[2026-07-07-nate-herk-daily-transcript]]
