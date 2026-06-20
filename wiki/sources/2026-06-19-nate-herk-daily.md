---
title: "Finally. Agent Loops Clearly Explained."
type: source
created: 2026-06-19
updated: 2026-06-19
tags: [implementation, agent-loops, claude-code]
sources: [2026-06-19-nate-herk-daily.md]
routine: "Nate Herk Daily Implementation Playbook"
---

# Finally. Agent Loops Clearly Explained. (2026-06-19)

[[nate-herk]] · [Video](https://www.youtube.com/watch?v=EuzYhzB0vbI) · 14:34 · 22,426 views · **DEEP-DIVE**

> Transcript unavailable for this video — Firecrawl could not open the YouTube transcript panel after two attempts (4s/6s waits, both documented click selectors). This page is grounded in the video description, chapter list, and top comments, not exact spoken words. No quotes are fabricated.

## Stack
Claude Code · /loop · three.js · Thumbnail Scoring Loop

## What It Is
Nate's framing: most advice about agent loops assumes a hardcore coder running fleets of agents around the clock — this video targets everyone else. An [[agent-loop]] is reason -> act -> observe -> repeat. He argues the verification step matters more than the loop's architecture, and the core skill is defining a "done" criteria the agent can actually check.

## How It Works
- **Reason, Act, Observe, Repeat** (2:23) — a top commenter (@Wheretheheckisjason) independently identifies this as the established **ReAct framework** applied to agent tooling.
- **Three ways to build loops** (5:29) — three concrete patterns rather than one abstract architecture.
- **Demos** (6:13–9:08): a thumbnail-scoring loop, a three.js plane build, and an Abbey Road recreation — three different "done" checks (a score, a visual/functional render, a match-to-reference).
- **What makes a loop work** (10:42) — loops exist to get you closer on the first try, not to brute-force a perfect output.

## The Verdict
Loop engineering isn't gated by running multiple agents in parallel — the value is in the checkable "done" condition. Nate's closing point: "if you have been feeling behind because you are not running five agents at once, this one is for you."

## When To Use It (and When Not)
1. **Use it** when the output has an objective, agent-checkable quality bar.
2. **Skip it** when single-shot prompting is sufficient — addressed directly in "Does This Apply to You?" (12:40).

## Set It Up
1. Pick one of his three loop patterns (5:29) instead of designing a bespoke architecture.
2. Define your "done" check first — a score, a visual/functional render check, or a match-to-reference, depending on task type.
3. Run reason -> act -> observe -> repeat against that check until it passes.
4. Treat the first pass as a draft; the loop's purpose is getting closer on try one, not perfection in one shot.

*Steps reconstructed from chapters/description since the transcript panel did not render — directional, not verbatim instructions.*

## Prompts, Commands & Configs
No verbatim prompts or commands published in the description or chapter list. A commenter references a "/loop" slash command by name; Nate doesn't publish its contents here.

## Gotchas & Watch-Outs (from comments)
- @carlin.unscripted: wants a loop-vs-no-loop comparison — the video doesn't quantify the lift.
- @AlexandreAlvesKribou: "Finally /loop explained. I wish there were more practical cases shown."
- @Wheretheheckisjason: this is the published **ReAct framework**, not a new invention.
- @bradymcmanama1684: unanswered — does Nate clean up failed loop iterations from his "herk2" project afterward?

## Steal This For Your Org
1. Write an objective "done" check before delegating any AI-agent task.
2. Don't gate loop adoption on running multiple parallel agents — one well-verified loop on one task is a legitimate starting point.
3. Use the ReAct framing when briefing technically literate staff — it connects faster for people with ML/agent background.
4. Pressure-test with a control: run the same task with and without the loop before an org-wide rollout.

## Mistake to Avoid
Don't assume loop engineering requires running fleets of agents around the clock — that's the exact misconception the video opens to correct. Don't adopt a loop pattern on faith either: without a before/after comparison, you can't tell whether it bought a meaningfully better result or just burned more tokens.

## In His Words
Transcript unavailable for this video — no verbatim quotes captured. (See note above.)

## Source & Resources
- Video: https://www.youtube.com/watch?v=EuzYhzB0vbI · 14:34 · 22,426 views
- Chapters: 0:00 Intro · 0:31 What Loop Engineering Means · 2:23 How an Agent Loop Works · 5:29 Three Ways to Build Loops · 6:13 Demo: Thumbnail Scoring · 8:12 Demo: Three.js Plane · 9:08 Demo: Abbey Road Recreation · 10:42 What Makes a Loop Work · 12:40 Does This Apply to You? · 14:06 Resources & Wrap-Up
- Linked resources: none substantive beyond Nate's own Skool community/course and affiliate tool links (Glaido, Hostinger) — skipped per routine rules (not a report/repo/docs link).

Links: [[nate-herk]] · [[agent-loop]] · [[claude-code-workflows]]
