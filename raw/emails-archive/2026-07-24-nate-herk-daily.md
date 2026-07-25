---
title: "Nate Herk Daily Implementation Playbook — 2026-07-24"
date: 2026-07-24
type: email-archive
routine: nate-herk-daily
lane: implementation
video_id: Ek1NBfnnTH0
video_url: https://www.youtube.com/watch?v=Ek1NBfnnTH0
video_type: DEEP-DIVE
duration: 25:04
---

# Nate Herk Daily Implementation Playbook — 2026-07-24

**Video:** [5 Hacks to Instantly Level Up Your AI OS](https://www.youtube.com/watch?v=Ek1NBfnnTH0) · 25:04  
**Type:** DEEP-DIVE  
**Stack:** Claude Code · Opus 4.8 · CLAUDE.md · OS Audit Skill (free) · GitHub · Hyperagent

---

## What It Is

- **The problem he's solving:** As you add more data to your AI OS every week, accuracy degrades — the agent hallucinates, misroutes, and surfaces stale facts. Nate calls these the four context failure modes: poisoning, bloat, confusion, and clash.
- **The deliverable:** Five specific hacks Nate runs on his own Herk 2 project to keep his AI OS accurate and scalable — grounded in a live OS Audit Skill he built and is giving away free via his Skool community.
- **The OS Audit Skill:** A Claude skill that reads the entire project, checks every claim against reality (routing integrity, index truth, freshness, bloat, context placement), and delivers a markdown report with a fix list awaiting approval. Read-only.

## How It Works — The 4 Failure Modes + 2 Context Types

- **Poisoning:** A false fact sits in the context; agent confidently delivers it. Fix: verification loops.
- **Bloat:** Too much data; needle-in-a-haystack. Fix: expertise vs. situational separation.
- **Confusion:** Missing/irrelevant facts → hallucination to fill gaps.
- **Clash:** Two conflicting sources (e.g., March says "always refund"; June says "never refund").
- **Expertise context** (always-loaded): who you are, policies, goals — like the principal who knows how classrooms run.
- **Situational context** (just-in-time): a specific customer ticket, yesterday's meeting — like the teacher who knows which kids have bad vision. Load only when needed.

## The Verdict

Nate's own Herk 2 audit (July 22): routing integrity broken, index claiming 55 folders vs 79 on disk, data stale through June 29th (month behind), bloat/duplication yellow, context placement red. His verdict: this is fundamentally a **habit** problem, not a tech problem. Team-level AI OS sync is a **people** problem.

## When To Use It (and When Not)

- **Use when:** you're getting wrong answers, context feels stale, or significant new data was added in the past month.
- **Segment knowledge when:** two distinct knowledge bases are both growing on a regular cadence — let Claude suggest the split.
- **Don't:** use audit as a substitute for ongoing maintenance. Pair with automations and the backtrack habit.
- **Not the right tool when:** your AI OS is brand-new and small.

## Set It Up — The 5 Hacks

1. **CLAUDE.md as a Router, Not a System Prompt** — Write "if you need X, go here" for every knowledge type. It becomes a master routing table. Sub-folders get their own CLAUDE.mds for project-specific context.
2. **Have AI Audit Itself** — Download the free OS Audit Skill from Skool, or prompt: "Read everything, check your routing rules, tell me what's wrong, suggest fixes — then wait for my approval."
3. **Build Automations to Update Data** — If you're pulling the same data repeatedly (Q&A transcripts, meeting notes), that's a cron. Natural language: "Set up a weekly cron to pull in my Fireflies transcripts and ingest them into my meetings wiki."
4. **Segment Knowledge** — Split growing, distinct knowledge bases into separate wikis. For clients: internal knowledge in AIOS, deliverables in a separate external repo.
5. **Backtrack** — When Claude can't find data you know exists: "Go look through what you did, where you searched, and figure out why you didn't find that right away." Then have it fix the routing.

## Prompts, Commands & Configs

```
/os-audit
# "Is your AIOS still true? This is your operating manual.
# Indexes and wikis are claims about what exist and what's current.
# The audit checks every claim against reality.
# Read only — never fix, rename, or delete. Just report."

# Backtrack prompt (verbatim from transcript):
"You told me you didn't have access to [X], but I know you do.
Go look through what you did, where you searched, and help me figure out
why you didn't find that data right away. Then update the routing."

# CLAUDE.md routing entry pattern:
# "If you need [X], go to [path]"
# Include: wiki path, hot cache, index, GP fallback, memory system,
#          API keys, skills/agents, decisions log, templates,
#          references, projects folder, other worlds (external repos)

# Cron setup (natural language):
"Set up a weekly cron to pull in my [data source]
and ingest them into my [target wiki]."
```

## Gotchas & Watch-Outs

- **Team syncing is a people problem:** Nate has no solved answer. The tech exists (GitHub, Notion, Drive); the blocker is habit change and permissioning.
- **Don't mix Obsidian Sync + Git on the same vault from multiple machines** (community note): creates conflicts and duplicated changes.
- **Clash is sneaky:** you may not know your policy changed in the context until a customer gets the wrong answer.
- **Audit is not a substitute for crons:** audit surfaces stale data; crons prevent it.

## In His Words

> "My cloudmd is essentially just a master routing file, just a master table of context." — [14:02]

> "There's the only way that you're doing this wrong is if you're constantly getting wrong answers and you're not doing anything about it." — [18:23]

## Steal This For Your Org

1. **Run the OS Audit Skill this week** — free from Skool community. Routing integrity + index truth + freshness report in under 2 minutes.
2. **Rewrite your CLAUDE.md as a routing table today** — strip background prose, replace with "If you need [X], go to [path]."
3. **Set up one automated data pipeline this sprint** — identify the most common manual data pull and build one cron.
4. **Introduce the Backtrack habit** — when an AI agent can't find something it should know, document what it tried, why it failed, fix the routing.

## Mistake to Avoid

Treating your top-level CLAUDE.md as a system prompt. As the project grows, the agent misroutes and hits bloat because it has no map of where things live. Make CLAUDE.md almost purely a routing table.

## Source & Resources

- **Video:** [5 Hacks to Instantly Level Up Your AI OS](https://www.youtube.com/watch?v=Ek1NBfnnTH0) · 25:04
- **Chapters:** 0:00 Intro · 0:39 Running the OS Audit Skill · 1:38 The 4 Context Failure Modes · 4:34 Expertise vs Situational Context · 6:57 Sponsor · 7:58 Audit Results & Skill Walkthrough · 11:56 Tip 1 · 16:53 Tip 2 · 19:09 Tip 3 · 20:15 Tip 4 · 22:50 Tip 5 · 23:48 Team Syncing & Final Thoughts
- **Linked:** [Hyperagent — Nate's Council Skill ($1,000 free credits)](https://hyperagent.com/marketplace/s/ccs01KWCXR3W4_XRNS6AAXVZBT0617) · Free OS Audit Skill on Skool (link in video description)

---
*[[2026-07-24-nate-herk-daily-transcript]] · [[nate-herk]]*
