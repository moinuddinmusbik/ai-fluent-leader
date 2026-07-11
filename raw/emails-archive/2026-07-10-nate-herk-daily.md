# Nate Herk Daily Implementation Playbook — 2026-07-10

**Video:** [I Tested GPT 5.6 Sol vs Fable 5. What You Need To Know.](https://www.youtube.com/watch?v=EthxaDswUFo)  
**Duration:** 20:25 · **Type:** DEEP-DIVE · **Published:** 2026-07-10  
**Transcript:** Unavailable (Firecrawl actions timed out; sandbox IP rate-limited by YouTube timedtext API)

---

## What It Is

- **The test:** Nate ran GPT-5.6 Sol against Claude Fable 5 all day on real work — not benchmarks. Head-to-head in Codex vs Claude Code on three creative builds, then a battery of API one-off tasks covering speed, cost, and reliability.
- **GPT-5.6 Sol:** Fast, cost-effective worker. "Ships fast at a fraction of the price."
- **Claude Fable 5:** More creative, capable model. "The better manager."
- **The framing:** Manager (Fable) vs Worker (Sol). Not absolute better, but workflow slot fit.

## Stack

`GPT-5.6 Sol` · `Claude Fable 5` · `OpenAI Codex` · `Claude Code` · `Direct API`

## How It Works — Test Architecture

- **Test 1 – Browser Bike Game (0:51):** Codex/Sol vs Claude Code/Fable on a playable browser game.
- **Test 2 – Scroll-Stopping Website (3:31):** Visual design/front-end creativity under open brief.
- **Test 3 – Five Visual Worlds (6:16):** Five distinct visual environments — creative range and sustained quality.
- **API One-Off Tests (12:38):** Rapid-fire battery over API: latency, cost per task, consistency.
- **Final Verdict (17:00–19:50):** Ranked placement and decision rules.

## The Verdict

**Fable is the manager; Sol is the worker.** Fable 5 wins on creativity, complex orchestration, and open-ended builds. Sol wins on speed and cost for well-scoped, high-volume tasks. Choice depends on workflow slot and optimization target.

## When To Use It — And When Not

- **Fable 5:** Creative, open-ended, long-context, orchestration. Quality > cost.
- **Sol:** Well-scoped, one-shot, high-volume API tasks. Speed + cost are constraints.
- **Do not use Sol for:** Complex existing codebases (community: tests were one-shot frontend only).
- **Missing test:** Fable 5 vs Opus 4.8 would be the true frontier comparison.

## Set It Up

1. Audit current model usage — classify tasks into Fable-slot vs Sol-slot.
2. Run your own 5-task benchmark on actual work.
3. Set Fable as orchestrator in Claude Code for multi-step builds.
4. Route Sol via API for high-volume worker tasks.
5. Build a model routing table — revisit monthly.

## Prompts, Commands & Configs

No verbatim prompts shown — transcript unavailable. See linked resources.

Test structure (from chapters + description):
- Test 1 · Browser Bike Game → Codex (Sol) vs Claude Code (Fable)
- Test 2 · Scroll-Stopping Website → Codex (Sol) vs Claude Code (Fable)
- Test 3 · Five Visual Worlds → Codex (Sol) vs Claude Code (Fable)
- API Tests → Direct API: speed / cost / reliability

Model routing heuristic: creative/complex/orchestrator → Fable 5 | fast/cost-sensitive/executor → Sol

## Gotchas & Watch-Outs

- **One-shot bias:** All creative tests were blank-canvas frontend. Sol's edge may not hold on complex codebases.
- **Cost asymmetry is real:** "The cost difference is wild" (174 likes). Factor price gap into ROI.
- **Missing frontier comparison:** Fable vs Opus 4.8 is the true frontier matchup (viewer request).
- **Model drift:** Both models update frequently. Routing table is a living document.

## Steal This For Your Org

1. Run a two-model benchmark on your actual tasks this week (5 tasks, both models, log cost + quality).
2. Build a one-page model routing table for your team and share it.
3. Route high-volume, well-scoped tasks to Sol to recapture budget.
4. Position Fable as orchestrator, not workhorse, in multi-agent workflows.

## Mistake to Avoid

Picking one model as permanent default. These models have distinct strength profiles. Route by task type, not habit.

## Source & Resources

- **Video:** [I Tested GPT 5.6 Sol vs Fable 5. What You Need To Know.](https://www.youtube.com/watch?v=EthxaDswUFo) · 20:25
- **Chapters:** 0:00 Intro & Benchmarks · 0:51 Test 1: Browser Bike Game · 3:31 Test 2: Scroll-Stopping Website · 6:16 Test 3: Five Visual Worlds · 12:38 API One-Off Tests · 17:00 Final Verdict: Manager vs Worker · 19:20 Where Each Model Ranks · 19:50 Final Thoughts
- **Linked:** [$1M AI Agency Playbook](https://app.aiautomationsociety.ai/opaa-ads-optin) · [Free Resources (Skool)](https://www.skool.com/ai-automation-society/about)
- **Transcript:** Unavailable for this video.
