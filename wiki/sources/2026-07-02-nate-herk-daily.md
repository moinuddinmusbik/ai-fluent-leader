---
title: "How Anthropic Engineers Actually Prompt Fable 5"
type: source
date: 2026-07-02
slug: nate-herk-daily
creator: "[[nate-herk]]"
url: https://www.youtube.com/watch?v=vcU85OrwuV0
duration: 10:45
video_type: DEEP-DIVE
tags: [claude-fable-5, prompting, fable-5-rules, opus-4-8, claude-code, effort-levels]
---

# How Anthropic Engineers Actually Prompt Fable 5

**Creator:** [[nate-herk]]  
**URL:** https://www.youtube.com/watch?v=vcU85OrwuV0  
**Published:** 2026-07-02  
**Duration:** 10:45  
**Type:** DEEP-DIVE  
**Transcript:** [[2026-07-02-nate-herk-daily-transcript]]

---

## Stack

- Claude Fable 5
- Opus 4.8 (fallback / cheaper model for routine/handoffs)
- Claude Code (`/model` to switch)
- Claude Desktop App
- VS Code

---

## What It Is

Claude Fable 5 returned after its first promotional period. Nate read Anthropic's official "Best Practices for Prompting Claude Fable 5" documentation end to end and synthesized guidance from Anthropic engineers on X into six concrete prompting habits. Cost: $10/M input, $50/M output (2× Opus). Promotional period on Claude plan ends July 7th — free use capped at 50% of weekly limits, usage credits apply after that.

---

## How It Works — The Six Rules

### Rule 1: Give it the why (any model)
Context lets Fable connect your task to the right information instead of guessing intent. Anthropic explicitly says Fable does better when it understands your intent. Add the bigger task context, who it's for, and what they need before the actual request. If AIOS/second brain is set up correctly, this also triggers Fable to pull the right context files automatically.

### Rule 2: Negative-prompt explicitly (any model)
AI predicts the next likely word and will improvise unless constrained. Tell it what NOT to do. Anthropic's own system prompt is full of negative constraints ("Don't add features. Don't do this."). Think of it like briefing an intern — they don't know your process, so you tell them specific things to avoid.

### Rule 3: Let it act once it has enough (any model)
Stop over-planning. Match effort levels to tasks:
- `high` — default for most tasks
- `xhigh` — most capability-sensitive work
- `medium`/`low` — routine work

Key insight: Fable 5 on LOW is cost-comparable to Opus 4.8 on XHIGH/MAX. The right lever is effort-level selection, not model selection. Nate's estimate: reach for Fable only 5–15% of the time.

### Rule 4: Make it prove it (any model)
Bake verification loops structurally into CLAUDE.md, agent skills, and memory files — not as ad hoc per-prompt instructions. The goal: trust that the model has verified its own output 2–5 times before reporting done, so you don't feel like you have to check it as much.

### Rule 5: Stop asking it to show its reasoning (Fable-specific)
A standing "explain your reasoning" or "show your work" line in a system prompt can trigger Fable's safety classifier and silently route the request to Opus 4.8. Fable has safety guardrails that push to a less capable model if intent appears suspicious or the classifier fires. UI users get no signal; API users see the model field.

### Rule 6: Say less, not more (Fable-specific)
Short instructions now steer as well as verbose rule enumerations. Not a contradiction with Rule 1 — context/why is still needed, but don't enumerate rules in a list. One clear outcome sentence replaces numbered rule sets.

---

## The Verdict

"It's the strongest model I've ever used, hands down." But overkill for 85–95% of tasks. The right approach: know which 5–15% of your work truly needs peak reasoning; clean system prompts of reasoning-trigger lines before July 7th; use effort-level selection for cost management.

---

## When To Use It (and When Not)

**Use Fable 5:**
- High-stakes reasoning, complex multi-step orchestration
- Tasks where peak accuracy is worth 2× the cost
- Effort: `high` (default) or `xhigh` (critical)

**Don't use Fable 5:**
- Routine tasks, drafting, quick lookups — use Opus 4.8 or lower
- Fable 5 on LOW rivals Opus 4.8 on XHIGH/MAX: you're paying 2× for the same result on routine work

**Hard triggers for handoff to Opus 4.8:**
- Hacking-related prompts
- Dangerous biology
- Asking Fable to reveal its private reasoning
All trigger silent reroute. No UI notification.

---

## Set It Up (Reproducible Steps)

