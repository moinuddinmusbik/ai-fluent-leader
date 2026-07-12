---
title: "Nate Herk Daily Implementation Playbook — 2026-07-11"
type: email-archive
date: 2026-07-11
video: "Claude Code for Non-Coders (6 Hour Course)"
url: https://www.youtube.com/watch?v=jdbOVepEtUE
duration: 5:59:00
video_type: BUILD
---

# AI-Fluent Leader · Implementation Playbook
## Claude Code for Non-Coders (6 Hour Course)

**Nate Herk · Published: 2026-07-11 · 5:59:00 · BUILD**

**Stack:** Claude Code · Claude Haiku 4.5 · Claude Sonnet 5 · Claude Opus 4.8 · MCP (Google Workspace) · claude.md · settings.json · GitHub + Vercel · VPS (Hostinger)

---

### What He Builds

- **AI Operating System (AIOS):** A complete personal operating system built on Claude Code — from a blank terminal to running scheduled cloud automations while you sleep. Every layer: project files, skills, sub-agents, second brain, and cloud routines.
- **Skills (slash commands):** Reusable markdown instruction files in `.claude/skills/`. He demonstrates a session-handoff skill, LinkedIn research skill, Grill-Me knowledge-quiz skill, and more.
- **Custom Sub-Agents:** YAML-front-matter markdown files in `.claude/agents/`. He builds a "Plan Roaster" sub-agent and a ClickUp Searcher agent with model assignment.
- **Second Brain:** Structured markdown knowledge files cached in project context — with the 5 Levels of a Second Brain and a Knowledge Graph/Grill-Me Skill.
- **Scheduled Cloud Routine:** Research automation on a VPS via cron — Claude Code runs non-interactively, fetches, synthesises, emails. No human needed after setup.
- **Token Dashboard:** Open-source GitHub repo that visualises token usage and cache hit rate locally.

---

### How It Works (Architecture)

- **The .claude/ folder is everything:** `claude.md` (project context + rules, cached every session), `settings.json` (permissions, model, hooks), `skills/`, `agents/`. Global versions in `~/.claude/` apply everywhere.
- **Orchestrator → Sub-agent delegation:** Main session (Opus/Sonnet) acts as orchestrator. Delegates parallel workloads to sub-agents in fresh, isolated context windows on cheaper models (Haiku/Sonnet). Keeps main context clean, cuts token cost.
- **Progressive disclosure:** Claude Code reads only YAML front matter (name + description) to decide whether to invoke a skill/agent — avoids wasting tokens on irrelevant files.
- **Prompt caching layers:** System instructions → globally cached. `claude.md` + memory → cached per project. Conversation turns → accumulated. Cache TTL: 1 hour on subscription, 5 minutes on API/sub-agents.
- **Cloud deployment:** Claude Code on VPS runs cron-scheduled or webhook-triggered tasks in non-interactive mode. Output committed to GitHub or emailed via API.

---

### Build It Yourself

