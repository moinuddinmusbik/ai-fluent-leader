# Nate B Jones Daily Leader Briefing — 2026-05-25

**Creator:** Nate B. Jones | **Date:** 2026-05-25 | **Platforms:** YouTube · Substack
**Video:** https://www.youtube.com/watch?v=z3pbrFKVyQE
**Substack:** https://natesnewsletter.substack.com/p/ai-big-tech-industrial-business

---

## Core Message

When AI agents begin doing work at scale, not all teams accelerate — platform and data engineering teams become the bottleneck. Emma, who leads data infrastructure at OpenAI, reveals that agents accelerate app teams while platform teams absorb the blast radius: jobs that “fix themselves overnight,” adversarial-feeling agents, and inbound that multiplies faster than headcount. Leaders who instrument this asymmetry now will still be standing when the compression hits.

## What He Covers

- **App vs platform teams accelerate at different rates:** When agents run the release process, app teams ship faster while platform teams absorb the side effects.
- **Agents turn adversarial without meaning to:** A user who doesn’t know what Flink is can now trigger Flink jobs through an agent — platform teams inherit the consequences.
- **The export job that fixed itself overnight:** Real example of agents self-modifying infrastructure behavior — a warning sign, not a success story.
- **Building a private eval suite:** Lightweight evals triage inbound and survive constant model upgrades.
- **Platform agents need different primitives:** Tighter contracts and rollback semantics, not chat/function-call patterns.

## As an AI-Fluent Leader — What To Do This Week

1. **Map your AI agent architecture for asymmetric acceleration.** Identify which teams are accelerating and which are absorbing.
2. **Audit your platform team’s load for agent-driven spikes.** Ask directly what has changed in inbound over the last 90 days.
3. **Stand up a lightweight eval suite before agents scale.** Even a “janky” suite covering 3 critical agent paths saves weeks later.
4. **Establish a triage protocol for agent-generated inbound.** Without triage, everything becomes urgent.

## Mistake to Avoid

Assuming all teams benefit equally when agents go into production. Platform and infra teams absorb the blast radius long before product teams notice the bottleneck forming.

## Source

- **YouTube:** https://www.youtube.com/watch?v=z3pbrFKVyQE
- **Substack:** https://natesnewsletter.substack.com/p/ai-big-tech-industrial-business
