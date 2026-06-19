---
title: "Second Brain Levels"
type: concept
created: 2026-06-18
updated: 2026-06-18
tags: [concept, knowledge-management, claude-code]
sources: [2026-06-18-nate-herk-daily.md]
---

# Second Brain Levels

Nate Herk's 5-level framework for structuring an AI-readable personal/team knowledge base on top of Claude Code (or any agent harness), introduced 2026-06-18.

## The Levels

1. **Router** — a CLAUDE.md/AGENTS.md acting as routing rules ("if you need X, look in folder Y") plus context/projects/decisions folders. Exact-word/file lookup only.
2. **Wiki + memory** — an auto-generated LLM-style markdown wiki (concepts, sources, relationships) plus Claude Code's built-in automemory.
3. **Semantic search** — vector search (Qdrant, Pinecone, Supabase) layered onto specific sub-folders where exact-word routing fails.
4. **Knowledge graph** — relationship graphs (e.g. LightRAG) mapping entities and how they connect.
5. **Always-on brain OS** — continuously syncing, autonomous memory that updates itself without manual ingestion (e.g. Gary Tan's GBrain + GStack).

## Key principle

Layers stack rather than replace each other, and levels should be adopted per-folder, not per-project. Climb a level only when the current level's actual failure mode (exact-word misses, scattered notes, wrong-chunk retrieval, no relationship tracing) shows up in real use — not preemptively. Vector search and knowledge graphs trade completeness for retrieval power, so content that needs to be read in full (e.g. meeting transcripts) should stay un-vectorized.

See [[nate-herk]], [[2026-06-18-nate-herk-daily]].
