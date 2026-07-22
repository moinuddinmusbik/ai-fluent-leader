---
title: "Reusable Agent Rig"
type: concept
created: 2026-07-21
updated: 2026-07-21
tags: [framework, ai-agents, automation, governance]
introduced_by: "[[nate-b-jones]]"
first_seen: "[[2026-07-21-nate-b-jones-daily]]"
---

# Reusable Agent Rig

A 9-stage AI agent architecture designed for high-stakes, document-heavy paperwork tasks. Built once, pointed at many jobs — only the context pack and output template change between builds. Introduced by [[nate-b-jones]] in his 2026-07-21 Substack post.

## The Core Principle

"Every agent you build should make your next agent cheaper to build." If that ratio is not improving, you are collecting chores that happen to run on AI, not building a system.

## The Pattern

**Stage shape:** Define what the agent is allowed to read → structure and cite the documents → export a reviewable packet → hard stop (hand back to human).

**The hard stop rule:** The agent drafts and organizes only. It never sends, files, submits, pays, or signs. This is not a limitation — it is what makes the rig deployable on money and health decisions.

**Deliberate no-vector-search:** For legal and health documents, the rig uses deterministic retrieval, not vector/RAG similarity search. Exact policy clause citation matters more than approximate relevance.

## Two Transferable Open Skills

1. **Context Engineering Open Skill** — controls what the agent reads and how it scopes the context pack
2. **Runbooks Open Skill** — step-by-step operating procedure that persists across builds

## Three Proof-Run Builds (Nate's sequence)

1. **Email & calendar** — training run, low stakes, validates the nine stages
2. **Insurance denial appeal packet** — high asymmetry problem; assembles cited appeal with exact policy references; stops before submitting
3. **Tax-year prep packet** — same rig, different context pack and output template; setup is a fraction of Build 1 by this point

## The Flywheel

The rig is explicitly designed to compound: between builds, only the "nouns" change (context pack + output template). The machinery transfers. By the third build, setup cost is dramatically lower than the first.

## Where It Applies

Any domain with: sensitive/unorganized documents + a decision that matters + the other side already has structure. Insurance, taxes, contract review, compliance audit, HR investigations, grant reporting.

## Related pages

- [[nate-b-jones]]
- [[2026-07-21-nate-b-jones-daily]]
