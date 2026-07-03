---
title: "Nate Herk Daily Implementation Playbook — 2026-07-02"
type: email-archive
date: 2026-07-02
source: nate-herk-daily
---

# Nate Herk Daily Implementation Playbook — 2026-07-02

**Video:** How Anthropic Engineers Actually Prompt Fable 5  
**URL:** https://www.youtube.com/watch?v=vcU85OrwuV0  
**Duration:** 10:45  
**Type:** DEEP-DIVE

---

## What It Is

Claude Fable 5 has returned — Anthropic's strongest model yet, with reasoning that "just feels like it knows what you're talking about." It costs $10/M input and $50/M output (2× Opus), and the free promotional window on the Claude plan closes July 7th (capped at 50% of weekly limits, after which usage credits apply). Nate read Anthropic's official prompting best-practices documentation end to end, synthesized guidance from Anthropic engineers on X, and distilled it into six concrete habits to maximize output quality while minimizing wasted tokens.

## How It Works — The Six Rules

1. **Give it the why (any model):** Context lets Fable connect your task to the right information instead of guessing intent. Don't say "write an email to a client about the delay" — say "I'm working on [bigger task] for [who]. What they need is [X]. With that in mind, help me write an email about the delay." If your AIOS/second brain is set up correctly, this also prompts Fable to pull the right context files.

2. **Negative-prompt explicitly (any model):** AI predicts the next likely word and will improvise unless constrained. Anthropic's own system prompt does this repeatedly. Example: "When I'm describing a problem, the deliverable is your assessment. Report what you find and stop. Don't fix, send, edit, or delete anything until I say go." Think of it like briefing an intern on what not to touch.

3. **Let it act once it has enough (any model):** Stop over-planning. Match effort to task: `high` as default, `xhigh` for critical work, `medium`/`low` for routine. Fable 5 on LOW is comparable to Opus 4.8 on XHIGH/MAX at similar or lower cost — using Fable for routine work means paying peak prices for mid-tier throughput.

4. **Make it prove it (any model):** Bake verification loops into every agent, skill, and CLAUDE.md rather than asking ad hoc. Build this structurally so verification is automatic, not optional.

5. **Stop asking it to show its reasoning (Fable-specific):** A standing "explain your reasoning" or "show your work" line in a system prompt can trigger Fable's safety classifier and silently route your request to Opus 4.8. The UI gives no signal that a handoff occurred.

6. **Say less, not more (Fable-specific):** Short instructions now steer as well as long rule enumerations. Not a contradiction with Rule 1 (context/why is still needed) — but don't bloat system prompts with numbered rule lists. "Lead with the outcome. Keep it simple and pause only when the work truly needs me."

## The Verdict

Fable 5 is genuinely the strongest model Nate has used — "hands down." But it is expensive and overkill for 85–95% of tasks. Reserve Fable for the 5–15% of tasks where peak reasoning genuinely moves the needle.

## When To Use It (and When Not)

- **Use Fable 5:** High-stakes reasoning, complex multi-step orchestration, tasks where peak accuracy is worth the cost. Set effort to `high` (default) or `xhigh` for critical work.
- **Don't use Fable 5:** Routine tasks, drafting, quick lookups. Fable 5 on LOW rivals Opus 4.8 on XHIGH/MAX at similar cost.
- **Hard triggers for handoff:** Hacking-related prompts, dangerous biology, asking Fable to reveal private reasoning — all trigger silent route to Opus 4.8.

## Set It Up

1. **Audit your CLAUDE.md and skill files** — Grep for "explain your reasoning," "show your work," "think step by step." Remove them before July 7th.
2. **Add Rule 4 verification block to every shared template** — "Before you tell me something is done, point to the result that proves it. Only report work you can show evidence for. If something isn't verified, say so plainly instead of guessing."
3. **Build negative-prompt guardrails into agent/skill definitions** — Move common "don't do X" constraints to the agent level.
4. **Set model intentionally** — Use `/model` in Claude Code to switch to Fable 5 only for high-stakes sessions.
5. **Wire effort levels into system prompts** — "Use `high` as default; `xhigh` for critical; `medium`/`low` for routine."
6. **Refactor prompt shape** — intent/why → task → what not to do → verification requirement.

