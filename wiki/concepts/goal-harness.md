---
title: "Goal Harness"
type: concept
created: 2026-07-04
updated: 2026-07-04
introduced_by: "[[nate-b-jones]]"
first_seen: "[[2026-07-04-nate-b-jones-daily]]"
related: ["[[ai-harness]]", "[[job-first-routing]]", "[[whole-job-spec]]"]
tags: [framework, ai-strategy, routing]
---

# Goal Harness

A **goal harness** is the objective structure that a frontier model (in Nate's framing, Fable 5) defines to steer whatever cheaper or specialized model handles actual execution. It is not a task list or a project brief. It is the set of steering goals that constrain and guide downstream models or agents.

## Core Distinction

| Layer | Who does it | What it is |
|-------|-------------|------------|
| Goal harness | Frontier model (Fable 5) | Objective structure, steering constraints, decision criteria |
| Execution | Specialist / workhorse model | Coding, writing, data processing, etc. |

Introduced by [[nate-b-jones]] in [[2026-07-04-nate-b-jones-daily]].

## Why It Matters

When you separate the goal-definition layer from the execution layer, you:
1. Apply frontier horsepower only where it is irreplaceable (novel, judgment-heavy goal definition)
2. Route execution to cheaper, faster, specialized models
3. Make the whole system more robust to model-availability disruptions

## Related Concepts

- [[ai-harness]] — the surrounding system (prompts, memory, routing) that makes a model productive; goal harness is the goal-specific variant
- [[job-first-routing]] — the broader routing framework; goal harness is the frontier-tier role within that framework
- [[whole-job-spec]] — nine-field framework for delegating a whole job; the goal harness defines the "goal" field at system level
- [[fable-style-problem]] — the class of problems (novel, judgment-heavy, unclear shape) that warrant goal-harness work
