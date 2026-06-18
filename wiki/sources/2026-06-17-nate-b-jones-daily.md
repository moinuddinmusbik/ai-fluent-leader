---
title: "Nate B Jones Daily — 2026-06-17"
type: source
date: 2026-06-17
creator: "[[nate-b-jones]]"
lens: FRAMEWORK
episode_url: "https://www.youtube.com/watch?v=BOXK2XFLA-E"
substack_url: "https://natesnewsletter.substack.com/p/ai-agent-maintenance?r=1z4sm5"
duration: "18:25"
tags: [nate-b-jones, strategy, ai-agents, agent-maintenance, the-harness, ai-strategy]
---

# Don't build more AI agents until you watch this

[[nate-b-jones]] · 2026-06-17 · FRAMEWORK · 18:25

> The beginner instinct is to add. The maintenance instinct is to ask what should be removed.

## The Big Idea

Maintenance, not building, is the real AI agent skill of 2026. Nate opens with a deliberately counterintuitive headline: Vercel made its sales agent better by deleting 80% of its tools — direct proof that the dominant industry instinct (give agents more context, more tools, more memory, more access) is often exactly backwards. The popular read of the Vercel story is a labor story ("AI replaced sales reps"). Nate argues the real story is what had to be true around the model for the agent to be trustworthy at all: a documented workflow lifted from one top-performing rep, defined tools, handoffs, and human review — and then the discipline to prune that setup once it started working. That setup is what he calls the harness, or the workbench, and keeping it healthy as the model changes and the world changes is, in his words, "the real agent story of 2026."

## The Framework