## Prompts, Commands & Configs

```
# Rule 1 — Give it the why
"I'm working on [bigger task] for [who]. What they need is [X].
With that in mind, help me write an email to this client about the delay."

# Rule 2 — Negative prompt (build into CLAUDE.md / agent skill)
"When I'm describing a problem or asking a question, the deliverable
is your assessment. Report what you find and stop. Don't fix, send,
edit, or delete anything until I say go."

# Rule 3 — Let it act
"When you have enough information to act, act."

# Rule 4 — Verification block (add to every CLAUDE.md / skill)
"Before you tell me something is done, point to the result that proves it.
Only report work you can show evidence for.
If something isn't verified, say so plainly instead of guessing."

# Rule 6 — Outcome-first instruction
"Lead with the outcome. Keep it simple and
pause only when the work truly needs me."

# Effort-level guidance
"Use high effort as default for most tasks.
Use xhigh for the most capability-sensitive work.
Use medium or low for routine tasks."
```

## Gotchas & Watch-Outs

- **Silent Opus handoffs are more aggressive than documented:** Community users (July 2026) report Fable routing to Opus every 2 minutes during security audits and code reviews. Anthropic acknowledged classifiers are overreacting on coding in the short term.
- **"Explain your reasoning" is a hidden trap:** A standing line triggers the safety classifier silently. You won't see it happen in the UI.
- **Promotional window closes July 7th:** After that, Fable 5 beyond 50% of weekly limits requires usage credits.
- **Cost math:** Fable 5 on LOW rivals Opus 4.8 on XHIGH/MAX. Using Fable for routine work is paying 2× for the same result.
- **Session-handoff tip (community):** Switch to Opus 4.8 for handoffs, do `/copy /clear`, then switch back to Fable 5. Saves meaningful weekly allocation.

## Steal This For Your Org

1. **Run a 30-minute CLAUDE.md audit before July 7th.** Strip "explain your reasoning," "show your work," "think step by step" from every team system prompt.
2. **Stamp the Rule 4 verification block into every shared agent template.** Verification becomes structural.
3. **Write a one-page model-tier decision tree.** Fable for 5–15% of tasks only. Share before the promotional period ends.
4. **Refactor your standard prompt template** to: why/intent → task → what not to do → verification requirement.

## Mistake to Avoid

Defaulting Fable 5 to all tasks because it's "the strongest model." Promotional window closes July 7th. Fable on LOW rivals Opus 4.8 on XHIGH/MAX — no uplift on routine work, at 2× the price.

## In His Words

> "Before you tell me something is done, point to the result that proves it. Only report work you can show evidence for. If something isn't verified, say so plainly instead of guessing." — 7:25

> "A standing explain your reasoning line, especially in the system prompt, can trigger a refusal and it can hand your task to Opus 4.8." — 7:47

## Source & Resources

- **Video:** [How Anthropic Engineers Actually Prompt Fable 5](https://www.youtube.com/watch?v=vcU85OrwuV0) · 10:45 · 48,696 views
- **Chapters:** 0:00 Fable 5 Is Back · 1:26 Sponsor · 2:25 Rule 1 · 3:33 Rule 2 · 5:01 Rule 3 · 6:44 Rule 4 · 7:42 Rule 5 · 8:29 Rule 6 · 9:22 When Fable Hands Off To Opus
- **Referenced:** Anthropic's official "Best Practices for Prompting Claude Fable 5" docs (free Skool community → classroom → All YouTube Resources)
- **Transcript:** [[2026-07-02-nate-herk-daily-transcript]]
