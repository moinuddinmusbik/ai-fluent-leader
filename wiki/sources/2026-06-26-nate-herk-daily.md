---
title: "I asked Claude Code to make me as much money as possible"
date: 2026-06-26
routine: nate-herk-daily
type: BUILD
video_id: iTY8Q449YNQ
url: https://www.youtube.com/watch?v=iTY8Q449YNQ
duration: "28:13"
creator: "[[nate-herk]]"
views: 70005
likes: 2116
stack: [Claude Code, Claude Opus 4.8, Custom CC Skills]
tags: [claude-code, agent-workflow, verification, sub-agents, context-management, income, implementation]
---

# 2026-06-26 — I asked Claude Code to make me as much money as possible

[[nate-herk]] · BUILD · 28:13 · [Watch](https://www.youtube.com/watch?v=iTY8Q449YNQ)

Related: [[2026-06-26-nate-herk-daily-transcript]] (auto-caption text; direct panel unavailable this run)

---

## What He Builds

Four Claude Code upgrades that together fix the core design flaws causing Claude to waste your time and money:

1. **The Council (Idea Roaster)** — multi-agent adversarial review before any build
2. **Build, Then Verify** — proof-of-done skill with screenshots and form tests
3. **Session Handoff** — context-reset document for clean restarts
4. **Sub-Agents + Goal Loops** — parallel deliverable harness with verification gate

---

## Stack

- [[claude-code]] — primary tool
- Claude Opus 4.8 — implied model for council agents
- Custom Claude Code skills (downloadable, Google Drive)
- Google Drive — skill distribution

---

## Architecture / How It Works

Claude has three built-in design flaws that cost builders money:
1. **Sycophancy:** Tuned to make you feel productive, not to make you money. Validates weak ideas.
2. **False completion:** Says "done" without verifying. Confidence ≠ evidence.
3. **Context rot:** Quality degrades in long sessions as context fills with stale decisions and abandoned branches.

The income equation: `income = f(quality × speed)`. Each upgrade targets one or both.

The council fix uses adversarial multi-agent structure — five roles that cannot all agree: Contrarian / Buyer / Market Researcher / First-Principles Thinker / Judge. The Judge role delivers an actionable verdict (green light / reshape / kill) with: strongest failure reason, strongest upside, riskiest assumption, cheapest 48-hour test.

---

## Build It Yourself (Step-by-Step)

1. Download the four skills from Nate's [Google Drive folder](https://drive.google.com/drive/folders/1eCOxxiFSMz49UONwPlbOfDnkHj9QzDg5). Read each file before installing.
2. **Upgrade 1 — Council Roast:** Invoke `/roast [idea]` before any build. Accept only green light verdict; reshape or kill otherwise.
3. **Upgrade 2 — Verify:** After any build, invoke `/verify`. Claude starts local server, captures screenshots (desktop + mobile), tests forms, reports file evidence.
4. **Upgrade 3 — Handoff:** At ~100k tokens or session slowdown, invoke `/handoff`. Paste output into a fresh thread.
5. **Upgrade 4 — Sub-Agent Goal Loop:** For projects with 3+ independent deliverables, invoke sub-agent skill. One agent per deliverable, each writing to its own file. Lead agent verifies all at the end.
6. Run the full stack: Council → Build with Verify → Handoff when needed → Sub-agents for parallel work.

---

## Prompts, Commands & Configs

```
## COUNCIL ROAST
Before building, stress-test this idea.
Roles: contrarian, buyer, market researcher, first-principles thinker, judge.
Deliver: Verdict (green light/reshape/kill) · Strongest failure reason ·
Strongest upside · Riskiest assumption · Cheapest 48-hour test

## VERIFY — definition of done
Build the feature, then verify before reporting done.
Start the local app. Capture evidence (screenshots desktop + mobile, form tests).
Report: Files changed · Commands run · Screenshots · Tests passed/failed ·
Known limitations · What a human should review next

## SESSION HANDOFF
Create a handoff doc for a fresh Claude Code thread.
Include: goal, locked decisions, current files, commands run,
verification completed, open risks, deferred work, exact first prompt to continue.

## PARALLEL SUB-AGENTS
Use parallel sub-agents, one per deliverable.
Each agent writes to a separate file.
Goal object: what "done" looks like, measurably.
After all finish: verification pass across every file.
```

---

## Gotchas & Watch-Outs

- **Verify can become theater:** Screenshots ≠ correctness. Human review gate mandatory for security/payments/production. (@contra-flux: "Claude definitely falls short" on council-style internal challenges.)
- **Multi-model councils work better:** @AlexKucera (12 likes) — run the roast across 4–8 different models to reduce echo chamber. Needs a plan/routing layer.
- **Third-party skills need review:** Read before installing. Understand tool calls and permission scope.
- **Parallel agents burn tokens:** Only worth it for genuinely independent tasks with reconcilable outputs.
- **Handoff can omit context:** Source files and logs stay on disk — treat them as ground truth, not the handoff doc.

---

## In His Words

> "I figured out how to turn Claude Code into the best business partner I could ask for. And I made three times more money in the past 30 days." — 00:00

> "It is not tuned to make you money. And these are two completely different things. And every one of those design errors is costing you money because your income is basically capped by two things. The first one is the quality of your output. And the second one is how fast you can produce it." — 01:03

_Source: YouTube auto-captions indexed by Tavily; Firecrawl transcript panel extraction was rate-limited this run._

---

## Steal This For Your Org

1. Replace vague team consensus polls with a Council roast before any AI build.
2. Write the "done" definition (verification checklist) before work begins — hand it to Claude as acceptance criteria.
3. Run a session handoff on your longest-running AI project this week; restart clean; measure quality.
4. Map one project to a sub-agent split (3+ independent deliverables) and compare to your sequential baseline.

---

## Mistake to Avoid

Optimising for feeling productive instead of being profitable. The moment a build feels effortless is exactly when Council, Verify, and Handoff earn their keep.

---

## Source & Chapters

- **URL:** https://www.youtube.com/watch?v=iTY8Q449YNQ
- **Duration:** 28:13 · **Views:** 70,005 · **Likes:** 2,116
- 00:00 Tripled My Income · 00:36 Habits Costing You · 01:03 Productive Or Profitable? · 01:53 Claude's Yes Man · 02:19 Is It Honest? · 02:49 Meet The Council · 03:55 Will Anyone Buy? · 05:35 Reshape Or Kill? · 07:55 Finished Or Working? · 08:33 When Claude Lies · 10:23 Build, Then Verify · 14:19 Try Breaking It · 16:47 Why Claude Slows · 18:27 Reset Without Losing? · 21:16 Stop The Bottleneck
- **Linked resources:** [Skills & Prompts Folder (Google Drive)](https://drive.google.com/drive/folders/1eCOxxiFSMz49UONwPlbOfDnkHj9QzDg5)
