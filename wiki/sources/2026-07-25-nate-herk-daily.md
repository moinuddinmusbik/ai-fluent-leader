---
title: "I Tested Opus 5 vs. Fable 5. What You Need to Know."
date: 2026-07-25
type: DEEP-DIVE
source: youtube
channel: "[[nate-herk]]"
url: https://www.youtube.com/watch?v=2J3uX8iRNng
duration: "30:53"
tags: [claude-opus-5, claude-fable-5, claude-code, model-comparison, deep-dive]
transcript: "[[2026-07-25-nate-herk-daily-transcript]]"
---

# I Tested Opus 5 vs. Fable 5. What You Need to Know.

**Channel:** [[nate-herk]] | **Published:** 2026-07-25 | **Duration:** 30:53 | **Type:** DEEP-DIVE  
**Stack:** [[claude-opus-5]] · [[claude-fable-5]] · [[claude-code]] · Codex (judge) · Excalidraw  
**Transcript:** [[2026-07-25-nate-herk-daily-transcript]]

---

## What It Is

Nate ran 10 structured head-to-head experiments — Claude Opus 5 vs. Claude Fable 5 — inside Claude Code with identical prompts across his real production workflows: codebase bug hunts, landing page builds, AI-generated announcement videos, LinkedIn carousels, audience research reports, video outlines, computer-use Snake game, and a structural engineering simulator.

**Headline finding:** Opus 5 ended up _more expensive_ overall despite costing half as much per token — it generated 2.4× more output tokens (2M vs. 832K for Fable) and averaged 63 min/session vs. 25 min for Fable sessions.

---

## How It Works (Test Design)

- All experiments run in **Claude Code** harness; model = the only variable
- Same goal prompt submitted to both models for every task
- **Codex used as independent judge** on bug-hunt outputs (evaluated both patches head-to-head)
- Scorecard per experiment: cost ($), active time, input/output tokens, API calls, tool calls
- 10 Opus 5 sessions vs. 8 Fable 5 sessions (Nate accidentally ran one extra Opus session)

### Experiment Results Summary

| Experiment | Fable 5 | Opus 5 | Winner |
|---|---|---|---|
| Codebase bug hunt | 11 min, $5.30 | 13 min, $4.22 | Fable (more precise patch per Codex) |
| AIS Live announcement video | 7 min, $7 (1 video) | 40 min, $11.19 (2 videos) | Mixed — Opus made 2, Fable's data more accurate |
| Landing page build | Similar quality | Similar quality | Tie |
| Structural simulator | 7 min, $73 | 2h26m, $112 | Opus (more complete; Fable stopped early) |
| Totals | ~832K tokens, 200 min active | ~2M tokens, 630 min active | Fable on efficiency |

---

## The Verdict

- **Fable 5** wins on efficiency, speed, and token economy
- **Opus 5** wins on verification depth and self-iteration quality
- **Best pattern:** Fable as orchestrator, Opus as sub-agent worker
- **Gotcha:** Opus 5 is not automatically cheaper — total cost can be higher despite lower per-token rate

---

## When To Use It (and When Not)

- **Opus 5:** knowledge work, sub-agent execution, verification-heavy builds, tasks where you want the model to keep iterating
- **Fable 5:** orchestration, fast precise code fixes, token-efficient execution
- **Older Sonnet models:** daily drafts and routine knowledge work — both Opus 5 and Fable 5 are overkill
- **Non-determinism:** same prompt, different results each run; don't over-index on one experiment

---

## Set It Up

1. Swap Opus 5 into your existing Claude Code skills; run identical prompts; capture scorecard
2. Build your personal cost/time/quality scorecard per task type
3. Try orchestrator split: Fable delegates ("you shouldn't be writing any code, just tell Opus what to do"), Opus executes
4. Add verification language to goal prompts to lean into Opus's self-checking tendency
5. Match model intelligence to task complexity — Sonnet-tier handles most daily work

---

## Prompts, Commands & Configs

```
# Orchestrator split prompt (to Fable 5, spoken ~29:00)
"You shouldn't be writing any code or executing anything.
You should just be telling Opus what to do."

# Goal prompt style used across experiments
/goal Build me a [DELIVERABLE]. You can look through whatever
you want in my codebase / entire computer to figure out
the information to use. Make it as impressive as possible.

# Codex as judge (bug hunt)
Submit both outputs: "Review these two patches head-to-head.
Which production fix is more precise?"

# Model-matching heuristic
- Orchestration → Fable 5 (stays under 300-400K ctx)
- Sub-agent execution → Opus 5
- Daily knowledge work → Sonnet-tier
```

---

## Gotchas & Watch-Outs

- **Token math trap:** Opus 5 emitted 2.4× more tokens than Fable → higher total cost despite lower rate
- **Structural simulator runaway:** Opus ran 2h26m / $112 vs Fable's 7min / $73 on the same prompt — Opus's verification loop kept spawning sub-agents
- **Fable's "done" problem:** Fable sometimes stops before its capability ceiling; add explicit completion criteria to prompts
- **Context integrity > model choice:** AIS Live video failure traced to stale speaker data in Nate's OS — not the model
- **Opus 5 ≠ Opus 4.8:** Different instruction interpretation; re-run all skills after model upgrade

---

## In His Words

> "You shouldn't be writing any code or executing anything. You should just be telling Opus what to do. And that saves your session limit with Fable big time because you can be running Fable for multiple hours or even a day and it won't even hit like 300K or 400K on the context because all it's doing is delegating." — ~29:00

> "Opus 5 spent more, which once again means that it's more inefficient — because Opus 5 per token is half the cost of Fable 5. So for it to be more expensive means that it's using way more tokens." — ~27:41

---

## Steal This For Your Org

1. **Model audit this week:** swap Opus 5 into your top 3 skills, record cost/time/quality
2. **Fable-orchestrates-Opus split:** Fable as router keeps context under 300-400K even after hours
3. **Codex-style verification:** two models solve independently, third AI judges both patches
4. **Monthly OS audit:** review and prune CLAUDE.md + knowledge base for stale context

---

## Mistake to Avoid

Treating "cheaper per token" as "cheaper overall." Opus 5 generated 2.4× more tokens and ran up a higher total bill. Budget by expected total token volume, not rate card alone.

---

## Source & Resources

- **Video:** [I Tested Opus 5 vs. Fable 5. What You Need to Know.](https://www.youtube.com/watch?v=2J3uX8iRNng) · 30:53
- **Chapters:** 0:00 Benchmarks · 1:00 Without a Harness · 3:17 Bug Hunts · 5:19 Verification · 6:51 AIS Live Video · 9:37 Landing Page · 12:15 LinkedIn · 14:38 Research Report · 16:58 Outline & Slides · 20:18 Computer Use · 22:39 Structural Simulator · 27:41 Cost Breakdown · 29:19 Final Thoughts
- **Linked:** [Full cost breakdown doc — AI Automation Society Skool](https://www.skool.com/ai-automation-society/about?el=Opus-5-vs-Fable-5)
