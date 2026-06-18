---
title: "Agent Maintenance"
type: concept
created: 2026-06-17
updated: 2026-06-17
tags: [ai-strategy, framework, nate-b-jones, ai-agents]
sources: [2026-06-17-nate-b-jones-daily.md]
---

# Agent Maintenance

A framework introduced by [[nate-b-jones]] for keeping [[the-harness]] around an AI agent fit for purpose after the agent ships. Where [[the-harness]] names the company layer that makes a model useful, Agent Maintenance is the operational discipline of keeping that layer healthy as the model and the business both keep moving.

## Definition

> "Agents, unlike almost anything else, break in two directions. They break because the world around them drifts. And they break because the model inside them improves."
> — Nate B. Jones, [[2026-06-17-nate-b-jones-daily]]

Most software only breaks when it gets worse. Agents are the first widely-deployed systems that can also break when the thing inside them gets *better* — a harness built for a weaker, unreliable model can become a trap (rules too strict for a now-capable model) or a liability (permissions too loose once a capable model starts acting on them at scale).

## The Seven Parts That Go Stale

- **Job** — what the agent is actually supposed to do; can drift silently as the model improves (e.g. quietly becoming a planning agent instead of a summarizing one)
- **Diet** — the sources and data it's fed; goes stale when a source moves, disappears, or becomes misleading
- **Memory** — what it remembers between runs; can hold preferences or corrections that no longer apply
- **Tools** — what it can call; the default failure mode is accumulation, not pruning
- **Reach** — what it's permitted to touch (read, draft, post, spend, publish); a permission sized for a weak model can be too broad for a strong one
- **Proof** — the linkable evidence trail (tickets, notes, quoted sources) it must produce instead of just asserting a conclusion
- **Value** — whether the output is still worth the work; whether anyone reads it, acts on it, or has to unwind it

## The Five-Question Audit

The operational version of the framework, walked through directly in the source video: for any agent, check its **diet** (are sources current?), **reach** (still right-sized for the current model?), **job** (still doing the job you assigned, on purpose?), **proof** (does it show its work?), and **value** (does the output get used?). Nate frames this as the basis of a "keep, change, pause, or retire" call on any agent before trusting it again.

## Why It Matters

> "The beginner instinct is to add. The maintenance instinct is to ask what should be removed."
> — Nate B. Jones, [[2026-06-17-nate-b-jones-daily]]

The industry default is to treat agent improvement as additive (more tools, more context, more memory, more access). Nate's central evidence against this is Vercel's sales agent, which got measurably better after deleting 80% of its tools. The deeper claim: useful agents need maintenance the way sailboats do — not because they were built badly, but because, per Stuart Brand's *The Maintenance of Everything*, they live in motion.

## Related Concepts

- [[the-harness]] — the umbrella concept; Agent Maintenance is the discipline of keeping a harness fit over time
- **The Maintenance of Everything** (Stuart Brand, Stripe Press) — the named source text; reframes agents as more like sailboats/vehicles than like static software

## Linked Pages

- [[nate-b-jones]] — introduced the framework
- [[2026-06-17-nate-b-jones-daily]] — first appearance
