---
title: "2026-07-12 Nate Herk Daily — Claude Code + Clay Makes Lead Generation Actually Fun"
date: 2026-07-12
type: source
lane: implementation
creator: [[nate-herk]]
video_type: BUILD
video_url: https://www.youtube.com/watch?v=zyvdl__Ywfk
duration: "18:03"
stack: [Claude Code, Clay, Clay Plugin, /goal, Sub-Agents, VS Code]
tags: [lead-generation, cold-outreach, clay, claude-code, build]
transcript: [[2026-07-12-nate-herk-daily-transcript]]
---

# Claude Code + Clay Makes Lead Generation Actually Fun

**Date:** 2026-07-12 · **Duration:** 18:03 · **Type:** BUILD · **Creator:** [[nate-herk]]
**URL:** https://www.youtube.com/watch?v=zyvdl__Ywfk

---

## What He Builds

A plain-English lead generation machine: [[Claude Code]] as orchestrator, [[Clay]] as the data and enrichment layer. One `/goal` prompt → Claude spawns parallel sub-agents across geographies → Clay's waterfall enriches leads (80–90% email match vs ~30% single vendor) → personalized CSV → imported into Clay to launch the email campaign. Total cost for 50 fully enriched leads with personalized copy: ~$12 (172 Clay credits).

## Stack

- **Claude Code** — orchestrator, goal-prompt driver, sub-agent spawner, copy writer
- **Clay** — B2B data sourcing + multi-vendor waterfall enrichment
- **Clay Plugin (Marketplace)** — installed via `/marketplace` in Claude Code terminal
- **/goal (Dynamic Workflow)** — end-condition-driven agentic loop with verification passes
- **Sub-Agents** — Claude spawned 6 parallel agents (Houston, San Antonio, Atlanta, Charlotte, Tampa, Las Vegas)
- **VS Code** — terminal host for Claude Code

## Architecture

```
/goal prompt → Claude Code (orchestrator)
                    ↓
         Spawn N sub-agents by city
                    ↓
         Each agent → Clay Plugin → Clay API
                    ↓
         Clay waterfall: Provider 1 → Provider 2 → ... → hit
         (emails, phones, pain points, recent signals, achievements)
                    ↓
         Sub-agents aggregate → dedup → verification debates
                    ↓
         Claude writes personalized subject + body (from /context files)
                    ↓
         Output: CSV (no blank columns)
                    ↓
         Import into Clay → campaign builder → sender domains → launch
```

## Build It Yourself

1. **Clay account** — clay.com, free trial, grab API key.
2. **Install Clay plugin** — Claude Code terminal only: `/marketplace` → Install plugin → paste Clay marketplace URL → reload plugins.
3. **Authenticate** — Ask Claude: "I just installed this Clay plugin. Can we connect my account? Can you help me authenticate?" Copy-paste auth URL manually if terminal wraps it.
4. **Context files** — `/context/` folder: business-profile.md, case-studies.md, faqs.md, proof.md, offer.md, website-copy.md.
5. **/goal prompt** — specify avatar, enrichment fields, CTA, "do not stop until done," delivery condition (CSV, no blank columns, N records).
6. **Wait** — quick pull: ~5 min; full enrichment + verification: ~1 hour.
7. **Import CSV → Clay** — Import Data → CSV → new blank table → campaign → map subject/body variables.
8. **Sender accounts** — buy pre-warmed domains in Clay (30 sends/day cap); add follow-up sequences.

## Prompts, Commands & Configs

### Authentication
```
"I just installed this Clay plugin. Can we go ahead and connect my account? Can you help me authenticate?"
```

### Verify connection
```
"Check if you can use Clay and tell me what available actions and tools you have."
```

### /goal prompt (Nate's verbatim HVAC example, timestamp ~9:08)
```
/goal
I am looking for some leads. I want 50 enriched leads that are HVAC or home
service companies and we are looking to get in front of decision makers —
business owners, presidents, people that might be decision makers at these companies.
We want fully enriched leads: email addresses, business pain points, anything that's
recently happened in their business, any notable achievements, so that you can also
get me the subject lines and the body for the email. Everything should be super
personalized. The CTA: we want the recipient to say yes to us sending over a
90-second Loom video that explains how our business can help them. Do not stop
until you have all 50 of these leads. Use a dynamic workflow to verify that
you've done everything correctly. Deliver a CSV file — no blank columns. Every
lead should have an email, a subject line, and a body, enriched with other data.
```

### Context folder structure (prereq for personalized copy)
```
/context/business-profile.md
/context/case-studies.md
/context/faqs.md
/context/proof.md
/context/offer.md
/context/website-copy.md
```

## Gotchas & Watch-Outs

- Plugin marketplace install: terminal only (not desktop app or VS Code extension for the install step).
- Terminal URL wrapping: copy-paste auth link manually.
- "Verified" emails ≠ zero bounce rate — run through external verifier at volume. (community: @aboutsupplies)
- Cost math at scale: ~$12/50 leads → $240+/week for 1,000 contacts minimum at 1% conversion. (community: @sgladue8346)
- Clay MCP server gaps: can't manage campaigns/follow-ups/sender accounts yet — Clay UI required.
- Context files are a hard prerequisite for quality copy.

## Steal This For Your Org

1. Run a $12 proof-of-concept: one vertical, three context files, /goal prompt, evaluate CSV copy quality.
2. Build an AI context folder (business profile + case studies + CTA) once → every campaign inherits it.
3. Use `/goal` + "do not stop until done" for overnight enrichment runs.
4. Apply Clay's waterfall logic to any multi-vendor data problem in your stack.

## Mistake to Avoid

Firing the machine before context files exist. Without them Claude writes generic copy regardless of data quality.

## In His Words

> "Clay is going to fix the data problem and Claude Code is going to fix the tool problem." — [0:56]

> "Do not stop until you have all 50 of these leads for me. Use a dynamic workflow to verify that you've done everything correctly and verify that everything is accurate." — [9:08]

## Source & Resources

- **Video:** [Claude Code + Clay Makes Lead Generation Actually Fun](https://www.youtube.com/watch?v=zyvdl__Ywfk) · 18:03
- **Chapters:** 0:00 What We're Building · 0:58 The Data Problem vs The Tool Problem · 3:01 Why Clay and the Waterfall · 4:25 Setting Up Clay and the Plugin · 6:06 Connecting Your Account · 7:26 The Goal Prompt · 9:37 How It Runs and What It Cost · 11:40 The Enriched Data and Email Copy · 13:32 Launching the Campaign in Clay · 17:02 Final Thoughts
- **Linked resources:** Clay free credits — https://bit.ly/4gzSl9L · Full demo project markdown in Nate's Skool community
- **Transcript:** [[2026-07-12-nate-herk-daily-transcript]]
