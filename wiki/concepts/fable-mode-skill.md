---
title: "Fable Mode Skill"
type: concept
created: 2026-07-07
updated: 2026-07-07
tags: [claude-code, skill-files, fable-5, opus, model-routing, reasoning]
sources: [[2026-07-07-nate-herk-daily]]
---

# Fable Mode Skill

A Claude Code installable skill file that encodes [[Fable 5]]'s five-gate working discipline into a portable, model-agnostic format. Introduced by [[nate-herk]] on 2026-07-07.

## What It Is

A skill file (`.claude/skills/fable-mode.md` or equivalent) that, when activated via `/fable-mode`, injects Fable's reasoning habits into any model — including Opus 4.8, Sonnet, or even GPT — making it "feel elevated" without requiring Fable 5 access.

## The 5 Gates

| Gate | Name | What It Does |
|------|------|-------------|
| 1 | SCOPING | Scope the work; play devil's advocate on the plan before starting |
| 2 | EVIDENCE | Require evidence before any reasoning step |
| 3 | ATTACKING | Reason adversarially; explore every unknown and failure mode |
| 4 | VERIFYING | Verify before declaring done |
| 5 | CALIBRATING | Match effort level to task size (1 pass / 3-5 / 5-10) |

## Standing Habits (from leaked Fable 5 system prompt)

- Partial memory ≠ current knowledge → verify before assuming
- A prompt implying a file exists ≠ the file exists → check
- Ambiguous queries → attempt answer first; one clarifying question max
- Errors → acknowledge, stay on problem, maintain forward momentum

## How to Generate It

Prompt Fable or Opus: *"Write a complete installable skill file that makes Opus 4.8 operate with your judgment, your planning, verification and reasoning habits and activated on something like fable mode."*

## Why It Matters

Nate ran dynamic workflows comparing Fable orchestrating Fable sub-agents vs. Fable orchestrating Opus sub-agents with the Fable Mode skill. Results were equivalent; the all-Fable run cost exponentially more. The skill captures the process, not the model.

## Free Resource

Available in the [AI Automation Society Skool](https://www.skool.com/ai-automation-society/about) (free tier → Classroom → All YouTube Resources).

## Related
- [[model-routing-table]]
- [[2026-07-07-nate-herk-daily]]
- [[nate-herk]]
