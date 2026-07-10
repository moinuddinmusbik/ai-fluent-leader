---
title: "Nate Herk Daily Implementation Playbook — 2026-07-09"
date: 2026-07-09
source: nate-herk-daily
type: email-archive
---

# Nate Herk Daily Implementation Playbook — 2026-07-09

**Video:** Fable 5 Just Built Me a Business With One Prompt  
**URL:** https://www.youtube.com/watch?v=R0qF17BVl9w  
**Duration:** 12:28  
**Type:** BUILD

---

## What He Builds

- **The experiment:** A single "goal prompt" given to Claude Fable 5, directing it to build a complete company from scratch — starting with nothing but the open internet and whatever API keys were already in Nate's .env file.
- **The output — Counterbrief:** A $19/response SaaS for Shopify store owners fighting chargebacks. Deliverables: working product dashboard, landing page, two launch videos (viral-style + voiceover), a founder avatar video (ElevenLabs clone + Hen avatar), brand guidelines, logo, business plan, and market research — all in ~3–4 hours.
- **The orchestration:** Fable spun up hundreds of Opus and Sonnet subagents across nine phases: Pain Hunt → Tournament → Research/Design → Brand Build → Product Build → Launch Video → Founder Video → Red Team → Package. Fable itself only planned, delegated, and reviewed — ~500K tokens + ~30–40% of the 5-hour compute limit on the $200/month Max plan.
- **Red-team result:** Six skeptic agents attacked market size, moats, and unit economics. Verdict: viable with fixes. Zero kills, 38 attacks ruled on, every fix applied.

## How It Works (Architecture)

- **Fable as manager, Opus/Sonnet as workers:** Fable 5 orchestrates only — plans phases, delegates to Opus/Sonnet workers, reviews results, loops back if quality fails. This is what kept Fable token spend low (~15% of weekly Fable budget).
- **Nine-phase arc:** (1) Pain Hunt — 10 research agents, 35 raw problems → 18 candidates, independently reverified. (2) Tournament — 5 judge personas score 18 options; chargeback evidence wins 3-0. (3) Research/Design — competitor pricing, platform docs, Visa rule PDFs. (4) Brand — logo through 6 AI generations + critique loop. (5) Build — product dashboard, offer, pricing. (6–7) Videos. (8) Red Team — 6 skeptic agents. (9) Package — recap HTML.
- **Orchestration patterns:** parallel fan-out researchers, judge tournament panels, adversarial skeptic agents, completeness critic before each phase close.
- **Infrastructure dependency:** Fable used pre-existing API keys (.env), ElevenLabs voice clone, and Hen avatar — these must exist before any autonomous run.

## Build It Yourself

1. **Pre-configure your .env** — Populate with API keys, voice clone credentials (ElevenLabs), avatar tool access.
2. **Write your goal file** — Create a markdown file with mission, guardrails (no new spending, publish nothing, verify every fact, never ask mid-run), orchestration definition, arc, and definition of done.
3. **Write the short /goal prompt** — Reference the file: "Read this file and execute everything below the divider line as your goal… Do not report back until the definition of done is met. Start now."
4. **Launch with Claude Code /goal** — Fable begins phase 1 autonomously. Expect 3–4 hours for a complex company-build.
5. **Monitor token spend** — Fable burns slowly (manager role); Opus/Sonnet workers burn compute hours. Budget for ~30–40% of your 5-hour limit on Max plan.
6. **Review the recap HTML** — Fable packages everything into a final recap. Use it to audit quality before iterating with a "run two" prompt.

## Prompts, Commands & Configs

```
// company-builder.md (goal file)

Build me a complete company from scratch.
Start with nothing but the open internet.
Find a real painful underserved problem that real people
are complaining about right now and design a business around it.
Build the product and the brand and the website and hand me a
finished package that I could take to market this month.
Then prove to me why it would work.

This is a test of how far you can go on your own.
I am not going to answer questions mid-run.
Make every call yourself. Write down why you made it and keep moving
within the guardrails below. You have total creative freedom.
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

---
// /goal prompt (short prompt referencing the file)

Read this file and execute everything below the divider line as your goal.
That file is your full instruction set — mission, guardrails, phases,
deliverables, definition of done, follow it exactly, including the
never ask rule. Do not report back to me until the definition of done
is met. Start now.
```

## Gotchas & Watch-Outs

- **"From scratch" is misleading:** Fable used pre-existing API keys, ElevenLabs voice clone, and Hen avatar. Without that infrastructure, videos and founder message can't be produced. Commenters flagged this (17+ upvotes).
- **Workers are Opus/Sonnet, not Fable:** Build quality ceiling is lower than an all-Fable run — "it would have been 100 times more expensive."
- **Cost isn't trivial:** ~500K Fable tokens + 30–40% of a 5-hour compute limit on the $200/month Max plan.
- **No revenue yet:** The business exists as a verified prototype — "viable with fixes" per the red team, but not yet in market.
- **Idea quality > build quality:** Nate's own takeaway: "What I would have put more emphasis on is the upfront idea — really stress-testing that before we build everything out."

## In His Words

> "It is the manager. It is the orchestrator that just says, 'Hey, Opus, do this, this, and this, and this. And when you're done, I'll check it. And if it's not good enough, I'm going to tell you to do it better.'" — 5:46

> "I think it's really important that we allow the model to actually be creative and we get out of its way so that it can do what it does really well." — 11:23

## Steal This For Your Org

1. **Run a pain-hunt sprint** — Assign 5–10 parallel Opus agents to sweep Reddit, HN, and G2 reviews in your industry, then run a structured tournament: 5 judge personas, scoring on pain, urgency, reachability, and willingness to pay.
2. **Write your Definition of Done before your goal prompt** — "A stranger should be able to open the recap HTML and understand the business, watch the video, run the site, and demo it." What observable state means done for your task?
3. **Add an explicit red-team phase** — Spin up 5–6 skeptic agents whose only job is to refute your product's market size, moat, and unit economics. Treat every surviving attack as a required fix.
4. **Build your .env infrastructure first** — Voice clones, avatar tools, API connections determine how far any autonomous run can go. One afternoon of setup work multiplies every future run's output ceiling.

## Mistake to Avoid

Launching an autonomous run without a written Definition of Done. Fable optimizes toward a target — an unclear finish condition means phases don't close cleanly and the package isn't ready to hand off.

## Source & Resources

- **Video:** [Fable 5 Just Built Me a Business With One Prompt](https://www.youtube.com/watch?v=R0qF17BVl9w) · 12:28
- **Chapters:** 0:00 One Prompt, A Whole Company · 1:52 The Founder Video · 3:16 The Goal Prompt · 4:42 How Fable Orchestrated It · 6:39 The Arc & Definition Of Done · 7:35 The Nine-Phase Recap · 8:59 The Deliverables · 10:28 Final Thoughts
- **Linked:** No substantive article/doc links in description (sponsor/affiliate links only)
- **Transcript:** [[2026-07-09-nate-herk-daily-transcript]]