- **The Harness (“the workbench”):** Nate's name for everything around the model that makes it usable: what the agent reads, what it remembers, what tools it can touch, what it's allowed to change, what proof it has to bring back, and what stops it when the work gets risky. “The agent is the worker. The harness is the workbench.”
- **Two ways agents break:** Most software only breaks when it gets worse. Agents break in two directions: (1) the world around them drifts — stale wikis, changed SOPs, moved owners, redefined dashboard fields — and the agent inherits that stale truth without knowing it; (2) the model inside them improves, and a harness built for a weaker, less reliable model becomes either a trap (over-restrictive rules that block a now-capable model) or a liability (loose permissions sized for a model a human had to babysit, now acting on its own at scale).
- **The seven parts of the harness that go stale:** Per his Substack breakdown: job, diet (the sources/data it's fed), memory, tools, reach (permissions), proof (the evidence trail it must produce), and value (whether the output is still worth the work) — each failing in its own specific way as the model and the business move.
- **Beginner instinct vs. maintenance instinct:** “The beginner instinct is to add. The maintenance instinct is to ask what should be removed.” Vercel's gain came entirely from subtraction, not addition.

The umbrella concept is [[the-harness]]; the operational discipline of keeping it fit is [[agent-maintenance]].

## How It Works

- **Diet:** What's the agent eating? Are its sources current? Did the underlying workflow move? Did a source become misleading rather than just outdated?
- **Reach:** What can it actually touch — read-only, draft, create tickets, post to Slack, update records, spend money, publish? A permission that was harmless for a weak model may be far too broad for a strong one; a restriction that protected you from an unreliable model may now just be drag.
- **Job:** Is it still doing the job you assigned, or has the model quietly let it drift from summarizing into planning, or from drafting into recommending? “Do not let the job change silently. Change the job on purpose if you're going to do it at all.”
- **Proof:** Does it produce a linkable trail a human can inspect — ticket links, sales notes, quoted customer language, which sources it checked and which it couldn't access — or does it just assert a conclusion?
- **Value:** Does anyone actually read the output? Does it save time after review, or create another pile of work to unwind? Has the model improved enough that the agent should be rebuilt, or has the business changed enough that it should be retired?

## Where It Applies

- **Product leaders:** the sources the agent reads before it plans.
- **Sales:** CRM fields, call notes, routing rules, and the human-approval steps around them — the exact setup behind the Vercel story.
- **Support:** the policy store, escalation paths, and refund rules the agent is reasoning against.
- **Writers:** drafts, transcripts, voice notes, editorial rules, and an explicit instruction to show where an idea came from.
- **Engineers:** repo, tests, terminal, permissions, work trees, logs, review rules — “in many ways the most mature example of a harness we have today.”
- **The frontier labs themselves:** OpenAI and Anthropic are racing to own the harness, not just the model. Codex's surface, as Nate lists it, now spans terminal, desktop app, IDE, browser, computer use, files, plugins, memory, automations, approvals, sandboxing, network controls, keychain storage, managed configs, and logs — “way beyond a chat box with a smarter brain.”

## Receipts

- **Vercel's tool deletion:** Vercel studied one of its best sales development reps, built an agent around the actual observed workflow (not the documented one), then deleted 80% of its tools and the agent got better, not worse.
- **Ten-person team to one:** Per Business Insider (cited in Nate's Substack post), Vercel moved from a ten-person inbound sales team to one person overseeing the agent, with the rest of the team shifted into more complex outbound work.
- **Codex's expanding harness:** Terminal, desktop app, IDE, browser, computer use, files, plugins, memory, automations, approvals, sandboxing, network controls, keychain storage, managed configs, logs — named on air as evidence OpenAI is building an operating surface, not just a chatbot.
- **The Maintenance of Everything (Stuart Brand, Stripe Press):** Nate's named source text: a sailboat isn't maintained because it was badly designed, it's maintained because it lives in motion. His thesis: agents are “a lot less like apps and more like sailboats.”

## What It Means For You

1. **Run the five-question harness audit on every agent you've shipped.** Diet (are sources current?), reach (are permissions still right-sized?), job (still doing the job you assigned?), proof (does it show a linkable trail?), value (does anyone act on the output?).
2. **Default to subtraction, not addition.** Before adding another tool, integration, or memory file, ask what should be deleted first &mdash; Vercel's improvement came from removing 80% of its tools, not adding more.
3. **Re-audit every harness after a model upgrade, not just after something breaks.** A harness sized for a weaker model can quietly become a trap or a liability the moment the underlying model gets better &mdash; treat model upgrades as a maintenance trigger, not a free win.
4. **Map your own harness by role before you delegate more.** Borrow his per-role checklist (sources for product, CRM/routing for sales, policy store for support, drafts/editorial rules for writing, repo/tests/permissions for engineering) as the starting point for what your team's agent actually needs.

## Mistake to Avoid

Assuming agent failure only looks like the model getting something visibly wrong. The more dangerous failure mode in 2026 is an agent that never fails loudly at all — it just keeps confidently producing work on top of a stale wiki, an outdated SOP, or a permission level sized for an older, weaker model. “All the agent has to do is to keep working and it will start to haunt your business.”

## In His Words

> "Agents, unlike almost anything else, break in two directions. They break because the world around them drifts. And they break because the model inside them improves."
> — 17:25

> "The beginner instinct is to add. The maintenance instinct is to ask what should be removed."
> — 2:22


## Source

- **Video:** [Don't build more AI agents until you watch this](https://www.youtube.com/watch?v=BOXK2XFLA-E) · 18:25
- **Substack:** [Vercel deleted 80% of its agent's tools and the agent got better + what to delete from yours (guide inside!)](https://natesnewsletter.substack.com/p/ai-agent-maintenance?r=1z4sm5) (preview; full post paid)
- **Transcript:** [[2026-06-17-nate-b-jones-daily-transcript]]
- **Chapters:** 00:00 Vercel made its agent better by deleting 80% of its tools · 04:34 The model changes inside, the world changes around the agent · 10:18 The art of a good harness and the two teams building them · 13:30 Your harness is the setup that makes a model useful · 18:03 Why you should read The Maintenance of Everything
