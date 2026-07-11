---
title: "2026-07-10 Nate Herk Daily — I Tested GPT 5.6 Sol vs Fable 5"
type: source
created: 2026-07-10
updated: 2026-07-10
tags: [nate-herk, deep-dive, model-comparison, gpt-5-6-sol, fable-5, model-routing]
routine: nate-herk-daily
video_url: https://www.youtube.com/watch?v=EthxaDswUFo
duration: "20:25"
video_type: DEEP-DIVE
transcript_available: false
---

# I Tested GPT 5.6 Sol vs Fable 5. What You Need To Know.

[[nate-herk]] · Published 2026-07-10 · 20:25 · DEEP-DIVE  
[Watch](https://www.youtube.com/watch?v=EthxaDswUFo)

> **Transcript unavailable** — Firecrawl actions timed out and sandbox IP is rate-limited by YouTube. Playbook grounded on description, chapter list, and top community comments.

---

## Stack

- `GPT-5.6 Sol` (OpenAI)
- `Claude Fable 5` (Anthropic)
- `OpenAI Codex` (coding environment for Sol tests)
- `Claude Code` (coding environment for Fable tests)
- `Direct API` (one-off task battery)

---

## How It Works — Test Architecture

Nate ran five distinct test categories:

| Chapter | Task | Models |
|---------|------|--------|
| 0:51 | Browser Bike Game | Codex/Sol vs Claude Code/Fable |
| 3:31 | Scroll-Stopping Website | Codex/Sol vs Claude Code/Fable |
| 6:16 | Five Visual Worlds | Codex/Sol vs Claude Code/Fable |
| 12:38 | API One-Off Tests | Sol API vs Fable API (speed, cost, reliability) |
| 17:00 | Final Verdict | Manager vs Worker ranking |

All three creative tests (Tests 1–3) were blank-canvas, one-shot frontend builds.

---

## The Verdict

**Fable is the manager; Sol is the worker.**

- **Fable 5:** More creative, more capable, better on open-ended / complex / long-context tasks. The orchestrating brain in a multi-agent workflow.
- **Sol:** Ships fast, costs a fraction of Fable's price. Best for well-scoped, high-volume, executor-tier tasks.

Not "which is better" — but which fits which slot and cost tier.

---

## When To Use Each

**Fable 5:**
- Creative, open-ended, long-context
- Orchestrator in multi-agent workflows
- Quality is the binding constraint

**Sol:**
- Well-scoped, one-shot, or high-volume API tasks
- Executor being directed by a manager model
- Speed and cost are the binding constraints

**Caution:** Tests were one-shot frontend tasks — Sol's edge may not hold on complex existing codebases with multi-step feature adds.

---

## Build Steps — Implementing the Manager/Worker Split

1. **Audit task inventory** — classify each into Fable-slot (creative/complex) vs Sol-slot (fast/scoped).
2. **Run your own 5-task benchmark** — actual work tasks, both models, log quality and cost per task.
3. **Set Fable as orchestrator in Claude Code** — for multi-step agentic builds.
4. **Route Sol via API** for high-volume, well-scoped tasks (content gen, classification, extraction).
5. **Build a model routing table** — one-page doc, task type → preferred model, revisit monthly.

---

## Prompts, Commands & Configs

No verbatim prompts captured (transcript unavailable).

```
Model routing heuristic (from Nate's verdict):
  creative / complex / orchestrator  →  Claude Fable 5
  fast / cost-sensitive / executor   →  GPT-5.6 Sol
```

---

## Gotchas & Watch-Outs

- **One-shot bias** — all creative tests were blank-canvas frontend. Real-world codebase complexity may shift results (community: 28 likes on this caveat).
- **Cost asymmetry is real** — "The cost difference is wild" (174 likes). Sol at a fraction of Fable's price materially changes ROI for high-volume use cases.
- **Missing frontier comparison** — Fable 5 vs Opus 4.8 is the true frontier matchup; Sol vs Fable is partly a cost-tier comparison. Viewers flagged this (18 likes).
- **Model drift** — both models update frequently. Routing table is a living document.

---

## Steal This For Your Org

1. Run a two-model benchmark on 5 actual work tasks this week. Log quality + cost.
2. Build and share a one-page model routing table with your team.
3. Route high-volume, well-scoped tasks to Sol — recapture budget for Fable-tier work.
4. Position Fable as orchestrator, not workhorse, in any multi-agent workflow.

---

## Mistake to Avoid

Picking one model as a permanent default. Nate's test surfaces two distinct strength profiles. Route by task type; don't let habits decide.

---

## Source & Chapters

- **Video:** https://www.youtube.com/watch?v=EthxaDswUFo · 20:25
- **0:00** Intro & Benchmarks
- **0:51** Test 1: Browser Bike Game
- **3:31** Test 2: Scroll-Stopping Website
- **6:16** Test 3: Five Visual Worlds
- **12:38** API One-Off Tests
- **17:00** Final Verdict: Manager vs Worker
- **19:20** Where Each Model Ranks
- **19:50** Final Thoughts
- **Linked resources:** [$1M AI Agency Playbook](https://app.aiautomationsociety.ai/opaa-ads-optin) · [Free Resources (Skool)](https://www.skool.com/ai-automation-society/about)
- **Transcript:** Unavailable
