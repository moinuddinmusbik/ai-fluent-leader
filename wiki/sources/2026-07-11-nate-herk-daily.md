---
title: "Claude Code for Non-Coders (6 Hour Course)"
type: source
date: 2026-07-11
url: https://www.youtube.com/watch?v=jdbOVepEtUE
duration: 5:59:00
creator: "[[nate-herk]]"
video_type: BUILD
stack: [claude-code, claude-haiku-4-5, claude-sonnet-5, claude-opus-4-8, mcp-google-workspace, claude-md, settings-json, github, vercel, vps-hostinger]
tags: [claude-code, sub-agents, skills, second-brain, automation, cloud-routines, prompt-caching, mcp]
---

# Claude Code for Non-Coders (6 Hour Course)

> BUILD · 5:59:00 · 2026-07-11 · [[nate-herk]]

**Video:** [Claude Code for Non-Coders (6 Hour Course)](https://www.youtube.com/watch?v=jdbOVepEtUE)  
**Transcript:** [[2026-07-11-nate-herk-daily-transcript]]

---

## Stack

- Claude Code (desktop app + terminal)
- Claude Haiku 4.5 (sub-agent workers)
- Claude Sonnet 5 (mid-tier orchestration)
- Claude Opus 4.8 (main orchestrator / planning)
- MCP: Google Workspace (Gmail, Docs, Sheets, Calendar)
- `.claude/claude.md` + `settings.json`
- GitHub + Vercel (website deployment)
- VPS: Hostinger (cloud scheduled routines)

---

## What He Builds

A complete 6-hour beginner-to-AI-native course covering every layer of the Claude Code ecosystem:
- **AIOS (AI Operating System):** The `.claude/` folder as the runtime — `claude.md`, `settings.json`, `skills/`, `agents/`.
- **Skills:** Reusable slash commands as markdown files. Demonstrated: session-handoff, LinkedIn researcher, Grill-Me quiz, agent-builder.
- **Custom Sub-Agents:** YAML-front-matter markdown files. Demonstrated: Plan Roaster, ClickUp Searcher.
- **Second Brain:** 5 Levels system — from raw notes to a Knowledge Graph with Grill-Me Skill for retention testing.
- **Scheduled Cloud Routines:** Research automation on VPS via cron. Claude Code in non-interactive mode → email output.
- **Token Dashboard:** Open-source GitHub repo for visualising session token usage and cache hit rate.

---

## How It Works (Architecture)

```
.claude/
  claude.md          ← project context + rules (cached per project)
  settings.json      ← permissions, model, hooks
  skills/            ← slash commands (.md files)
  agents/            ← sub-agents (.md files with YAML front matter)

~/.claude/
  claude.md          ← global context (all projects)
  settings.json      ← global permissions
```

**Prompt caching layers:**
1. System instructions → globally cached
2. claude.md + memory files → cached per project (1h TTL on subscription, 5min on API)
3. Conversation turns → accumulated each message

**Orchestrator pattern:**
- Main session: Opus or Sonnet (judgment + orchestration)
- Sub-agents: Haiku or Sonnet (parallel workers, fresh 200K context each)
- Sub-agents invoked by progressive disclosure — Claude reads only YAML front matter to decide

---

## Build It Yourself

1. **Install & first prompt** — `npm i -g @anthropic-ai/claude-code`. Open folder → `claude` → *"Tell me what you see and ask me three clarifying questions before you do anything."*
2. **Create project claude.md** — `.claude/claude.md`: who you are, project purpose, tools, rules. + `settings.json` with permission mode.
3. **Connect tools** — `.env` with scoped API keys. Google Workspace MCP for Gmail/Docs/Sheets/Calendar.
4. **Build first Skill** — `.claude/skills/session-handoff.md`. YAML front matter + step-by-step instructions. Trigger: `/session-handoff`.
5. **Build custom Sub-Agent** — `.claude/agents/plan-roaster.md`. `name`, `description` (be precise!), `model: claude-haiku-4-5`. Body: persona + framework. Test auto-invocation.
6. **Deploy cloud routine** — VPS + `claude --print "…task…"` + `crontab -e`. Output → email or GitHub commit.
7. **Monitor tokens** — Token dashboard repo (Skool community) → `claude "Set this up on localhost."` → tracks past sessions, shows cache hit rate.

---

## Prompts, Commands & Configs

```
# Slash commands
/compact          # summarise + compress context
/clear            # wipe session
/model            # switch model (BREAKS cache — set at session start only)

# Sub-agent YAML front matter
---
name: plan-roaster
description: Use proactively when user shares a business plan or idea to critique ruthlessly
model: claude-haiku-4-5-20251001
color: red
---

# Orchestrator → Sub-agent cost pattern
Main (Sonnet/Opus): judgment, orchestration, final synthesis
Sub-agents (Haiku): research, drafting, data extraction — parallel, fresh context

# Cache discipline (3 habits)
1. Don't leave session idle > 1 hour
2. /session-handoff → /clear  (not /compact)
3. Choose model ONCE at start — never switch mid-session
```

---

## Gotchas & Watch-Outs

- **Sub-agent cache TTL = 5 min** (not 1 hour). Long routines must handle cold-cache costs.
- **Model switch resets entire cache** — `/model` or `opus plan` mid-session reprocesses all prior tokens.
- **Vague agent descriptions → misfires** — iterate description field with real test prompts; it's the only trigger Claude checks.
- **Claude won't find undisclosed files** — put paths to key folders explicitly in `claude.md`.
- **Can't automate what you can't map** — document trigger → steps → decision points → output format before building.

---

## In His Words

> "In this course, I'm going to take you from a complete beginner to someone who is AI native and can build automations, AI agents, literally anything that you can describe, you're going to be able to build by the end of this course." — 0:00

> "When we use a sub agent we can delegate tokens to be spent in a different context window in a fresh sub agent. That way our main orchestration agent is able to just call on a bunch of them. This main agent can delegate work to all of these little workers that are all maybe on Sonnet or maybe even on Haiku. So you can delegate work that's a little bit less high priority or high risk to cheaper models and you can just get some really cool results by doing stuff like that." — 2:20:23

---

## Steal This For Your Org

1. **Process audit:** Map 5–10 trigger-based weekly tasks → pick highest-frequency → build Skill or sub-agent. Heuristic: triggers >weekly + takes >20 min = automate.
2. **Team claude.md:** One file per project, written by domain expert. Cached context every agent inherits automatically.
3. **Scheduled research routine:** VPS + cron + `claude --print` → email brief. Start from 5:03:03 chapter pattern.
4. **Orchestrator → Sub-agent cost model:** Sonnet orchestrator + Haiku workers ≈ same cost as Sonnet alone, with parallelism.

---

## Mistake to Avoid

Automating before mapping. *"If I had 6 hours to chop down a tree, I would spend the first four sharpening the axe."* (Abraham Lincoln, quoted by Nate at ~2:11:35.) Document the process first.

---

## Source & Chapters

- **Video:** [Claude Code for Non-Coders (6 Hour Course)](https://www.youtube.com/watch?v=jdbOVepEtUE) · 5:59:00
- **Full chapter list:**
  - 0:00 Intro: From Beginner to AI Native
  - 1:00 What Is Claude Code (Chat, Cowork, Code)
  - 5:04 Models vs Context (The Core Analogy)
  - 6:48 The 12 Mindset Shifts
  - 14:52 Prompt Engineering vs Context Engineering
  - 17:33 Taste, Iteration & Building Your Jarvis
  - 24:20 One Passion, Many Branches
  - 31:44 Installing Claude Code & Your First Prompts
  - 34:09 Working With Local Files (Excel, HTML)
  - 38:18 Prompt Engineering & Verifying the Output
  - 43:25 Tokens & Choosing Your Model
  - 48:10 Setting Up a Project (claude.md & settings.json)
  - 1:00:06 Connecting Tools: API Keys & .env
  - 1:09:59 Permission Modes, Scoped Keys & Privacy
  - 1:20:31 Building Your AI Operating System
  - 1:25:08 Connecting Google Workspace: CLIs vs MCPs
  - 1:40:28 Skills Deep Dive
  - 1:56:13 The Context Window & Session Handoff
  - 2:03:17 Memory & Your Second Brain
  - 2:11:35 Constraints, Metrics & Mapping Your Process
  - 2:20:23 Sub-Agents Explained
  - 2:31:41 Building a Sub-Agent: The Plan Roaster
  - 2:43:46 When to Use Sub-Agents
  - 2:47:27 Installing in the Terminal + Free Resources
  - 2:53:11 Building & Cloning Websites
  - 3:10:54 Deploying With GitHub & Vercel
  - 3:18:58 The AI Systems Pyramid & Trusting the Output
  - 3:36:15 Building a Second Brain
  - 3:56:28 The 5 Levels of a Second Brain
  - 4:13:43 Knowledge Graphs & the Grill-Me Skill
  - 4:31:50 Sub-Agents vs Agent Teams
  - 4:45:35 Scheduled Automations & Cloud Routines
  - 5:03:03 Building a Research Automation
  - 5:27:13 Token Management & Prompt Caching
  - 5:58:20 Final Thoughts
- **Linked resources:** [Hostinger VPS](https://www.hostinger.com/vps/claude-code-hosting) · [Free Skool Community](https://www.skool.com/ai-automation-society/about)
