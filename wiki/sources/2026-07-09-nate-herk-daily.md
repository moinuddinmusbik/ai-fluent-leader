---
title: "Fable 5 Just Built Me a Business With One Prompt"
date: 2026-07-09
source_type: youtube
creator: "[[nate-herk]]"
video_url: https://www.youtube.com/watch?v=R0qF17BVl9w
video_id: R0qF17BVl9w
duration: "12:28"
views: 41658
likes: 1342
type: BUILD
lane: implementation
tags: [fable-5, multi-agent, orchestration, company-builder, goal-prompt, claude-code]
transcript: "[[2026-07-09-nate-herk-daily-transcript]]"
---

# Fable 5 Just Built Me a Business With One Prompt

**Creator:** [[nate-herk]]  
**Date:** 2026-07-09  
**URL:** https://www.youtube.com/watch?v=R0qF17BVl9w  
**Duration:** 12:28 · Views: 41,658 · Likes: 1,342  
**Type:** BUILD  

---

## Stack

- [[claude-fable-5]] — orchestrator (manager only; plans, delegates, reviews)
- [[claude-opus]] — worker subagents (actual build work)
- [[claude-sonnet]] — worker subagents (lighter tasks)
- ElevenLabs — voice clone for founder video
- Hen — avatar for founder video
- Claude Code `/goal` — interface for launching the autonomous run

---

## What He Builds

Nate gave Claude Fable 5 a single "goal prompt" directing it to build a complete company from scratch using nothing but the open internet (plus pre-existing API keys in his .env).

**Output — Counterbrief:**
- Product: SaaS dashboard for Shopify store owners fighting chargebacks — pulls real evidence (tracking, order history, emails), assembles it into a packet the owner approves. $19 flat per approved response.
- Landing page (counterbrief.com — domain checked, not purchased)
- Two launch videos: (1) viral-style synced to music, (2) voiceover product demo
- Founder avatar video using Nate's ElevenLabs voice clone and Hen avatar
- Brand guidelines, logo (6 AI generations + critique loop, then hand-vectorized)
- Business plan, market research
- Final HTML recap linking all deliverables

**Runtime:** ~3–4 hours  
**Fable tokens:** ~500,000  
**Compute usage:** ~30–40% of 5-hour compute limit on $200/month Max plan  
**Fable budget impact:** ~15% of weekly Fable budget (because workers are Opus/Sonnet)

---

## How It Works (Architecture)

### The Fable Manager Pattern

Fable 5 acts purely as orchestrator: it plans phases, delegates tasks to Opus/Sonnet workers, reviews outputs against the Definition of Done, and loops back if quality isn't met. It never does the actual build work itself. This is what keeps Fable token spend low.

### Nine-Phase Arc

1. **Pain Hunt** — 10 research agents sweep Reddit, HN, G2, App Store reviews. 35 raw problems → 18 candidates. 18 independent verifier agents refetch every key quote to confirm. All 18 survived.
2. **Tournament** — 5 judge personas score all 18 opportunities (pain, urgency, reachability, willingness to pay, buildability, incumbent weakness). Top 4 get an advocate + a skeptic each. 3 fresh judges vote. Chargeback evidence wins 3-0.
3. **Research/Design** — Competitor pricing pages, platform docs, Visa rule PDFs, API references.
4. **Brand Build** — Logo through 6 AI generations + critique loop → hand-vectorized winner. Serif = argument; Mono = evidence.
5. **Product Build** — Dashboard, offer, pricing ($19 flat, no success fees), landing page.
6. **Launch Video** — Viral-style: UI animation synced to music; screen captures from the product.
7. **Founder Video** — ElevenLabs voice clone + Hen avatar; wrote the founder message from project context.
8. **Red Team** — 6 skeptic agents attack market size, competitive moat, unit economics. Zero kills; 38 attacks ruled on; every fix applied. Verdict: viable with fixes. "Honesty artifacts" documented.
9. **Package** — Final recap HTML linking all deliverables; everything in file explorer organized under brand/, research/, run-1/.

### Orchestration Patterns (from the goal file)

- Parallel fan-out: N researchers sweep different sources simultaneously
- Tournament: independent agents pitch ideas → judge panel scores → advocates + skeptics for finalists
- Adversarial verify: skeptic agents whose only job is to refute each claim
- Completeness critic: runs before any phase is declared done

---

## Build It Yourself

1. **Pre-configure .env** — API keys, ElevenLabs voice clone credentials, avatar tool access. Quality of autonomous run is bounded by what's already available.
2. **Write a goal file** (e.g., `company-builder.md`) — Include: mission, guardrails (no new spending, publish nothing, verify every fact, never ask mid-run), a definition of "ORCHESTRATE," the arc as a floor, and a concrete Definition of Done.
3. **Write the /goal prompt** (short, references the file) — "Read this file and execute everything below the divider line as your goal. Do not report back until the definition of done is met. Start now." (The /goal character limit is ~4,000; put the full instructions in the file.)
4. **Launch with Claude Code /goal** — Fable begins phase 1 autonomously. Expect 3–4 hours.
5. **Monitor budgets separately** — Fable token budget vs. compute-hour limit (workers burn the hours).
6. **Review the recap HTML** — Fable packages everything there. Iterate with a "run two" goal prompt informed by what fell short.