1. **Audit every CLAUDE.md and skill file** — Grep for "explain your reasoning," "show your work," "think step by step." Strip them before July 7th.
2. **Add Rule 4 verification block to every shared template** — See Prompts section below.
3. **Build negative-prompt guardrails into agent/skill definitions** — Move common "don't do X" constraints to the agent level, not per-prompt.
4. **Set `/model` in Claude Code** intentionally — Fable 5 only for high-stakes sessions; Opus 4.8 for everyday work.
5. **Wire effort levels into system prompt** — "Use `high` as default; `xhigh` for critical; `medium`/`low` for routine."
6. **Refactor prompt shape** — intent/why → task → what not to do → verification requirement.

---

## Prompts, Commands & Configs

```
# Rule 1 — Give it the why
"I'm working on [bigger task] for [who]. What they need is [X].
With that in mind, help me write an email to this client about the delay."

# Rule 2 — Negative prompt (add to CLAUDE.md / agent skill)
"When I'm describing a problem or asking a question, the deliverable
is your assessment. Report what you find and stop. Don't fix, send,
edit, or delete anything until I say go."

# Rule 3 — Let it act
"When you have enough information to act, act."

# Rule 4 — Verification block (add to every CLAUDE.md / skill)
"Before you tell me something is done, point to the result that proves it.
Only report work you can show evidence for.
If something isn't verified, say so plainly instead of guessing."

# Rule 6 — Outcome-first instruction (replaces verbose rule lists)
"Lead with the outcome. Keep it simple and
pause only when the work truly needs me."

# Effort-level guidance (add to system prompt)
"Use high effort as default for most tasks.
Use xhigh for the most capability-sensitive work.
Use medium or low for routine tasks."
```

---

## Gotchas & Watch-Outs

1. **Silent Opus handoffs are more aggressive than documented:** Community reports (July 2026) show Fable routing to Opus every 2 minutes during security audits and code reviews — not just obviously malicious prompts. Anthropic acknowledged classifiers are overreacting on coding tasks in the short term.
2. **"Explain your reasoning" is a hidden trap:** A standing line in any system prompt silently triggers the handoff. No UI notification.
3. **Promotional window closes July 7th:** Fable beyond 50% of weekly limits requires usage credits. Plan testing window accordingly.
4. **Cost math is non-intuitive:** Fable 5 on LOW ≈ Opus 4.8 on XHIGH/MAX. Using Fable for routine work = 2× price for the same result.
5. **Session-handoff tip (from community):** Switch to Opus 4.8 for the handoff step (cheaper tokens), run `/copy /clear`, then switch back to Fable 5 with the pasted handoff notes. Saves meaningful Fable weekly allocation.

---

## Steal This For Your Org

1. **30-minute CLAUDE.md audit before July 7th** — Strip reasoning-trigger lines from every team system prompt and agent skill.
2. **Stamp Rule 4 verification block into every shared agent template** — Verification becomes structural, not per-prompt.
3. **One-page model-tier decision tree for your team** — Fable for 5–15% of tasks only. Share before promotional period ends.
4. **Refactor standard prompt template** to: intent/why → task → what not to do → verification requirement.

---

## Mistake to Avoid

Defaulting Fable 5 to all tasks because it's "the strongest model." Promotional window closes July 7th. Fable on LOW rivals Opus 4.8 on XHIGH/MAX — no uplift on routine work at 2× the price. Nate's estimate: 85–95% of your tasks don't need Fable.

---

## In His Words

> "Before you tell me something is done, point to the result that proves it. Only report work you can show evidence for. If something isn't verified, say so plainly instead of guessing." — 7:25

> "A standing explain your reasoning line, especially in the system prompt, can trigger a refusal and it can hand your task to Opus 4.8." — 7:47

---

## Source & Chapters

- **Video:** [How Anthropic Engineers Actually Prompt Fable 5](https://www.youtube.com/watch?v=vcU85OrwuV0) · 10:45 · 48,696 views
- **Chapters:**
  - 0:00 Fable 5 Is Back
  - 1:26 Sponsor (Hyper Agent)
  - 2:25 Rule 1 — Give it the why
  - 3:33 Rule 2 — Negative prompt
  - 5:01 Rule 3 — Let it act once it has enough
  - 6:44 Rule 4 — Make it prove it
  - 7:42 Rule 5 — Stop asking it to show reasoning
  - 8:29 Rule 6 — Say less, not more
  - 9:22 When Fable Hands Off To Opus
- **Referenced docs:** Anthropic "Best Practices for Prompting Claude Fable 5" (linked in free Skool community)
- **Linked:** [[2026-07-02-nate-herk-daily-transcript]], [[nate-herk]]
