---
title: "Stanford's Method Turns Claude Into a PHD Level Research Team"
date: 2026-06-29
routine: nate-herk-daily
type: BUILD
video_id: Tj3018n5MVg
url: https://www.youtube.com/watch?v=Tj3018n5MVg
duration: "12:06"
creator: "[[nate-herk]]"
views: 23563
likes: 972
stack: [Claude Code, Claude Desktop, Opus 4.8, Claude Skills, VS Code, Codex]
tags: [claude-code, claude-skills, research, sub-agents, storm-research, deep-research, implementation]
---

# 2026-06-29 — Stanford's Method Turns Claude Into a PHD Level Research Team

[[nate-herk]] · BUILD · 12:06 · [Watch](https://www.youtube.com/watch?v=Tj3018n5MVg)

Related: [[2026-06-29-nate-herk-daily-transcript]] (full transcript extracted via Firecrawl-rendered transcript panel)

---

## What He Builds

A free "Storm Research" Claude Skill that ports Stanford's STORM method — peer-reviewed to produce articles 25% more organized than single-prompt research — into a reusable skill.md plus a report-template.html. It produces a self-contained, verified HTML briefing assembled from five expert "lenses" (practitioner, academic, skeptic, economist, historian) that converge, get mapped for contradictions, then are adversarially peer-reviewed and citation-checked before delivery. He benchmarks it head-to-head against Claude Code's native Deep Research (which spun up 103 agents in his test) with Codex judging both outputs across six criteria.

---

## Stack

- [[claude-code]] — primary tool
- Claude Desktop
- Opus 4.8 — model running the lens sub-agents
- [[claude-code-skills]] — Storm Research packaged as a `.claude` folder skill
- VS Code
- Codex — compatible target for porting the skill

---

## Architecture / How It Works

- **Phase 0 — Scope:** if the topic isn't specific enough, the skill asks clarifying questions before kicking off the pipeline.
- **Phase 1 — Five lenses in parallel:** practitioner, academic, skeptic, economist, and historian sub-agents each research the topic independently on Opus 4.8 (swappable to Haiku/Sonnet).
- **Phase 2 — Contradiction map:** the main session compares the lenses' findings against each other to flag where they disagree and which evidence is strong vs. weak.
- **Phase 3 — Synthesis:** everything is written into the fixed report-template.html — a 60-second summary plus key findings ranked by reliability (e.g. "high, 9/10").
- **Phase 4 — Adversarial peer review:** six more agents verify every citation/stat against its primary source; each source is marked confirmed, corrected, or demoted in the V2 report.
- **Sub-agents, not agent teams:** the five lenses report only to the main session and can't talk to each other — that's what keeps it cheaper than an agent-team setup where lenses would debate one another.

---

## Build It Yourself (Step-by-Step)

1. Grab the two free files — skill.md and report-template.html — from Nate's Skool community: Classroom → All YouTube Resources (link in the video description).
2. **Install the skill** by telling Claude: "this is a skill called Storm Research, put this in the .claude folder." Codex or other agents: drop it in their own skills folder instead.
3. **Invoke it conversationally** — no slash command needed, e.g. "Hey Claude, please run a storm research for me on [your topic]." Vague topics trigger clarifying questions first.
4. **Watch the pipeline run** — five parallel lens sub-agents, then contradiction mapping, synthesis, and adversarial peer review. You can click into any sub-agent to see its exact prompt and live web research.
5. **Review the V2 HTML report** — check the bottom for sources marked confirmed/corrected/demoted, and read the "missing lens" callout (his voice-AI-agents demo flagged a missing frontline-employee/customer perspective).
6. **Customize** — feed the skill your business context so future reports come back pre-tailored, swap the sub-agent model, edit the HTML template, or add a 6th/7th lens (he suggests a "beginner in AI" or "content creator" lens for his own audience).

---

## Prompts, Commands & Configs

```
# Install the skill (verbatim phrasing)
"Hey Claude, this is a skill called Storm Research, put this in the .claude folder."

# Invoke the skill (verbatim phrasing)
"Hey Claude, please run a storm research for me on voice AI agents."

# Tailoring instruction to bake into the skill (verbatim)
"Here's what I'm doing. Here's my business. Here's what our goals are.
Every time you run a storm research report, make it tailored towards us."

# The 4-prompt chain inside the skill (described, not verbatim text)
1. Spin up five expert lenses (practitioner, academic, skeptic, economist, historian) on the topic
2. Contradiction map -- where do the lenses disagree, which evidence is strong vs. weak
3. Synthesis -- write findings into the fixed report-template.html structure
4. Adversarial peer review -- verify every citation against its primary source

# Files (free, linked in video description via Skool community)
skill.md
report-template.html
```

---

## Gotchas & Watch-Outs

- **Deep Research can rate-limit you:** Claude Code's native Deep Research spun up 103 agents on one prompt in his test and got hit by API rate limits — Storm caps at 5 lenses + 6 verifiers (~12 agents total) to avoid that.
- **Skill location matters:** in Claude it has to go in the .claude folder specifically; Codex or other agents need their own skills folder.
- **Don't confuse sub-agents with agent teams:** Storm's five lenses can't talk to each other (sub-agents); agent teams can debate each other but cost more — pick the architecture deliberately.
- **Cross-platform report (community comment):** @dinzilab tried porting the skill into Codex and said it auto-adapted the Claude-specific wording while keeping the STORM workflow intact — worth testing if your org isn't standardized on Claude.

---

## In His Words

> "So Stanford has a research method called Storm, which has actually been shown in peer-reviewed testing to produce articles 25% more organized than the next best method." — 0:00

> "The Storm Research was faster to run and it was 100% cheaper." — 4:06

_Source: Firecrawl-rendered YouTube transcript panel (ytwTranscriptSegmentViewModel DOM); 96 segments, 0:00-12:00, no gaps detected._

---

## Steal This For Your Org

1. Run the head-to-head yourself. Install Storm Research and run it against one real open research question, then run Claude Code's native Deep Research on the identical prompt — compare cost, speed, and source count instead of taking anyone's word for it.
2. Tailor the skill once. Feed it your business context so every future report comes back pre-aimed at your actual decisions instead of generic findings.
3. Add your missing lens. Identify the perspective your org's research chronically skips (frontline employee, customer, beginner) and add it as a sixth lens.
4. Pick sub-agents vs. agent teams on purpose. Default to sub-agents (cheaper, no cross-talk) for research; reserve agent teams (debate, consensus) for decisions that need it.

---

## Mistake to Avoid

Don't assume more agents means better research. Claude Code's native Deep Research fired off 103 agents on a single prompt and ran into rate limits, while Storm's fixed five-lens-plus-verification structure (about a dozen agents total) ran faster and, per Codex's own side-by-side judgment across six categories, produced the stronger, more actionable report.

---

## Source & Chapters

- **URL:** https://www.youtube.com/watch?v=Tj3018n5MVg
- **Duration:** 12:06 · **Views:** 23,563 · **Likes:** 972
- 0:00 What STORM Builds · 0:42 Why Five Perspectives Beat One · 1:28 STORM vs Claude's Deep Research · 4:36 The Four Prompts Behind It · 6:06 How to Get the Skill · 7:26 Live Run: Voice AI Agents · 8:34 Subagents vs Agent Teams · 10:35 Final Takeaways
- **Linked resources:** Free skill.md + report-template.html via Nate's Skool community (Classroom → All YouTube Resources, link in the video description). No other substantive article/report links in the description — only course/sponsor links.