---

## Prompts, Commands & Configs

### The Goal File (company-builder.md)

```
Build me a complete company from scratch.
Start with nothing but the open internet.
Find a real painful underserved problem that real people
are complaining about right now and design a business around it.
Build the product and the brand and the website and hand me a
finished package that I could take to market this month.
Then prove to me why it would work.

This is a test of how far you can go on your own.
I am not going to answer questions mid-run.
Make every call yourself. Write down why you made it and keep
moving within the guardrails below. You have total creative freedom.
Do whatever you want. Surprise me. I want to see your best work,
not your safest work.

GUARDRAILS:
- No new spending. Anything in my .env is fair game.
- Publish nothing. Create everything locally.
- Invent nothing. Verify every fact, every stat.
- Work inside this project. Never ask me anything.

ORCHESTRATE means: use multi-agent workflows aggressively.
Fan out parallel researchers across different sources and angles.
Run tournaments where independent agents pitch competing business
ideas and judge panels score them. Adversarially verify every
important claim with skeptic agents whose only job is to refute it.
Use completeness critic before you call any phase done.
Design whatever orchestration shapes the work calls for.
The patterns above are a floor, not a ceiling.

ARC: hunt for pain → pick the winner → design the business →
build the brand → build the thing → make the launch video →
make the founder video → try to kill it → package it.
(This is a floor, not a ceiling.)

DEFINITION OF DONE: a stranger should be able to open the recap HTML
and understand the business, watch the video, run the site, and demo it.
```

### /goal Prompt (short, references the file)

```
Read this file and execute everything below the divider line as your goal.
That file is your full instruction set — mission, guardrails, phases,
deliverables, definition of done, follow it exactly, including the
never ask rule. Do not report back to me until the definition of done
is met. Start now.
```

---

## Gotchas & Watch-Outs

- **"From scratch" framing is misleading** — Fable had access to pre-existing .env API keys, ElevenLabs voice clone, and Hen avatar. Without that infrastructure, videos and founder message can't be produced. Top commenter (17+ upvotes): "the reason Fable was able to build what it built [is] all the plumbing already there in your setup."
- **Workers are Opus/Sonnet, not Fable** — Quality ceiling is lower than an all-Fable run. Nate: "it would have been even better if every single worker was also Fable, but it would have been 100 times more expensive."
- **Cost isn't trivial** — ~500K Fable tokens + 30–40% of a 5-hour compute limit on the $200/month Max plan.
- **No revenue yet** — Prototype only. Red team: "viable with fixes." Commenters (87+ likes): "So, how much money does this business make?"
- **Idea quality > build quality** — Nate's own takeaway: "What I would have put more emphasis on is the upfront idea… really stress-testing that before we build everything out."

---

## In His Words

> "It is the manager. It is the orchestrator that just says, 'Hey, Opus, do this, this, and this, and this. And when you're done, I'll check it. And if it's not good enough, I'm going to tell you to do it better.'" — 5:46

> "I think it's really important that we allow the model to actually be creative and we get out of its way so that it can do what it does really well." — 11:23

---

## Steal This For Your Org

1. **Run a pain-hunt sprint on your next initiative** — 5–10 parallel Opus agents sweep Reddit, HN, G2 reviews in your industry → structured tournament (5 judge personas, scoring pain + urgency + reachability + WTP). Surface validated problems, not assumed ones.
2. **Write your Definition of Done before writing any goal prompt** — "A stranger should be able to open the recap HTML and understand the business, watch the video, run the site, and demo it." Apply this to any autonomous run.
3. **Add an explicit red-team phase to your next build** — 5–6 skeptic agents, only job is to refute your product's market size, moat, and unit economics. Every surviving attack is a required fix.
4. **Build your .env infrastructure before your next big prompt** — Voice clones, avatar tools, API connections determine the output ceiling of any autonomous Fable run.

---

## Mistake to Avoid

Launching an autonomous run without a written Definition of Done. Fable optimizes toward a target — unclear finish conditions mean phases don't close cleanly and the package isn't ready to hand off.

---

## Source & Chapters

- **Video:** [Fable 5 Just Built Me a Business With One Prompt](https://www.youtube.com/watch?v=R0qF17BVl9w) · 12:28
- **0:00** One Prompt, A Whole Company
- **1:52** The Founder Video
- **3:16** The Goal Prompt
- **4:42** How Fable Orchestrated It
- **6:39** The Arc & Definition Of Done
- **7:35** The Nine-Phase Recap
- **8:59** The Deliverables
- **10:28** Final Thoughts
- **Linked:** No substantive article/doc links in description
- **Transcript:** [[2026-07-09-nate-herk-daily-transcript]]
