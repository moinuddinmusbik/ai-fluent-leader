---
title: "Loop of Loops"
type: concept
created: 2026-06-24
updated: 2026-06-24
tags: [framework, ai-agents, automation, cognitive-load, strategy]
sources: [2026-06-24-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Loop of Loops

A three-tier framework for AI agent work introduced by [[nate-b-jones]] in his 2026-06-24 episode "I Stopped Prompting AI One Task At A Time. This Works Better."

## Definition

A **loop of loops** is a set of narrow recurring jobs, each with memory, defined data sources (diet), safe actions, and explicit stop conditions (boundaries), where individual loops are allowed to notice when a change in one domain should trigger work in another.

## The Three Tiers

| Tier | What It Is | What It Carries |
|------|-----------|----------------|
| **Prompt** | One-time ask | Nothing — you carry context every time |
| **Loop** | Recurring job | Memory of what changed, diet of data sources, clear stop conditions |
| **Loop of Loops** | Control layer | Cross-domain dependencies — loops notify each other |

## The Core Diagnosis

The **app era** made individual tasks easy to reach while creating a new cognitive burden: the wiring between tasks. Each app optimized its own surface; no app carried the integration layer. Humans became the integration layer by default. A loop of loops moves that burden from human memory into the system.

## Well-Formed Loop Components

- **Job:** The recurring obligation the loop carries
- **Diet:** The data sources it reads (email, calendar, Slack, API feeds, etc.)
- **Boundaries:** What actions it can take without asking vs. where it must stop and surface a decision
- **Review:** How often the human checks and adjusts loop output

## The Five Questions Test

Nate's diagnostic questionnaire (from the Substack) structures any recurring task into a properly bounded loop by answering: what does it monitor? what changed? what can it not touch? where does it stop? who reviews it?

## Design Principles

- Start with **draft-and-stop** for consequential outputs; reserve autonomous action for genuinely reversible, low-stakes tasks
- Build **single loops** first; cross-loop dependencies reveal themselves through use rather than up-front design
- Stop conditions are the **primary safety mechanism** — a loop without boundaries is a liability, not an assistant
- The household baseline (kids' clothes, grocery inventory) is the recommended training ground before applying the pattern to professional high-stakes work

## Contrarian Position

Nate explicitly rejects the "one giant agent" narrative. The loop-of-loops is not autonomy maximalism — it is constrained, incremental, trust-building automation. The goal is not to let AI run your life; it is to stop being the person who remembers how all the recurring pieces fit together.

## Sources

- [[2026-06-24-nate-b-jones-daily]] — framework introduction
- Substack: https://natesnewsletter.substack.com/p/ai-loop-managers (preview; full post paid)
