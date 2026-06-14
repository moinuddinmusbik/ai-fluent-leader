---
title: "Nate Herk Daily Implementation Playbook — 2026-06-13"
date: 2026-06-13
routine: nate-herk-daily
video: "Claude Fable 5 Made This Entire Video By Itself."
video_url: "https://www.youtube.com/watch?v=ONmaDdOBGig"
type: BUILD
sent_to: moinuddin.musbik@gmail.com
---

# Nate Herk Daily Implementation Playbook — 2026-06-13

**AI-Fluent Leader · Implementation Playbook**  
**Claude Fable 5 Made This Entire Video By Itself.**  
Nate Herk · Published: 2026-06-13 · 5:47 · BUILD

**Stack:** Claude Fable 5 · Claude Code · 11 Labs · HeyGen Avatar 5 · Playwright · Voice Playbook

---

## What He Builds

- **Single-prompt video factory:** Nate types one goal into Claude Code, walks away, and returns to a fully produced YouTube video — script, voice, avatar, motion graphics, and final edit — all completed autonomously by Claude Fable 5.
- **The trigger:** Claude Fable 5 (Anthropic's first Mythos-class model, tier above Opus, available to paid subscribers) enabled this pipeline.
- **No filming, no editing, no review:** "What you're watching right now was not filmed. This avatar is AI. The voice you're hearing is a clone of mine. And every single word of this script was written by Claude."

## How It Works — Architecture

- **Orchestrator — Claude Fable 5 in Claude Code:** One prompt kicks off the entire agent loop. Claude plans, researches, writes, and dispatches tasks to downstream services end-to-end.
- **Script layer — Voice Playbook:** Claude writes the script in Nate's voice by referencing a "voice playbook" built from his actual past transcripts.
- **Audio layer — 11 Labs:** Script sent to Nate's voice clone. Critical: audio chunked into segments under 60 seconds each — longer generations cause voice drift.
- **Avatar layer — HeyGen Avatar 5:** Each audio chunk rendered via HeyGen Avatar 5. Previously required Playwright browser automation; HeyGen's new API now exposes it directly.
- **Motion graphics & assembly:** Claude builds all motion graphics and handles final video assembly.

## Build It Yourself

1. **Build a Voice Playbook** — Collect 10–20 of your own transcripts. Prompt Claude to extract your sentence rhythm, vocabulary, and patterns into a reusable voice document.
2. **Set up an 11 Labs voice clone** — Upload 5–10 min of clean audio. Always chunk generation requests to under 60 seconds to prevent drift.
3. **Activate HeyGen Avatar 5 via API** — HeyGen's new API now exposes Avatar 5 directly. Use Playwright as a bridge if your plan doesn't yet support it.
4. **Write the orchestration prompt in Claude Code** — Give Claude: topic/goal + voice playbook file + 11 Labs API key/voice ID + HeyGen API key/avatar ID. Instruct: plan → research → draft script → generate audio chunks → render avatar clips → assemble final video.
5. **Wire Playwright as a fallback** — Keep a browser automation scaffold in your repo for any downstream UI without an API.
6. **Walk away, review on return** — Do not watch while it builds. Review the finished artifact, then iterate.

## Prompts, Commands & Configs

No verbatim system prompt shown on screen.

```
# Voice Playbook pattern (described approach)
# 1. Collect past transcripts → extract voice doc via Claude
# 2. Script: "write in my voice using the attached voice playbook"
# 3. Audio: chunk script into segments <60s, send each to 11 Labs
# 4. Avatar: send each audio chunk to HeyGen Avatar 5 API
# 5. Motion graphics + assembly: Claude handles end-to-end

# Key constraint:
# "you can't just generate like four straight minutes of audio
#  because the longer a generation runs, the more the voice starts to drift.
#  So Claude split the script into chunks, just under a minute each."
```

## Gotchas & Watch-Outs

- ⚠ **Fable 5 access revoked the day this video dropped:** Multiple comments confirm — "And it's gone." Check your plan's current model access.
- **Voice drift above ~60 seconds is non-negotiable:** Hard constraint — not configurable. Always chunk.
- **HeyGen Avatar 5 API availability varies by plan:** Use Playwright bridge if API not yet available.
- **AI voice clone has no natural pauses** — community-noted quality floor.
- **Fable 5 burns session tokens faster than Opus** — budget for token burn on long agentic runs.

## Steal This For Your Org

1. **Build a voice playbook for your team's written voice.** Collect 10–15 transcripts from top communicators; ask Claude to distill vocabulary, rhythm, and patterns.
2. **Map your content pipeline for agentic hand-offs.** Diagram every step from topic to published asset; mark which steps have APIs.
3. **Use Playwright as an API bridge.** When a vendor's UI outpaces their API, ship with the browser fallback and swap to API when it arrives.
4. **Run a one-prompt stress test this week.** Write a single orchestration prompt for any repeatable deliverable. The gaps it hits are your automation roadmap.

## Mistake to Avoid

Assuming the pipeline "just works" at scale on the first try. Voice drift is architectural. HeyGen Avatar 5 API was unavailable until recently. Fable 5 itself lost public availability the same day this video went live. Copy the **pattern** — one orchestrating agent, voice playbook, chunked audio, Playwright as API bridge — not the exact toolstack.

## In His Words

> "I just typed one prompt into Claude code and walked away. And everything else — the research, the script, the voice, the avatar, the motion graphics — all of it happened on its own." — Nate Herk [~0:20]

> "You can't just generate like four straight minutes of audio because the longer a generation runs, the more the voice starts to drift. So Claude split the script into chunks, just under a minute each, and generated them separately." — Nate Herk [~2:30]

## Source & Resources

- **Video:** [Claude Fable 5 Made This Entire Video By Itself.](https://www.youtube.com/watch?v=ONmaDdOBGig) · 5:47 · 84,361 views
- **Chapters:** No chapter markers (single continuous demonstration)
- **Linked:** [AI Automation Society (Skool)](https://www.skool.com/ai-automation-society) · [Glaido](https://get.glaido.com/nate)
- **Transcript:** Partial — extracted via Tavily (Firecrawl unavailable this run, MCP timeout)
