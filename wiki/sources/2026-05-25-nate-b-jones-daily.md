---
title: "The Infrastructure Nightmare Nobody Is Talking About"
type: source
created: 2026-05-25
updated: 2026-05-25
tags: [strategy, infrastructure, platform-teams, agents]
sources: [2026-05-25-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# The Infrastructure Nightmare Nobody Is Talking About

**Routine:** [[nate-b-jones]] Daily Leader Briefing | **Date:** 2026-05-25
**YouTube:** https://www.youtube.com/watch?v=z3pbrFKVyQE
**Substack:** https://natesnewsletter.substack.com/p/ai-big-tech-industrial-business

## Summary

An interview with Emma, who leads data infrastructure engineering at OpenAI. When agents start doing work at scale, app teams and platform teams accelerate at completely different rates. App teams ship faster; platform teams absorb the blast radius. The asymmetry is silent — it does not announce itself until a platform team hits a wall, often in the form of agents that “fix” infrastructure problems overnight without human sign-off, or users triggering complex platform operations through agents without understanding the consequences (Polanyi’s paradox at the system level).

Emma’s team responded by building a private eval suite to triage inbound and survive constant model upgrades. The practical insight is that platform agents need different primitives than app agents — tighter contracts, explicit rollback semantics, and instrumentation designed for infrastructure behavior, not user-facing chat.

## Key Takeaways

- App and platform teams accelerate at different rates when agents scale — the asymmetry compounds silently
- Agents can turn adversarial without intent when users delegate work they don’t understand
- Platform agents need different primitives: tighter contracts and rollback semantics
- A lightweight “janky” eval suite covering critical paths saves weeks of incident response
- Triage protocols for agent-generated inbound are essential before agents scale

## Linked Pages

- [[nate-b-jones]] — source creator
- [[ai-supply-chain]] — related infrastructure theme
