---
title: "Reusable Agent Rig"
type: concept
created: 2026-07-03
updated: 2026-07-03
tags: [framework, agent-design, context-engineering, paperwork-automation, nate-b-jones]
sources: [2026-07-03-nate-b-jones-daily.md]
---

# Reusable Agent Rig

A framework introduced by [[nate-b-jones]] on 2026-07-03 for building one AI agent skeleton that works across multiple high-trust paperwork jobs.

## Definition

A nine-step reusable workflow skeleton — assembled once on low-stakes work (email/calendar), then pointed at any pile of sensitive documents with a real decision attached. Between jobs, only two things change: the **context pack** (what documents go in and how they are structured) and the **export template** (what the output packet looks like). The nine steps themselves are invariant.

## The One Rule

The agent drafts and organizes only. It **never sends, files, submits, pays, or signs.** This is not a risk disclaimer; it is the architectural decision that makes the rig trustworthy enough to aim at money and health. The hard stop before submission is the feature, not a limitation.

## The Nine-Step Structure

Runs from "deciding what the agent is allowed to read" through to "a hard stop that hands the work back to you." The Substack deep-dive gives the full step list (paid); the structure is visible in the chapter sequence: context pack → run plan → build → bridge to the next job → cited packet export → human gate.

## The Flywheel

Every component — context packs, export templates, runbooks — gets sharper with each build. By the third build, setup takes a fraction of the effort of the first. The ratio of setup cost to output value keeps improving because the system is being built, not just used.

## Three Proof Builds

1. **Email/Calendar** — the 101 (training run; low stakes; nothing expensive if it fails)
2. **Insurance Appeal Packet** — cited packet from denial letters; hard stop before submission
3. **Tax Prep Packet** — organized document pile for a preparer or filing decision

## Underlying Skills

- **Context Engineering Open Skill** — how information is structured before entering the agent
- **Runbooks Open Skill** — step-by-step behavioral rules; portable as SKILL.md across Claude Code, Codex, Cursor

## Where It Applies

Any situation with: sensitive documents + no existing structure + a decision that matters. Nate names insurance and taxes as proof runs, not limits. Also applies to: employee benefits disputes, vendor contract review, regulatory filing prep, grant application organization.

## The Evidence Behind It

- KFF: ~85M denied ACA marketplace claims in 2024; <1% appealed; ~1/3 internal reversals; ~half external; >80% prior authorization
- 2024 Senate Subcommittee report: algorithmic denial tools at Medicare Advantage insurers; UnitedHealthcare denial rate more than doubled in two years
- The structural insight: most denials stick because nobody appeals, not because insurers are right

## Relationship to Other Concepts

- Extends [[open-stack]] (memory/skills/engine) — the rig uses Open Skills (SKILL.md runbooks) as the portable component
- Consistent with [[agent-ownership]] framework (one named human owner at the gate)
- Consistent with [[responsible-utility]] (useful enough to act; careful enough to know whether you authorized it)
- The hard stop before sending is a concrete implementation of the [[5-part-agent-loop]] boundary stage

## Sources

- [[2026-07-03-nate-b-jones-daily]] — introduced
