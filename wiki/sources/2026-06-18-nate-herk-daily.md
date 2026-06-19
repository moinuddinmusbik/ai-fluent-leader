---
title: "Every Level of a Claude Second Brain Explained"
type: source
created: 2026-06-18
updated: 2026-06-18
tags: [implementation, deep-dive, second-brain, claude-code, knowledge-management, semantic-search, knowledge-graph]
sources: []
routine: "Nate Herk Daily Implementation Playbook"
---

# Every Level of a Claude Second Brain Explained

**Date:** 2026-06-18  
**Source:** [[nate-herk]] · YouTube [DTCyvo6cC54](https://www.youtube.com/watch?v=DTCyvo6cC54)  
**Duration:** 31:00 · 51,827 views  
**Type:** DEEP-DIVE  
**Transcript:** Full transcript extracted via Firecrawl (622 raw segments, deduped to 311, ends 30:55 — matches the 31:00 runtime, no duplicate pass detected).

## What It Is

A 5-level second-brain framework, walked through using Nate's real "Herk2" project, for structuring an AI-readable personal/team knowledge base on top of Claude Code (or any agent harness):

- **Level 1 — Router:** a CLAUDE.md acting as routing rules ("if you need X, look in folder Y") plus context/projects/decisions folders. Exact-word/file lookup only.
- **Level 2 — Wiki + memory:** adds an auto-generated LLM-style markdown wiki (concepts, sources, relationships) and Claude Code's built-in automemory. This is where Nate runs almost his entire production system.
- **Level 3 — Semantic search:** vector search (Qdrant, Pinecone, Supabase) layered onto specific sub-folders — searching by meaning instead of exact words.
- **Level 4 — Knowledge graph:** relationship graphs (e.g. LightRAG) mapping entities and how they connect ("Jordan works at Acme," "Acme is endorsed by Postpilot").
- **Level 5 — Always-on brain OS:** Gary Tan's GBrain + GStack — continuously syncing, autonomous memory that updates itself without manual ingestion.

## How It Works (Architecture)

- **Router, not just role:** CLAUDE.md (or AGENTS.md for Codex) is loaded every session and must contain explicit routing rules, not just background — otherwise the agent will ask for context it should already be able to find rather than search the whole project.
- **Layers stack, don't replace:** the base folder skeleton (context/, projects/, decisions/) stays constant; each level adds on top — wiki, then vector index, then knowledge graph, then autonomous sync.
- **Tool-agnostic by design:** because it's "just files and folders," the same second brain works across Claude Code, Codex (via a parallel AGENTS.md), and his custom Hermes agent — point each harness's memory file at the same underlying markdown.
- **Mixed levels per folder:** a single project doesn't have to sit at one level — his YouTube-transcript wiki runs Level 2/3 (LLM wiki + semantic "smart lookup") while his quarterly-priorities (OTA) folder stays flat Level 1.
- **Work backwards from the question:** design storage format around how you'll actually query it later — vector chunking only retrieves the top-N "similar" chunks (bad for "summarize the whole meeting"), while a single markdown file read in full is more accurate for anything needing complete context.

## The Verdict

Nate's own production second brain runs mostly at Level 2 — CLAUDE.md router + markdown context/projects/decisions + an LLM wiki, with automemory on — not because higher levels are technically out of reach, but because he hasn't hit a pain point Level 2 doesn't already solve. His explicit framing: don't climb levels for their own sake. Climb only when the current level's actual failure mode (exact-word misses, scattered notes, wrong-chunk retrieval, no relationship tracing) shows up in your day-to-day use.

## When To Use It (and When Not)

- **Level 1:** if you're constantly re-explaining context to your agent or need exact-word/filename lookup.
- **Level 2:** once you have 30+ notes and keep forgetting what's in them — where Nate runs almost everything.
- **Level 3:** only for sub-folders where exact-word routing keeps "whiffing" on notes you know exist — never vectorize content you need to read in full, like meeting transcripts you want fully summarized.
- **Level 4:** if you need to trace relationship chains (who works where, who competes with whom) — skip it if your work isn't relationship/CRM-heavy; Nate plays with it but doesn't run it daily.
- **Level 5:** only if you're running agents continuously/offline and want memory to sync itself — Nate flags the risk of low-quality, uncurated data doing "more damage than good" once ingestion is fully autonomous.

## Set It Up

1. **Write a router, not a bio.** Start every project with a CLAUDE.md (or AGENTS.md on Codex) with explicit routing rules: "if you need X, look in folder Y."
2. **Build the baseline skeleton.** context/ (always-true background), projects/ (one file/folder per ongoing project or client), decisions/ (a running, dated decision log).
3. **Turn on automemory.** Run `/memory` in Claude Code to enable it; the agent writes and updates memory.md on its own. Point Codex's AGENTS.md at the same memory.md to share it across harnesses.
4. **Ingest into a wiki once you hit 30+ notes.** Build an LLM-style markdown wiki (concepts/sources/relationships pages); Nate did this for his YouTube transcripts and meeting notes, viewable for free in Obsidian since it just renders markdown folders.
5. **Add semantic search only where routing fails.** Layer Qdrant, Pinecone, or Supabase vector search onto the specific sub-folder that's missing notes on exact-word search — not the whole project.
6. **Add a knowledge graph only for relationship questions.** Build a LightRAG-style entity/relationship layer on top of the same markdown data when you need to trace chains like "who works at this company."
7. **Decide per-folder, not per-project.** Mix levels deliberately: keep flat, evergreen data (like quarterly priorities) at Level 1 while letting high-volume, search-heavy data (like transcripts) run at Level 2/3.

## Prompts & Configs

From what Nate says on screen + the file/folder names he shows — not OCR of his editor, and no verbatim CLAUDE.md or skill source was read aloud.

```
/memory                     # toggle Claude Code automemory on/off

CLAUDE.md                   # router file loaded every session (Claude Code)
AGENTS.md                   # same router content, for Codex / other harnesses
memory.md                   # auto-written + updated by automemory

Folder skeleton (Level 1+):
  context/        # always-true background (about-me, stack, conversations)
  projects/       # one file/folder per ongoing project or client
  decisions/      # running decision log, dated entries

Level 2 adds:
  wiki/           # LLM-style markdown wiki (concepts, sources, relationships)
  references/

Level 3 adds (per sub-folder, not the whole project):
  vector-index/   # Qdrant / Pinecone / Supabase semantic search

Level 4 adds:
  knowledge-graph/  # e.g. LightRAG -- entities + relationships

Skill: "grill me" (customized from Matt Pocock) -- interviews you on a topic,
won't stop until it has full context, writes a brainstorm file for ingestion
into the knowledge graph.
```

## Gotchas & Watch-Outs

- **Don't vectorize what you need in full:** Nate's own example — a meeting transcript chunked for semantic search only returns the top-matching chunks, so "summarize March 5th" can miss the actual highest-sales week if it's not in the top-retrieved chunks. Full markdown read beats vector search whenever you need complete context.
- **Wiki backlinks ≠ knowledge graph:** Nate is explicit that his Level 2 wiki's links are just backlinks, not typed relationships ("endorsed by," "competitor of") — Obsidian's graph view doesn't give you Level 4 capability.
- **Data privacy:** anything ingested goes to Anthropic when processed through Claude — Nate flags this mid-video and says sensitive/client data may need open-source or local models instead.
- **Community pushback:** commenters note the "grill me" skill isn't easy to actually locate via the link given (@JaeyeokYoon); his "three-dimensional" embedding-space explanation is a simplification — real models use far more dimensions (@funkdoc94); and notes need to stay atomic/focused or Level 4 relationship graphs get "messy and meaningless" (@user-e3l9d).
- **Knowledge graphs can be less efficient, not more:** Nate notes a graph layer still has to read an entire file even for a narrow question — sometimes a well-routed wiki is faster.

## Steal This For Your Org

1. **Audit your CLAUDE.md/AGENTS.md this week** — check it has explicit routing rules ("if you need X, look in folder Y"), not just a role description. That alone stops most "I don't have enough context" replies.
2. **Turn on automemory** — run `/memory` in your next Claude Code session and review after a few days whether what it's capturing is accurate enough to trust.
3. **Pick one underperforming folder** — test semantic search (Qdrant/Pinecone/Supabase) on just the folder where your agent keeps missing notes you know exist, before vectorizing anything else.
4. **Write down the pain point before building anything new** — before adding a knowledge graph or autonomous memory layer, confirm Level 1/2 is actually failing you; if it isn't, don't build it yet.

## Mistake to Avoid

Treating "more sophisticated" as "better." Nate deliberately runs most of his own production second brain at Level 2, not Level 4 or 5, because he hasn't hit a real pain point those levels would solve. Jumping straight to a knowledge graph or an autonomous GBrain setup before you've actually felt where simple CLAUDE.md routing or a markdown wiki falls short just adds complexity — and, at Level 5 especially, the risk of low-quality data flooding your agent's context — without fixing anything.

## In His Words

> "You kind of have to work backwards. You want to reverse engineer based on the question... how it's going to be accessed and recalled determines the way that you put it in in the first place." — 2:28

> "If you don't have a pain point in your system, then I don't really think there's a need to go experiment or develop a new sort of architecture. If there's not pain, then why create more?" — 4:08

## Linked Pages

- [[nate-herk]]
- [[second-brain-levels]]
- [[claude-code]]
- [[context-engineering]]

## Source & Chapters

- **Video:** [Every Level of a Claude Second Brain Explained](https://www.youtube.com/watch?v=DTCyvo6cC54) · 31:00 · 51,827 views
- **Chapters:** 0:00 Intro · 3:25 The 5 Levels Overview · 4:19 Level 1 · 8:11 Level 2 · 13:03 Level 3 · 19:27 Level 4 · 25:25 Level 5 · 28:48 Finding Your Level · 30:41 Final Thoughts
- **Linked resources:** No substantive external article/repo links in the description (only Nate's own Skool community and affiliate links).
