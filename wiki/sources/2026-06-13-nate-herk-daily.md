---
title: "Claude Fable 5 Made This Entire Video By Itself."
date: 2026-06-13
type: source
routine: nate-herk-daily
video_type: BUILD
creator: "[[nate-herk]]"
video_url: "https://www.youtube.com/watch?v=ONmaDdOBGig"
duration: "5:47"
stack: [claude-fable-5, claude-code, 11-labs, heygen-avatar-5, playwright, voice-playbook]
tags: [build, agentic-video-production, voice-clone, ai-avatar, claude-code]
transcript: "[[2026-06-13-nate-herk-daily-transcript]]"
---

# Claude Fable 5 Made This Entire Video By Itself.

**Creator:** [[nate-herk]]  
**Date:** 2026-06-13 · **Type:** BUILD · **Duration:** 5:47  
**Video:** https://www.youtube.com/watch?v=ONmaDdOBGig  
**Stack:** [[claude-fable-5]] · [[claude-code]] · [[11-labs]] · [[heygen]] · [[playwright]]

---

## What He Builds

Nate gives [[claude-fable-5]] a single goal prompt inside [[claude-code]], goes to the gym, and returns to a fully produced YouTube video — script, voice, avatar, motion graphics, and final edit — all completed autonomously. No filming. No editing. No watching.

Enabled by [[claude-fable-5]]: Anthropic's first Mythos-class model (tier above Opus) available to paid subscribers.

## Architecture

```
Claude Fable 5 in Claude Code (orchestrator)
  ↓ plan + research
  ↓ write script [using Voice Playbook context doc]
  ↓ chunk script into <60s segments
  ↓ → 11 Labs (voice clone generation per chunk)
  ↓ → HeyGen Avatar 5 (avatar render per chunk)
  ↓ → [Playwright as fallback if Avatar 5 not yet in API]
  ↓ build motion graphics
  ↓ assemble final video
```

**Voice Playbook:** doc Claude extracts from Nate's actual past transcripts — his vocabulary, rhythm, sentence patterns. Fed as context for the script-writing step.

**Audio chunking:** 11 Labs voice generation degrades (voice drift) past ~60 seconds. Claude splits script into sub-minute chunks and generates them separately.

**HeyGen Avatar 5:** Previously not accessible via API — Claude drove a real browser via [[playwright]] to flip each video manually. HeyGen's new API now exposes Avatar 5 directly.

## Build Steps

1. Collect past transcripts → extract Voice Playbook via Claude
2. Set up 11 Labs voice clone (5–10 min clean audio, custom model)
3. Activate HeyGen Avatar 5 via new API (Playwright fallback if plan doesn't expose it yet)
4. Write orchestration prompt: topic/goal + voice playbook path + 11 Labs API key/voice ID + HeyGen API key/avatar ID
5. Claude executes: plan → research → script → audio chunks (<60s each) → avatar renders → assembly
6. Review finished artifact; iterate on prompt or Voice Playbook

## Prompts & Configs

No verbatim orchestration prompt shown on screen.

```
# Described approach:
# "write in my voice using the attached voice playbook"
# Chunk audio: segments just under a minute each → 11 Labs
# HeyGen Avatar 5: direct API call (or Playwright fallback)
# Motion graphics + final assembly: Claude-managed
```

Key constraint (exact words): _"you can't just generate like four straight minutes of audio because the longer a generation runs, the more the voice starts to drift. So Claude split the script into chunks, just under a minute each."_

## Gotchas

- ⚠ **Fable 5 revoked 2026-06-13:** Community: "And it's gone." Anthropic pulled or restricted Fable 5 public access the same day this video published. Check plan model access.
- **Voice drift >60s is a hard constraint** — not configurable. Always chunk 11 Labs generation.
- **HeyGen Avatar 5 API varies by plan** — Playwright bridge needed if API not yet on your tier.
- **No natural pauses in AI voice clone** — community-noted quality floor.
- **Fable 5 eats session tokens faster than Opus** — budget for token burn on long agentic runs.

## In His Words

> "I just typed one prompt into Claude code and walked away. And everything else — the research, the script, the voice, the avatar, the motion graphics — all of it happened on its own." — [~0:20]

> "You can't just generate like four straight minutes of audio because the longer a generation runs, the more the voice starts to drift. So Claude split the script into chunks, just under a minute each, and generated them separately." — [~2:30]

## Steal This For Your Org

1. Build a Voice Playbook for your team's written communications (transcripts → Claude extract → reusable doc)
2. Map your content production pipeline step-by-step; mark which steps have APIs → build order for orchestration prompt
3. Use Playwright as an API bridge when vendors lag (ship the fallback, swap to API when it lands)
4. One-prompt stress test: write a single orchestration prompt for any repeatable deliverable; gaps hit = your automation roadmap

## Mistake to Avoid

Copy the **pattern** (one orchestrator + voice playbook + chunked audio + Playwright fallback), not the exact toolstack — it will keep changing. Voice drift is architectural. HeyGen Avatar 5 API was unavailable until recently. Fable 5 itself was pulled the day the video dropped.

## Source

- **Video:** https://www.youtube.com/watch?v=ONmaDdOBGig · 5:47
- **Chapters:** None
- **Linked:** [AI Automation Society](https://www.skool.com/ai-automation-society) · [Glaido](https://get.glaido.com/nate)
- **Transcript:** [[2026-06-13-nate-herk-daily-transcript]] (partial — Firecrawl unavailable this run)
- **Views:** 84,361 · Likes: 3,620 · Comments: 334
