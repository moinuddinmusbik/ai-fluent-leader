---
title: "Model Fit"
type: concept
created: 2026-07-13
updated: 2026-07-13
tags: [model-selection, ai-strategy, work-pattern, framework, nate-b-jones]
sources: [2026-07-13-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# Model Fit

A diagnostic concept and free tool (modelfit.natebjones.com) introduced by [[nate-b-jones]] on 2026-07-13. The core claim: **the right AI model is not the highest-ranked model — it is the model that fits how you actually work**.

## Definition

Model Fit is the alignment between:
1. **Your work pattern** — how you construct prompts, at what stage of task clarity you engage the model, and how you steer through correction vs. delegation
2. **Your task ambiguity profile** — whether the important part of your job is already articulate (→ execution model) or still emerging between your intent and your words (→ intent-inference model)

The fit determines which model you will produce better work with, regardless of which model scores higher on shared benchmarks.

## The Two Model Families (as of 2026-07)

| Family | Representative Model | Strengths | Best For |
|--------|---------------------|-----------|----------|
| Execution/RL family | GPT-5.6 Sol (OpenAI) | Takes full instruction seriously, keeps going, integrates with pre-built tools and skills | Long technical prompts, edges-known tasks, steer-by-correction work patterns |
| Intent-inference/pre-train family | Fable 5 (Anthropic) | Finds what you meant before you've said it cleanly; excels at ambiguity and incomplete intent | Tasks where the important part is still between intent and words; architectural thinking |

## The Diagnostic

The Model Fit tool at modelfit.natebjones.com:
1. Asks you how you work (not your job title — your actual prompting and steering behavior)
2. Returns a model mix recommendation
3. Provides "think bigger" prompts calibrated to the mix
4. Prescribes a **two-week calibration window** — a concrete falsifiability signal, not a one-time quiz

## Key Insight

Nate's own case: Fable beats Sol on his Dingo benchmark suite, yet he opens Sol every morning. The reason is work-pattern fit, not capability ranking. His prompting style (long, technical, edges-known, steer-by-correction) is a Sol pattern. He routes to Fable when a task is still architecturally ambiguous.

## Temporal Argument

As models improve, the reasons different people pick different ones will **drift further apart**, not converge. The leaderboard becomes less useful as a selection tool over time. Model Fit becomes more important as model families specialize.

## Related Concepts

- [[job-first-routing]] — prior related work (2026-07-02): three-tier routing model (Daily Driver / Cheap Workhorse / Frontier); Model Fit extends this by adding the work-pattern axis
- [[2026-07-13-nate-b-jones-daily]] — source episode

## Sources

- Introduced: [[2026-07-13-nate-b-jones-daily]]
- Tool: https://modelfit.natebjones.com/
- Substack: https://natesnewsletter.substack.com/p/pick-ai-model-how-you-work
