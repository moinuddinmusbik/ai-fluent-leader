---
title: "Routing Tree"
type: concept
created: 2026-06-10
updated: 2026-06-10
tags: [context-architecture, ai-os, claude-fable]
---

# Routing Tree

The **Context** layer of [[nate-herk]]'s [[ai-operating-system]] — a hierarchical file/folder structure inside a Claude.ai Project (or CLAUDE.md) that acts as Claude's map of the user's world.

## What it does

Before Fable answers a query, the routing tree tells it *where* to look: who the user is, their domain, their goals, their communication preferences, and their decision-making patterns. The tree routes incoming queries to the right layer of knowledge before inference begins.

## Structure pattern

```
/context
  /static       ← evergreen identity: role, goals, style, decision patterns
  /live         ← current context: active projects, this week's priorities
```

## Why it matters

Without a routing tree, Claude starts every session context-blind. With one, each session opens with Fable already knowing who it's talking to and what matters — eliminating the "let me explain myself again" tax on every interaction.

## Source

Introduced / demonstrated in depth: [[2026-06-10-nate-herk-daily]] — *I Turned Claude Fable Into The Ultimate Second Brain* (4:55 chapter: "Context: Your Routing Tree")

Related: [[ai-operating-system]] · [[claude-fable-5]] · [[nate-herk]]
