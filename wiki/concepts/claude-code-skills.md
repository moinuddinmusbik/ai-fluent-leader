---
title: "claude-code-skills"
type: concept
created: 2026-06-03
updated: 2026-06-03
tags: [claude-code, implementation, automation]
---

# Claude Code Skills

Custom slash commands stored in `.claude/commands/` that turn any repeatable Claude Code workflow into a single-command operation. Nate Herk ranked Skills as the **#1 most impactful Claude Code feature** for knowledge workers and automation practitioners.

## What they are

A Skill is a markdown file in `.claude/commands/<name>.md` containing a prompt/instruction set. Once created, it is invokable as `/<name>` inside a Claude Code session. The effect: Claude behaves like a trained specialist for that specific workflow every time.

## Why it's #1

- **Compression:** A workflow that took multiple back-and-forth turns becomes a single command.
- **Consistency:** The same instructions run identically every time — no prompt drift.
- **Compounding:** Each Skill you build makes subsequent ones faster to write and more powerful to combine.
- **Specialization:** Makes Claude Code act like a domain expert for your specific work, not a generalist.

## Implementation pattern

1. Identify a task you repeat more than once a week.
2. Write a `.claude/commands/<task-name>.md` with clear instructions.
3. Run it 3× to verify it matches your expected output.
4. Build a second Skill that calls the first (chaining).

## Linked pages

- [[2026-06-03-nate-herk-daily]] — Source: Nate Herk's tier-list video ranking Skills #1