---
title: "Strategic Discovery vs Execution"
type: concept
created: 2026-07-17
updated: 2026-07-17
introduced_by: "[[nate-b-jones]]"
first_seen: "[[2026-07-17-nate-b-jones-daily]]"
tags: [ai-agents, strategy, mental-model, automation, strategic-discovery]
---

# Strategic Discovery vs Execution

A framework introduced by [[nate-b-jones]] in [[2026-07-17-nate-b-jones-daily]] to distinguish two fundamentally different operating modes for AI agents.

## The Distinction

**Strategic Discovery:** An agent reasons about context to identify *what problem deserves solving*. It inspects a domain, evaluates competing priorities, and surfaces high-leverage opportunities — before any task is defined.

**Execution:** An agent receives a well-defined task and delivers against it. Performance is measured on speed, completeness, and quality of output for the pre-specified problem.

## Why It Matters

Most AI workflows assume execution: a human defines the problem, the agent solves it. Nate's experiment reveals that capable models can now operate in strategic-discovery mode — inspecting a business and recommending what deserves automating before the human has decided.

This shifts model routing upstream: you now need to choose the right agent *before* you know the task, based on which model is better at surfacing the problem worth solving.

## "Big Model Smell"

Nate's informal signal (at video timestamp 03:10) for recognizing strategic-discovery behavior in practice: the model is reasoning about context — prioritizing, evaluating consequences, identifying leverage — rather than just executing instructions. It "smells" like a large, capable model reasoning strategically rather than pattern-matching to a task spec.

## Design Implication: The Stop-and-Propose Checkpoint

Nate's rebuilt automation-discovery skill deliberately stops after the discovery phase. The agent returns up to five evidenced offers; a human selects before any build begins. This prevents the agent's problem-framing from making its own choice feel inevitable.

## First Appearance

[[2026-07-17-nate-b-jones-daily]] — Nate B. Jones, 2026-07-17  
Chapter reference: 06:20 "Strategic discovery versus execution"
