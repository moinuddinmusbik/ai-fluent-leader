---
title: "Agent Analytics"
type: concept
created: 2026-05-28
updated: 2026-05-28
tags: [strategy, agents, product-analytics]
sources: [2026-05-28-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Agent Analytics

**Product analytics starting from the agent run** as the unit of product behavior — distinct from session analytics (click-based), engineering traces (mechanical), or chat logs (conversational).

## The Core Distinction

| Layer | What It Tells You | Sufficient for Agents? |
|-------|------------------|------------------------|
| Engineering traces | What happened mechanically | No — not a product question |
| Chat logs | What was said | No — not a behavior question |
| Session analytics | What was clicked | No — wrong unit of behavior |
| **Agent analytics** | Whether delegated work built trust | **Yes** |

## The Agent Run as Unit of Product Behavior

A **run** tracks:
- What the agent was asked to do (the delegation)
- What it did (the execution)
- Whether the user accepted, modified, or rejected the output (the trust signal)

This replaces the session as the meaningful unit of product behavior in AI-native products.

## Key Signals

- **Correction event:** User overrides, redoes, or rejects AI output — the highest-signal trust indicator
- **Completion-vs-acceptance gap:** How often does the agent complete a run vs. how often does the user actually use the output? A large gap is a product problem.
- **Salesforce Agent Work Units:** A naming convention model for classifying delegated work

## Minimum Viable Agent Analytics

Three events to ship first:
1. Run started
2. Correction made
3. Run accepted / rejected

## Related Concepts

- [[agent-harness]] — the broader system around an agent; analytics is one component

## Sources

- [[2026-05-28-nate-b-jones-daily]] — primary source for this concept
