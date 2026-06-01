---
title: "AI Document Workflow"
type: concept
created: 2026-05-27
updated: 2026-05-27
tags: [strategy, workflow, verification, trust]
sources: [2026-05-27-nate-b-jones-daily.md]
routine: "Nate B Jones Daily Leader Briefing"
---

# AI Document Workflow

A **four-stage workflow for producing trustworthy AI-generated documents** — decks, models, reports — that wraps AI generation in a truth layer rather than treating output as a finished draft.

## The Problem

AI models are goal-directed: when sources are missing or ambiguous, they guess — and the output looks finished regardless of whether the underlying data is trustworthy. A board deck that silently blends actuals with projections is worse than no deck at all. Single-prompt generation looks like a win until the numbers are reviewed.

## The Four-Stage Workflow

1. **Sources** — Gather and scope your input documents. Clean, deduplicated, explicitly labeled (actuals vs. projections, internal vs. external). The truth layer starts here.
2. **Structure** — Build the outline or template before generating. AI fills structure; structure constrains guessing.
3. **Creation** — AI generates in passes and layers, not in one shot. Each pass has a defined scope.
4. **Verification** — Run the hostile reviewer prompt: a second AI prompt playing a skeptical senior executive that attacks the output for logical gaps, unsupported claims, and blended data.

## The Task Risk Gradient

| Risk Level | Task Type |
|------------|----------|
| Low | Formatting, structure, layout |
| Medium | Synthesis, summarization, narrative |
| High | Numerical reasoning, sourcing, compliance claims |

AI is lowest risk at formatting, highest risk at numerical reasoning. Map every delegated task against this gradient.

## The RALPH Loop

Multi-model verification workflow: Codex generates, Opus 4.7 audits. One model creates; a second attacks. The productivity upside is measurable in weeks per year when applied consistently to high-stakes documents.

## Related Concepts

- [[judgment-visibility]] — building a truth layer is a form of making reasoning visible
- [[career-evidence]] — verified documents are stronger career evidence than polished ones

## Sources

- [[2026-05-27-nate-b-jones-daily]] — primary source for this concept
