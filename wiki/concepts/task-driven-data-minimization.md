---
title: "Task-Driven Data Minimization"
type: concept
created: 2026-07-24
updated: 2026-07-24
introduced_by: "[[nate-b-jones]]"
introduced_in: "[[2026-07-24-nate-b-jones-daily]]"
tags: [framework, privacy, data-minimization, shadow-ai, ai-governance]
---

# Task-Driven Data Minimization

**Introduced by [[nate-b-jones]] on 2026-07-24.**

Also called **"Begin with the Job"** — Nate's framework for operationalizing AI privacy policy at the task level rather than the file level.

## Core Claim

"Don't upload the file" is a rule, not a process. The question it leaves unanswered — *how do I finish the work?* — is where shadow AI enters. The framework answers it by reframing the privacy decision: instead of asking "what's sensitive in this file?" ask "what does this specific task need the model to see?"

## The Framework

1. **Define task output first** — what must the model produce? That output defines the required inputs.
2. **Strip to the task** — remove only what the task doesn't need. Airlock (Nate's on-device Mac app) does this mechanically: it identifies protected terms, strips them, and rebuilds a clean file on-device.
3. **Rebuild, don't redact** — redaction leaves visible gaps that can be reverse-engineered. Rebuilding removes the inference-enabling structure entirely.
4. **Route the clean copy by residual risk** — on-device for highest sensitivity; private enterprise API for moderate; frontier public API only when residual data is genuinely low-risk.
5. **Human gates the output** — sanitization handles the mechanical stripping; human judgment holds the final review before anything moves externally.

## The Two-Minute Test

Put the organization's approved AI path on a clock against the consumer route for one common sensitive-file task. The time difference predicts what employees under deadline pressure will actually use. If the gap is large, shadow AI is the default by design, not defiance.

## Why It Matters

The "two-mandate dynamic": managers demand AI productivity gains (immediate, personal incentive) while IT bans the tools that deliver them (abstract, delayed, shared consequence). Employees carry the conflict and are judged on the result. Task-driven data minimization turns a policy compliance problem into a task architecture problem — one that can be engineered rather than remembered.

## Contrarian Stance

No single "clean copy" of a document can be a permission slip for every future task — relevance is task-dependent. This means blanket anonymization templates miss the point: you need decision rules per workflow, not one universal scrubbed version.

## Related Concepts

- [[shadow-ai]] — the behavior this framework is designed to reduce
- [[airlock]] — Nate's on-device implementation of task-driven stripping

## Linked Sources

- [[2026-07-24-nate-b-jones-daily]] — introduced here (FRAMEWORK, 2026-07-24)
