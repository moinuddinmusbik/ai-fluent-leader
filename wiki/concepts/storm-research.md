---
title: "Storm Research"
type: concept
created: 2026-06-29
updated: 2026-06-29
tags: [research, claude-skills, sub-agents, methodology]
---

# Storm Research

A research methodology, ported by [[nate-herk]] into a free Claude Code skill, based on Stanford's STORM method — peer-reviewed to produce articles 25% more organized than single-prompt research.

## How it works

1. **Scope:** if the topic is too vague, the skill asks clarifying questions first.
2. **Five lenses, in parallel:** practitioner, academic, skeptic, economist, and historian sub-agents independently research the topic (default model: Opus 4.8, swappable to Haiku/Sonnet).
3. **Contradiction map:** the main session compares the five outputs to flag disagreements and rate evidence strength.
4. **Synthesis:** findings are written into a fixed `report-template.html` — a 60-second summary plus key findings ranked by reliability.
5. **Adversarial peer review:** six more agents verify every citation/stat against its primary source; each is marked confirmed, corrected, or demoted in a V2 report.

Roughly a dozen agents total (5 lenses + up to 6 verifiers), deliberately capped to avoid the rate-limit problems Nate hit running Claude Code's native Deep Research (103 agents on one prompt).

## Sub-agents vs. agent teams

Storm's five lenses are [[claude-code-skills|sub-agents]] — they report only to the main session and cannot talk to each other. This is cheaper than an "agent team" architecture where the lenses would debate one another, but it also means disagreements are resolved by the main session's contradiction map rather than live agent negotiation.

## Distribution

Free — skill.md + report-template.html, via Nate's Skool community (Classroom → All YouTube Resources). Built for Claude (`.claude` folder) but reported portable to Codex with auto-adapted wording (per community comment, untested by the routine).

## Linked pages

- [[2026-06-29-nate-herk-daily]] — introduced this concept
