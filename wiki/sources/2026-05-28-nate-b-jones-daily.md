---
title: "A Cursor Agent Wiped a Database in 9 Seconds. Agent Analytics Would Have Seen It Coming."
type: source
created: 2026-05-28
updated: 2026-05-28
tags: [strategy, agent-analytics, product-analytics, agents]
sources: [2026-05-28-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# A Cursor Agent Wiped a Database in 9 Seconds. Agent Analytics Would Have Seen It Coming.

**Routine:** [[nate-b-jones]] Daily Leader Briefing | **Date:** 2026-05-28
**YouTube:** https://www.youtube.com/watch?v=n0nC1kmztSk
**Substack:** https://natesnewsletter.substack.com/p/agent-product-analytics

## Summary

Every analytics layer built before AI agents existed was designed for click-based user behavior. When a Cursor agent wipes a database in 9 seconds, the failure appears in monitoring — but the product analytics that would have predicted the trust erosion leading to that moment were never instrumented.

Nate argues the agent run — not the session or the API call — is the correct unit of product behavior. A run tracks delegated work: what the agent was asked to do, what it did, and whether the user accepted or corrected it. The correction event and the completion-vs-acceptance gap are the highest-signal data points for agent trust, and they require purpose-built instrumentation. Salesforce’s Agent Work Units provide a naming convention model. The minimum viable agent analytics layer is three events: run started, correction made, run accepted/rejected.

## Key Takeaways

- Agent runs replace sessions as the unit of product behavior in AI-native products
- Chat logs are not product analytics; engineering traces are not product analytics
- The correction event is the highest-signal data point for agent trust
- The completion-vs-acceptance gap reveals whether agents are building or eroding trust
- Salesforce Agent Work Units: a naming model for classifying delegated work
- Three events to ship first: run started, correction made, run accepted/rejected

## Concepts Referenced

- [[agent-analytics]] — product analytics starting from the agent run

## Linked Pages

- [[nate-b-jones]] — source creator
