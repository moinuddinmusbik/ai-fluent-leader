# Nate Herk Daily Implementation Playbook — 2026-06-19

**Video:** [Finally. Agent Loops Clearly Explained.](https://www.youtube.com/watch?v=EuzYhzB0vbI) · 14:34 · DEEP-DIVE
**Stack:** Claude Code, /loop, three.js, Thumbnail Scoring Loop

## What It Is
- Loop engineering, demystified: Nate opens by noting most advice about agent loops "assumes you are a hardcore coder running fleets of agents around the clock" — this video is for everyone else.
- Core mechanic: an agent loop is reason -> act -> observe -> repeat. The verification step matters more than the loop's architecture.
- "Done" criteria: the throughline is teaching the agent a checkable condition for "finished," not looping blind.

## How It Works
- Reason, Act, Observe, Repeat (2:23) — a commenter independently IDs this as the classic ReAct framework.
- Three ways to build loops (5:29) — three concrete patterns, not one abstract architecture.
- Real demos (6:13–9:08): thumbnail-scoring loop, three.js plane build, Abbey Road recreation — three different "done" checks for three kinds of output.
- What makes a loop work (10:42) — loops exist to get closer on the first try, not to brute-force perfection.

## The Verdict
Loop engineering isn't reserved for people running five agents in parallel — the value is in defining a checkable "done" condition, not scale. "If you have been feeling behind because you are not running five agents at once, this one is for you."

## When To Use It (and When Not)
1. Use it — when output has an objective, agent-checkable quality bar (score, visual match, pass/fail build).
2. Skip it — "Does This Apply to You?" (12:40) directly addresses when single-shot prompting is enough.

## Set It Up
1. Pick one of his three loop patterns (5:29) rather than designing a bespoke architecture.
2. Define your "done" check first (score / visual-functional render / match-to-reference, per the three demos).
3. Run reason -> act -> observe -> repeat against that check until it passes.
4. Treat the first pass as a draft — the loop's job is getting closer on try one, not perfection in one shot.

*Note: transcript panel could not be captured — steps reconstructed from chapters/description, not verbatim.*

## Prompts, Commands & Configs
No verbatim prompts or commands shown in the description or chapter list. A top comment references a "/loop" slash command by name, but Nate does not publish its contents in the video description.

## Gotchas & Watch-Outs
- No before/after comparison (@carlin.unscripted): wants a loop vs. no-loop comparison.
- Light on practical cases (@AlexandreAlvesKribou).
- It's a known pattern under another name (@Wheretheheckisjason): this is the ReAct framework.
- Cleanup unanswered (@bradymcmanama1684): does Nate delete failed loop iterations afterward?

## Steal This For Your Org
1. Write a "done" check before you delegate any AI-agent task.
2. Stop measuring AI maturity by agent count — one well-verified loop is a legitimate starting point.
3. Borrow the ReAct framing when training technical staff.
4. Pressure-test with a control: run the task with and without the loop before rolling out org-wide.

## Mistake to Avoid
Don't assume loop engineering requires running fleets of agents around the clock. Don't adopt a loop pattern on faith either — without a before/after comparison you can't tell if it bought a meaningfully better result or just burned more tokens.

## Source & Resources
- Video: https://www.youtube.com/watch?v=EuzYhzB0vbI · 14:34
- Chapters: 0:00 Intro · 0:31 What Loop Engineering Means · 2:23 How an Agent Loop Works · 5:29 Three Ways to Build Loops · 6:13 Demo: Thumbnail Scoring · 8:12 Demo: Three.js Plane · 9:08 Demo: Abbey Road Recreation · 10:42 What Makes a Loop Work · 12:40 Does This Apply to You? · 14:06 Resources & Wrap-Up
- Linked: No substantive external resources beyond Nate's own Skool community/course and affiliate tool links — skipped per routine rules.
- Transcript unavailable for this video (Firecrawl could not open the transcript panel after two attempts).
