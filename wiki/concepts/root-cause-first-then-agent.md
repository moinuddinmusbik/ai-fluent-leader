---
title: "Root-Cause First, Then Agent"
type: concept
created: 2026-07-26
tags: [framework, ai-agents, process-design, operational-excellence]
related: [[nate-b-jones]], [[2026-07-26-nate-b-jones-daily]]
---

# Root-Cause First, Then Agent

A six-step framework introduced by [[nate-b-jones]] for identifying and deploying your first AI agent use case. The key reframe: agents should attack the repeating upstream failure in operational work, not just automate the cleanup.

## The Six Steps

1. Pull 50–100 recent operational cases (support, IT, finance exceptions)
2. Strip PII; group by root cause, not subject line
3. Pick the largest repeating category — boring and reversible over interesting
4. Write the process down before automating (documentation = instruction set)
5. Keep human approval on access and money only
6. Scorecard weekly by category recurrence, not closure rate

## The Core Argument

"The common story is that AI helps you answer tickets faster — but the real question is whether the ticket had to exist at all." — Nate B. Jones

## Evidence

- 39 of 52 support tickets were the same Slack-access failure (masked by 98% closure rate)
- Fixing the upstream path → 52 cases to 19 in a comparable week
- Applies across: customer support, finance, IT, sales, product

## See Also

- [[2026-07-26-nate-b-jones-daily]] — full episode briefing
- [[nate-b-jones]] — creator
