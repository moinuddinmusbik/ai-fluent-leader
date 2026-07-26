---
title: "Nate Herk Daily Implementation Playbook — 2026-07-25"
date: 2026-07-25
type: DEEP-DIVE
video_url: https://www.youtube.com/watch?v=2J3uX8iRNng
duration: "30:53"
routine: nate-herk-daily
---

# Nate Herk Daily Implementation Playbook — 2026-07-25

**Video:** I Tested Opus 5 vs. Fable 5. What You Need to Know.  
**Published:** 2026-07-25 | **Duration:** 30:53 | **Type:** DEEP-DIVE  
**Stack:** Claude Opus 5 · Claude Fable 5 · Claude Code · Codex (judge) · Excalidraw

---

## What It Is

Nate ran 10 structured head-to-head experiments — Claude Opus 5 vs. Claude Fable 5 — inside Claude Code with identical prompts across his real production workflows: codebase bug hunts, landing page builds, AI-generated announcement videos, LinkedIn carousels, audience research reports, video outlines, computer-use Snake game, and a structural engineering simulator. The headline finding: Opus 5 ended up _more expensive_ overall despite costing half as much per token, because it generated 2.4× more output tokens (2M vs. 832K) and ran an average of 63 minutes per session versus 25 minutes for Fable.

---

## How It Works

- **Test harness:** All experiments ran inside Claude Code (same harness, variable = the model). A few side tests were done directly in Claude Chat to compare "without a harness" feel.
- **Same prompt, both models:** Identical goal prompt submitted to each model; output quality judged by Nate and — for the bug hunt — by Codex acting as an independent reviewer.
- **Scorecard per experiment:** Cost ($), active time (min), input tokens, output tokens, model choices, tool calls, API calls — all captured from the Claude Code dashboard.
- **Consolidated scorecard (10 Opus / 8 Fable sessions):** Opus total: ~$247 across sessions, 2M output tokens, 630 min active. Fable: less total spend, 832K output tokens, ~200 min active.
- **Verification signal:** Codex was used in the bug-hunt session to evaluate both models' patches head-to-head — it judged Fable's one-liner production patch as more precise.

---

## The Verdict

Fable 5 wins on efficiency; Opus 5 wins on self-verification depth. Neither model is simply "better" — they interpret instructions differently, produce different aesthetics, and have different stopping criteria. Nate's practical recommendation: **run Fable 5 as orchestrator, Opus 5 as the sub-agent worker**. Fable delegates without burning context; Opus does the heavy execution while verifying its own work carefully.

---

## When To Use It (and When Not)

- **Use Opus 5 for:** knowledge work (research, content, reports), sub-agent tasks where thorough verification matters, tasks where you want the model to keep iterating until it succeeds.
- **Use Fable 5 for:** orchestration/planning (barely touches context when it just delegates), fast precise code fixes, tasks where speed and token efficiency matter.
- **Do NOT use Opus 5 as orchestrator:** it uses 2.4× more output tokens — even at half the per-token cost, it drove a higher total bill.
- **Consider older models for daily work:** Nate explicitly says both Opus 5 and Fable 5 are "overkill" for simple drafts and routine knowledge work.
- **Non-determinism caveat:** Same prompt produces different behavior each run. Don't over-index on one result.

---

## Set It Up

1. **Swap Opus 5 into your existing skills** — open Claude Code, change the model to Opus 5, and re-run two or three of your standard skills. Capture cost, time, and output quality.
2. **Build your scorecard** — note cost ($), active time (min), output tokens per test. Don't rely on per-token price alone.
3. **Try the orchestrator split** — start a Fable 5 session and tell it: "You shouldn't be writing any code or executing anything. You should just be telling Opus what to do."
4. **Add verification language to goal prompts** — Opus 5 naturally runs more sub-agents and verification loops; lean into this by writing prompts that explicitly request self-checking.
5. **Match model to task complexity** — ask whether the task needs frontier reasoning or if a Sonnet-tier model is sufficient.

---

## Prompts, Commands & Configs

```
# Orchestrator prompt to Fable 5 (spoken ~29:00)
"You shouldn't be writing any code or executing anything.
You should just be telling Opus what to do."

# Goal prompt style used across experiments
/goal Build me a [DELIVERABLE]. You can look through whatever
you want in my codebase / entire computer to figure out
the information to use. Make it as impressive as possible.

# Codex as judge pattern (bug hunt)
- Run both models on the same codebase prompt
- Submit both outputs to Codex: "Review these two patches
  head-to-head. Which production fix is more precise?"

# Model-matching heuristic (final thoughts)
- Orchestration / delegation → Fable 5 (stays under 300-400K ctx)
- Sub-agent execution / verification-heavy work → Opus 5
- Daily knowledge work / drafts → Sonnet-tier (both are overkill)
```

---

## Gotchas & Watch-Outs

- **Token math trap:** Opus 5 at half the per-token price still cost MORE overall — 2M output tokens vs Fable's 832K.
- **Structural simulator runaway:** Same prompt → Fable 7min $73 vs Opus 2h26min $112. Opus's verification loop kept spawning sub-agents.
- **Fable's "I'm done" problem:** Fable sometimes declares completion before reaching its capability ceiling. Add explicit completion criteria to prompts.
- **Context integrity matters:** The AIS Live video failure traced to outdated speaker data in Nate's internal docs — not the model. Keep your CLAUDE.md current.
- **Opus 5 ≠ Opus 4.8:** Same family, meaningfully different instruction interpretation. Re-run your skills on every major model upgrade.

---

## In His Words

> "You shouldn't be writing any code or executing anything. You should just be telling Opus what to do. And that saves your session limit with Fable big time because you can be running Fable for multiple hours or even a day and it won't even hit like 300K or 400K on the context because all it's doing is delegating." — ~29:00

> "Opus 5 spent more, which once again means that it's more inefficient — because Opus 5 per token is half the cost of Fable 5. So for it to be more expensive means that it's using way more tokens." — ~27:41

---

## Steal This For Your Org

1. **Run a model audit on your top 3 skills this week.** Swap Opus 5 in with same prompts. Record cost, time, quality per run.
2. **Deploy the Fable-orchestrates-Opus split** on your most token-hungry workflows. Fable stays under 300-400K context even after hours of delegating.
3. **Add a Codex-style verification step** to your code review workflow — two models solve independently, third AI judges both patches.
4. **Audit your AI OS context for stale data.** Schedule a monthly review of CLAUDE.md and knowledge base to prune expired context.

---

## Mistake to Avoid

Treating "cheaper per token" as "cheaper overall." Opus 5 costs half as much per output token as Fable 5 — and still ran up a higher total bill because it generated 2.4× more tokens. Budget by expected total token volume, not rate card alone.

---

## Source & Resources

- **Video:** [I Tested Opus 5 vs. Fable 5. What You Need to Know.](https://www.youtube.com/watch?v=2J3uX8iRNng) · 30:53
- **Chapters:** 0:00 Opus 5 Benchmarks vs Fable 5 · 1:00 Testing Without a Harness · 3:17 Codebase Bug Hunts · 5:19 Why Verification Matters · 6:51 AIS Live Announcement Video · 9:37 Landing Page Build · 12:15 LinkedIn Post & Carousel · 14:38 Audience Research Report · 16:58 Video Outline & Slide Deck · 20:18 Computer Use Snake Game · 22:39 Structural Simulator Build · 27:41 Total Cost & Token Breakdown · 29:19 Final Thoughts
- **Linked:** Full cost breakdown doc in Nate's free Skool community — [AI Automation Society](https://www.skool.com/ai-automation-society/about?el=Opus-5-vs-Fable-5)
