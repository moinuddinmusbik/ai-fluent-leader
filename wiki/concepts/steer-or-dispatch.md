---
title: "Steer or Dispatch"
type: concept
created: 2026-06-10
updated: 2026-06-10
tags: [framework, agent-management, claude-code, codex, decision-making]
sources: [2026-06-10-nate-b-jones-daily.md]
---

# Steer or Dispatch

A [[nate-b-jones]] framework for deciding how to manage AI agent work, introduced in his 2026-06-10 episode on Claude Code vs. Codex.

## Definition

Two fundamental modes of working with AI agents:

**Steer** — Stay close to the work. Converse through it in real time. Correct, redirect, and adjust as the agent runs. Appropriate when the *shape of the problem itself* is the hard part: ambiguity, taste, design judgment, writing, architecture.

**Dispatch** — Write a bounded assignment. Define the goal, the sources, the tools, and what "done" means. Stand back. Demand proof when the agent returns. Appropriate when the work can be articulated clearly, sources and files are known, and the output is checkable.

## The Interface Connection

Nate argues each major coding agent tool trains one of these habits:
- **Claude Code** → trains the *steer* habit (cockpit metaphor)
- **Codex** → trains the *dispatch* habit (operations desk metaphor)

The key insight: interfaces train behavior, not just features. Just as Mac vs. Windows taught people what a computer was *for*, Claude and Codex are teaching people what an *agent* is for.

## Decision Rule

| Use | When |
|-----|------|
| Claude (steer) | Shape of the question is the hard part; taste/ambiguity/judgment; need conversation before assignment |
| Codex (dispatch) | Task can be written as a bounded assignment; sources/files/tools known; proof checkable; parallelism needed |
| Both | Stakes are high: one plans, other critiques; one implements, other reviews |

## Failure Modes

- **Steer failure** = Conversation theater: a great conversation makes you feel closer to the work than you are
- **Dispatch failure** = Completion theater: a completed run makes the work feel more done than it really is

## Related Concepts

- [[agent-literacy]] — the meta-skill that steer-or-dispatch is a component of
- [[agent-loop-management]] — what Nate calls the actual practice (beyond "prompting")

## Sources

- [[2026-06-10-nate-b-jones-daily]] — introduced in this episode
