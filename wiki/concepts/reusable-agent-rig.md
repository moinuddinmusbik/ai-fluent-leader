---
title: "Reusable Agent Rig"
type: concept
created: 2026-07-30
updated: 2026-07-30
tags: [ai-agents, framework, systems-thinking, automation, document-processing]
sources: [2026-07-30-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Reusable Agent Rig

A 9-stage AI agent architecture introduced by [[nate-b-jones]] (Substack: July 3, 2026; promoted via YouTube Short July 30, 2026) for building document-processing agents that get cheaper with every additional use case.

## Definition

A single agent architecture you assemble once on a low-stakes problem, then point at any domain where you have sensitive, unorganized documents and a high-stakes decision. Between builds, only the "nouns" change (what goes into the context pack, what the output packet looks like). The nine execution stages transfer verbatim.

## Core Principle: The Flywheel

"Every agent you build should make your next agent cheaper to build." If each new agent feels like starting from zero, you are collecting AI chores — not building a system. The rig inverts this: each component gets sharper with use, and by the third build, setup costs a fraction of the first.

## The Nine Stages (from preview; full stages paywalled)

1. **Ingestion** — converts unstructured documents into text with source links
2. **Normalization** — types the data (dates, names, amounts)
3. **Context Pack** — defines scope: what the agent is allowed to read
4. [Stages 4–8 per Substack; full post paid]
5. **Receipt** — audit log of what the agent read, concluded, flagged
6. **The Hard Stop (Gate)** — the agent drafts and organizes only; never sends, files, submits, pays, or signs

## The Three Build Sequence

| Build | Problem | Agent |
|-------|---------|-------|
| 1 (training run) | Email / calendar | Generic task agent |
| 2 | Insurance denial | Healthcare Claim Appeals Agent |
| 3 | Tax-year prep | Tax Prep Organizer Agent |

## Underlying Open Skills

- **Context Engineering** — scope definition and ingestion
- **Runbooks** — step-by-step execution logic

Both skills transfer across all builds.

## When to Apply

Nate's test: "Anywhere life hands you sensitive documents, no structure, and a decision that matters."
- Insurance denials, tax prep, compliance reviews, vendor contract analysis, audit prep, grant applications
- Any domain where the opposing party (insurer, regulator, lender) operates with automation and structure, while you have a pile

## Key Distinction

The Hard Stop (Gate) — the agent never sends, files, submits, pays, or signs — is the reason the rig can safely address health and financial decisions. This is a design principle, not a legal disclaimer.

## Sources

- [[2026-07-30-nate-b-jones-daily]] — introduced (FRAMEWORK lens; Short-only day; primary source is Substack preview)
