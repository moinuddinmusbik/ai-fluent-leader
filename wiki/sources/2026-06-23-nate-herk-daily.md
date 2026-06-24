---
title: "I Battle Tested Sakana Fugu's Fable Killer"
date: 2026-06-23
creator: "[[nate-herk]]"
url: https://www.youtube.com/watch?v=GpSqBjW6hR4
duration: 12:16
type: DEEP-DIVE
lane: implementation
views: 74210
likes: 1825
transcript_available: false
tags: [sakana, fugu, orchestration, claude-opus, deep-dive, benchmark]
---

# I Battle Tested Sakana Fugu's Fable Killer

[[nate-herk]] · 2026-06-23 · 12:16 · DEEP-DIVE

**URL:** https://www.youtube.com/watch?v=GpSqBjW6hR4

> **Transcript unavailable** — YouTube, youtubetranscript.com, and Firecrawl stealth all blocked. Content below is grounded in the video description, chapters, and top comments (74K views, 1,825 likes).

---

## Stack

- [[sakana-fugu-ultra]] (Fugu Ultra orchestration API)
- [[claude-opus-4-8]]
- [[claude-code]]
- Codex (OpenAI)
- Open Router Fusion API

---

## What It Is

Sakana AI dropped Fugu Ultra with viral claims that it matches Fable and Mythos performance. The core nuance: **Fugu is not a new model**. It is a single API that automatically orchestrates and routes tasks across existing frontier models — Claude Opus 4.8, GPT, and Gemini — similar to how Claude Code spins up sub-agents, but fully automated. Nate ran Fugu Ultra against Claude Opus 4.8 across 38 tasks to test whether the orchestration advantage is real.

---

## How It Works

- **Single API endpoint:** receives a task → automatically routes sub-tasks to the best available frontier model (Opus for heavy reasoning, GPT/Gemini for others)
- **Dashboard + Claude Code integration (2:32):** web dashboard for monitoring; runs directly inside Claude Code as the model endpoint
- **Orchestration Spectrum (3:30):** Nate maps the range from fully-manual model selection to Fugu's fully-automatic routing
- **vs Open Router Fusion API (5:07):** comparable multi-model fusion approach; Nate compares both so you can weigh alternatives
- **Speed & Cost Reality (5:39):** orchestration overhead is measurable — some tasks took over 2 minutes through Fugu vs. 6 seconds direct on Opus

---

## The Verdict

After 38 tasks, Nate is **not switching off Claude Code and Codex**. Fugu's automated routing does not consistently outperform a tuned Opus 4.8 setup at the workflow level. Latency overhead (up to 20× slower on some tasks) and cost unpredictability erode the theoretical multi-model quality gain. The viral "matches Fable and Mythos" framing was benchmarked under conditions that don't hold on real, representative workloads.

---

## When To Use It (and When Not)

**Consider Fugu when:**
- Exploratory/research tasks where quality matters far more than speed
- Experimenting with multi-model routing without manual wiring
- Free trial period (through end of June 2026) — benchmark against your stack before committing

**Avoid Fugu when:**
- Predictable sub-30-second task completion is required
- You already have a tuned Opus 4.8 workflow in Claude Code that clears your quality bar
- You're already paying for Claude Pro + Codex and need to justify every additional cost layer

**Alternative:** OpenCode + OMO plugin achieves similar multi-model routing using your own API keys (noted by community).

---

## Set It Up

1. **Start the free trial** — Go to the Fugu dashboard, create an account, get your API key
2. **Connect to Claude Code (2:32)** — Configure Fugu Ultra as the model endpoint, substituting it for the direct Opus 4.8 call
3. **Run your own baseline benchmark** — 5–10 tasks from your real workload. Track quality, wall-clock time, cost per task
4. **Review the Orchestration Spectrum (3:30)** — Map each task type onto the spectrum; "Opus wins solo" tasks don't need the routing layer
5. **Compare vs Open Router Fusion API (5:07)** — Price-compare for the same task mix before committing

---

## Prompts, Commands & Configs

No verbatim prompts shown — see linked resources. (Transcript unavailable; chapter 2:32 shows Claude Code integration but exact commands not captured.)

---

## Gotchas & Watch-Outs

- **Speed cliff is real:** Tasks that took 2+ minutes through Fugu vs. 6 seconds direct on Opus — blocker for time-sensitive pipelines
- **Recursive abstraction risk:** Fugu on top of Claude Code on top of Opus = three orchestration layers, three failure surfaces. Community top comment (82 likes): "Another harness that harnesses different harnesses"
- **Benchmark framing gap:** Viral "matches Fable/Mythos" claims don't replicate across diverse real-world workloads (38-task test)
- **Cost opacity:** Routing across multiple frontier APIs creates variable per-task cost harder to budget than a single-model subscription

---

## Steal This For Your Org

1. **Run the 38-task structure on your actual use cases** — 10 real tasks, Fugu Ultra vs. current best setup, track quality/latency/cost
2. **Map workloads on the Orchestration Spectrum** — Identify tasks that genuinely benefit from model routing vs. "just Opus" tasks
3. **Evaluate Open Router Fusion API** — Same use case, different pricing and integration path
4. **Define your quality floor first** — If Opus 4.8 clears 90%+ of your tasks, the case for routing layers weakens

---

## Mistake to Avoid

Treating viral benchmark framing as your evaluation. Nate's 38-task structured test showed the gap disappears at the workflow level, with some tasks regressing 20× on speed. Always benchmark against YOUR baseline on YOUR tasks.

---

## Source & Chapters

**Video:** [I Battle Tested Sakana Fugu's Fable Killer](https://www.youtube.com/watch?v=GpSqBjW6hR4) · 12:16

**Chapters:**
- 0:00 Intro & Fugu Dashboard Demo
- 1:00 How Fugu Actually Works
- 2:32 Running Fugu In Claude Code
- 3:30 The Orchestration Spectrum
- 5:07 vs Open Router Fusion API
- 5:39 Speed And Cost Reality
- 6:28 The 38-Task Test
- 10:27 Final Takeaway
- 11:45 Outro

**Linked resources:** No substantive article/doc links in description (sponsor/affiliate links only).

**Transcript note:** Unavailable — YouTube blocking. Content grounded on description + chapters + top comments.

**Related notes:** [[nate-herk]] · [[2026-06-23-nate-herk-daily-transcript]] (N/A — unavailable)
