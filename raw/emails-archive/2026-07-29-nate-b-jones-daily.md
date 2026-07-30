---
title: "Nate B Jones Daily Leader Briefing — 2026-07-29"
date: "2026-07-29"
lens: FRAMEWORK
type: email-archive
---

# Nate B Jones Daily Leader Briefing — 2026-07-29

**FRAMEWORK: The Clean Desk — 3-Level Token Management System**

## The Big Idea

You don't hit your AI token limits because you ask too much — you hit them because every message you send silently carries the entire conversation history along with it. Nate B. Jones calls that "reused input," and on his hardest Codex day it made up 95.73% of 3.77 billion tokens — almost none of which he actually typed. His argument: the model providers have no incentive to fix this for you, bigger context windows will make the problem worse (not better), and the only durable solution is treating your AI workspace like a physical desk that requires active discipline to keep clean. He teaches a three-level framework that he claims can 10× the effective value of any AI subscription.

## The Framework — The Clean Desk (3 Levels)

- **Level 1 — Clean Your Own Desk (9 habits, any AI):** Edit mistakes instead of retrying; batch related questions; start fresh tasks when jobs change; carry only the accepted artifact forward; request only the output format you need; search files yourself and send excerpts; convert sources to text/markdown before uploading; load only tools the current job requires; maintain a retrievable answers database.
- **Level 2 — Token Saver Skill (one-command automation for Claude Code / Codex):** Automates the tedious parts of Level 1: searches before opening large sources, sends selected passages, runs exact operations as code, saves accepted output and builds next requests from that result, keeps responses to requested length, stops pointless retry loops, suggests the lightest model for the task.
- **Level 3 — Ringer (local multi-agent intermediary):** Runs locally between your AI client and the model provider. Before any request reaches the cloud, it can: return a cached answer with zero model calls, run a fixed local recipe, select only useful passages, enforce hard packet-size limits, or abort the call. Integrates with OpenBrain for zero-call retrieval of accepted prior answers.

## How It Works

- **Why reused input compounds:** LLMs re-send full conversation history every call. By message 30, what you typed is "a tiny tiny rounding error."
- **Output tokens cost twice:** Every token the model writes becomes part of the next input — so a 5,000-token response costs 5,000 tokens to generate, then 5,000 more on each subsequent turn.
- **The skill's ceiling:** Token Saver Skill can only act once invoked — by which point conversation history, standing instructions, and tool definitions are already in the envelope. Ringer intercepts before that.
- **Context editing vs. compaction:** OpenAI supports compaction; Anthropic supports context editing. Both depend on approximate reconstructions — plan to anticipate the ceiling, not just react to it.

## Where It Applies

- Knowledge workers on consumer plans (ChatGPT, Claude.ai, Codex): Levels 1 and 2
- Teams running multi-tool setups: Rule 10 (connect only tools the job needs) — ~55K tokens saved per session
- API developers doing repeated work: prompt caching (API-layer feature only)
- Advanced users/builders: Level 3 (Ringer) for hard limits and zero-call retrieval

## Receipts

- 3.77B tokens in one Codex day; 95.73% (3.59B) was reused input he never typed — across 143 threads and 28,877 local records
- Anthropic's data: ~55,000 tokens burned in tool definitions (GitHub + Slack + Sentry + Grafana) before Claude starts any work
- Starting a fresh task was the single biggest measured change in Nate's testing across his Claude and Codex installs
- Target: 90% reduction in reported reused input without increasing mistakes, retries, or review time (Substack claim)

## The Contrarian Edge

- More AI capability = faster token burn, not more room: "the more capable the tool, the more tools you hand it, the more material it puts in, and the faster you hit the wall"
- Labs won't fix this — they profit from usage. "It is up to us."
- Prompt caching is NOT for regular knowledge workers — it's an API feature

## What It Means For You

1. **Start a new thread every time the job changes** — the single biggest measured win
2. **Install the Token Saver Skill** (one command, Substack link) for automated Level 1 enforcement
3. **Audit your reused input ratio** before optimizing — use a tracker to see where tokens actually go
4. **Disconnect tools your session doesn't need** — ~55K tokens per session on a typical multi-tool setup

## Mistake to Avoid

Waiting for bigger context windows and smarter models to make this a non-problem. More capability without desk hygiene doesn't buy more room — it accelerates how fast you fill the room you already have.

## In His Words

> "The message you typed is the tiniest part of the overall call." — 0:53

> "Output costs you twice. It costs you once when it's written very expensively and again when it becomes part of the input on the next turn — and again when there's a turn after that, and again when there's a turn after that. You keep getting billed on it." — 8:13

## Source

- **Video:** [Paste This Into Claude, Never Hit a Token Limit Again](https://www.youtube.com/watch?v=Y8vAQ1FgNbM) · 20:17
- **Substack:** [I Built The Token Saver Skill To Cut My Token Use By 90%](https://natesnewsletter.substack.com/p/reduce-ai-token-usage) (preview; full post paid)
- **Chapters:** 00:00 Running out of tokens · 04:40 Rule 1 — edit mistakes · 11:13 Token Saver Skill · 15:35 Prompt caching · 16:23 Ringer · 18:51 Keeping your desk clean
