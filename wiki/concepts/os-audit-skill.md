---
title: "OS Audit Skill"
type: concept
introduced: 2026-07-24
creator: [[nate-herk]]
tags: [ai-os, audit, claude-code, skill]
---

# OS Audit Skill

A free Claude skill built by [[nate-herk]] that audits an AI Operating System project for accuracy and structural integrity. Available in the Nate Herk Skool community and on the Hyperagent Marketplace.

## What It Checks

| Check | What It Looks For |
|-------|------------------|
| **Routing integrity** | Do all referenced paths exist? Are there misrouted entries? |
| **Index truth** | Does the index match what's actually on disk? |
| **Freshness** | Are data feeds current, drifting, frozen, retired, or on-demand? |
| **Bloat/Duplication** | Is there redundant or oversized context? |
| **Hygiene** | Naming, organization, stale refs |
| **Context placement** | Is expertise vs. situational context correctly separated? |

## How It Works

- Read-only: never modifies files, only reports
- Creates an `/audits/` folder at project root with a timestamped markdown report
- For large projects (100+ folders): fans out one sub-agent per check, merges reports
- Deliverable: a prioritized fix list awaiting approval ("Do you want me to fix A, B, C?")

## Usage

```
/os-audit
```

Run at end of week, after major data additions, or whenever answers feel stale.

## Related

- [[2026-07-24-nate-herk-daily]] — introduced in this video
- [[nate-herk]]
