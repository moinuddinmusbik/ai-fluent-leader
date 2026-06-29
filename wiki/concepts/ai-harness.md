---
title: "AI Harness"
type: concept
created: 2026-06-28
updated: 2026-06-28
tags: [ai-infrastructure, agents, model-selection, last-mile]
introduced_by: "[[2026-06-28-nate-b-jones-daily]]"
---

# AI Harness

The surrounding infrastructure system that makes an AI model productive in a specific work context. Without a harness, a capable model is, in Nate B. Jones's phrase, "a brain in a jar."

## Components

- **Prompts & system prompts** — tuned to the model's instruction-following style
- **Memory architecture** — how context is stored, retrieved, and injected
- **Tool calls** — integrations with external systems, APIs, and data sources
- **Routing logic** — decisions about which model (or tier) handles which task
- **Output validation** — checks tuned to the model's failure modes

## Why Harnesses Matter

Switching models is not switching an API call — it is rebuilding the harness. Lindy (Flo Crivello) publicly documented this: migrating from Claude to DeepSeek required rewriting their entire harness from scratch. No lift-and-shift. Every prompt, memory structure, and tool call needed to be rebuilt and retuned.

This is why **[[context-lock-in]]** is so powerful: a frontier model that supplies its own harness (e.g. Claude Tag for Slack) makes switching irrational even when a cheaper, comparably-capable open model exists.

## The Harness Talent Problem

Building harnesses requires rare, expensive AI engineering talent — understanding tool call differences between models, memory architecture design, system prompt tuning for open-source vs. frontier models. This talent currently commands any price it wants and flows to hyperscalers. Most companies cannot afford to build their own last-mile harnesses.

## Nate's Framework

> "A model can be an incredible brain in a jar. And it just isn't useful to you without a harness." — Nate B. Jones, 2026-06-28

Harness innovation is Nate's primary watchlist signal — he tracks it more closely than model benchmark releases, as he considers it the real source of AI moats.

## Related Concepts

- [[context-lock-in]] — the strategic consequence of not owning your harness
- [[center-edge-distribution]] — determines which model the harness should route to
- [[open-engine]] — Nate's model-agnostic harness foundation framework
- [[operational-velocity-moat]] — harness speed as competitive moat

## Sources

- [[2026-06-28-nate-b-jones-daily]] — core definition; GLM 5.2 / Claude Tag context