1. **Install Claude Code & run your first prompt** — Install from Claude desktop app or terminal (`npm i -g @anthropic-ai/claude-code`). Open a folder, run `claude`, start with: *"You are in my [project] folder. Tell me what you see and ask me three clarifying questions before you do anything."*
2. **Create your project claude.md** — In `.claude/claude.md`: who you are, what this project does, what tools you use, rules Claude must follow. Also set up `settings.json` with permission mode.
3. **Connect tools via API keys & MCPs** — Add `.env` with scoped API keys. Install Google Workspace MCP server and authenticate.
4. **Build your first Skill** — Create `.claude/skills/session-handoff.md`. YAML front matter + step-by-step instructions. Trigger with `/session-handoff`.
5. **Build a custom Sub-Agent** — Create `.claude/agents/plan-roaster.md`. YAML: `name`, `description` (be precise!), `model: claude-haiku-4-5`. Body: persona + critical framework. Test auto-invocation.
6. **Deploy a scheduled cloud routine** — Spin up VPS, install Claude Code, authenticate. Shell script: `claude --print "…task prompt…"`. Crontab for daily/weekly schedule. Output → email or GitHub commit.
7. **Monitor token usage** — Clone token dashboard repo (in Nate's free Skool community). Tell Claude: *"Set this up on localhost."* It ingests past sessions and shows cache-hit rates, daily burn, per-session cost.

---

### Prompts, Commands & Configs

```
# Built-in slash commands
/compact          # summarise context + compress session
/clear            # wipe session and start fresh
/model            # switch model (WARNING: breaks prompt cache — choose at session start)

# YAML front matter for a sub-agent (.claude/agents/my-agent.md)
---
name: plan-roaster
description: Use proactively when the user shares a business plan or idea to critique it ruthlessly
model: claude-haiku-4-5-20251001
color: red
---
[agent instructions here]

# Orchestrator cost pattern
Main session: Opus (judgment + orchestration)
Sub-agents:   Haiku or Sonnet (research, drafting, data tasks)
→ Parallel execution, each in a fresh 200K context window

# Three cache habits that cover 95% of users
1. Don't pause a session for more than 1 hour (TTL resets)
2. Use /session-handoff skill → /clear instead of /compact
3. Set model ONCE at session start — switching mid-session breaks cache
```

---

### Gotchas & Watch-Outs

- **Sub-agent TTL is 5 minutes, not 1 hour:** API and sub-agent calls drop to 5-minute TTL. Long cloud routines relying on sub-agents will constantly bust cache.
- **Switching models mid-session resets the entire cache:** `/model` or `opus plan` pattern (Opus for planning → Sonnet for execution) breaks prefix-matching — every prior token reprocessed from scratch.
- **Vague agent descriptions cause misfires:** Sub-agent description = trigger mechanism. Too broad = unwanted invocations. Too narrow = never fires. Iterate with real test prompts.
- **Claude won't look for files it doesn't know about:** Put paths to key folders explicitly in `claude.md` or tell Claude directly at session start.
- **You can't automate what you can't map:** Document the trigger, steps, decision points, and desired output format before you automate.

---

### Steal This For Your Org

1. **Process audit this week.** Write down 5–10 trigger-based tasks. Pick highest-frequency. Build a Skill or sub-agent. Nate's heuristic: triggers more than weekly + takes more than 20 minutes = automate it.
2. **Give every team project a claude.md.** Written by whoever knows the project best. Defines context, terminology, data sources, rules. Cached context every team member (and agent) inherits automatically.
3. **Deploy one scheduled research routine.** Competitive intel, news monitoring, client signals. VPS + cron + Claude → email brief. Zero human time after setup. Start with 5:03:03 chapter.
4. **Implement Orchestrator → Sub-agent cost model.** Main session: Sonnet. Parallel branches: Haiku. One Sonnet orchestrator + five Haiku workers ≈ same cost as running on Sonnet alone.

---

### Mistake to Avoid

Starting to build automations before you can map the process. Nate invokes Abraham Lincoln: *"If I had 6 hours to chop down a tree, I would spend the first four sharpening the axe."* Hand Claude an unstructured, un-mapped process and you're hiring an intern with zero onboarding.

---

### In His Words

> "In this course, I'm going to take you from a complete beginner to someone who is AI native and can build automations, AI agents, literally anything that you can describe, you're going to be able to build by the end of this course." — 0:00

> "When we use a sub agent we can delegate tokens to be spent in a different context window in a fresh sub agent. That way our main orchestration agent is able to just call on a bunch of them. This main agent can delegate work to all of these little workers that are all maybe on Sonnet or maybe even on Haiku. So you can delegate work that's a little bit less high priority or high risk to cheaper models and you can just get some really cool results by doing stuff like that." — 2:20:23

---

### Source & Resources

- **Video:** [Claude Code for Non-Coders (6 Hour Course)](https://www.youtube.com/watch?v=jdbOVepEtUE) · 5:59:00
- **Chapters:** 0:00 Intro · 1:00 What Is Claude Code · 6:48 The 12 Mindset Shifts · 31:44 Installing · 48:10 Project Setup · 1:00:06 API Keys & .env · 1:25:08 Google Workspace MCPs · 1:40:28 Skills Deep Dive · 2:03:17 Second Brain · 2:20:23 Sub-Agents · 2:31:41 Building a Sub-Agent · 4:45:35 Scheduled Automations · 5:03:03 Research Automation · 5:27:13 Token Management · 5:58:20 Final Thoughts
- **Linked:** [Hostinger VPS](https://www.hostinger.com/vps/claude-code-hosting) · [Free Skool Community](https://www.skool.com/ai-automation-society/about)
- **Transcript:** [[2026-07-11-nate-herk-daily-transcript]]
