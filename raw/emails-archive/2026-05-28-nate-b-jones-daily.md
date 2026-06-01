# Nate B Jones Daily Leader Briefing — 2026-05-28

**Creator:** Nate B. Jones | **Date:** 2026-05-28 | **Platforms:** YouTube · Substack
**Video:** https://www.youtube.com/watch?v=n0nC1kmztSk
**Substack:** https://natesnewsletter.substack.com/p/agent-product-analytics

---

## Core Message

When a Cursor agent wipes a production database in 9 seconds, the failure appears in monitoring — but it was already too late. Product analytics for AI agents cannot start from clicks or engineering traces. It must start from the agent run — the new unit of product behavior. The correction event and the completion-vs-acceptance gap are where operator judgment lives, and they are invisible to every dashboard built before agents existed.

## What He Covers

- **Agent runs replace sessions:** A run tracks delegated work — what the agent was asked to do, what it did, whether the user accepted or corrected it.
- **Chat logs ≠ product analytics:** Chat logs tell you what was said; product analytics tell you whether the product is building trust.
- **Engineering traces ≠ product analytics:** Traces tell you what happened mechanically; the completion-vs-acceptance gap tells you whether users trusted it.
- **Salesforce Agent Work Units:** A naming convention for the unit of delegated work — a model for classifying what agents do.
- **Three events to ship first:** Run started, correction made, run accepted/rejected.

## As an AI-Fluent Leader — What To Do This Week

1. **Define what an “agent run” means for your product.** What is the start event? The end event? What counts as delegated work?
2. **Instrument the correction event.** Log when users override, redo, or reject AI output — this is your highest-signal data point.
3. **Compute your completion-vs-acceptance gap.** How often does the agent complete a run vs. how often does the user actually use the output?
4. **Review Salesforce’s Agent Work Units as a naming model.** Name what your agents do as units of work, not API calls.

## Mistake to Avoid

Treating engineering traces and chat logs as product analytics for agents. Neither answers the product question: is this agent building or eroding user trust over time?

## Source

- **YouTube:** https://www.youtube.com/watch?v=n0nC1kmztSk
- **Substack:** https://natesnewsletter.substack.com/p/agent-product-analytics
