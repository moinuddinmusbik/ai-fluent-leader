---
title: "AI Operating System"
type: concept
created: 2026-05-29
updated: 2026-05-29
tags: [implementation, claude-code, ai-os, workflow]
sources: [2026-05-29-nate-herk-daily.md]
routine: "Nate Herk Daily Implementation Playbook"
---

# AI Operating System

A framework for running business operations through Claude Code as a primary workspace, eliminating constant context-switching between apps. Articulated by Nate Herk using the **Four C's** model.

## The Four C's

| C | Component | What it means |
|---|-----------|---------------|
| **Context** | CLAUDE.md + memory files | All business state, role, recurring decisions, output preferences stored in files Claude reads at session start |
| **Connections** | MCP servers | GitHub, Gmail, Notion, calendar, Slack wired directly into Claude Code |
| **Capabilities** | Slash commands + agents | Custom commands and agent definitions for recurring workflows |
| **Cadence** | Automated routines | Daily/weekly tasks that run without manual triggering (e.g., this wiki pipeline) |

## The Mindset Shift

From: "I open Claude when I have a task."
To: "Claude Code is my primary workspace; external apps are tabs I open only when Claude can't reach the data."

## Connections

- [[2026-05-29-nate-herk-daily]] — source
- [[opus-4-8]] — the model that powers the AI OS
- [[claude-code-dynamic-workflows]] — a capabilities layer within the AI OS
- [[nate-herk]] — creator
