---
title: "Fable 5 + Karpathy's LLM Wiki is Basically Cheating"
date: 2026-07-04
type: source
lane: implementation
video_url: https://www.youtube.com/watch?v=hQvwMj7IJe4
duration: "14:35"
video_type: BUILD
tags: [llm-wiki, obsidian, claude-code, fable-5, karpathy, second-brain, knowledge-base]
links:
  - [[nate-herk]]
  - [[2026-07-04-nate-herk-daily-transcript]]
---

# Fable 5 + Karpathy's LLM Wiki is Basically Cheating

**Video:** [https://www.youtube.com/watch?v=hQvwMj7IJe4](https://www.youtube.com/watch?v=hQvwMj7IJe4)  
**Published:** 2026-07-04 · **Duration:** 14:35 · **Type:** BUILD  
**Creator:** [[nate-herk]]  
**Transcript:** [[2026-07-04-nate-herk-daily-transcript]]

---

## Stack

- **Fable 5** — used for synthesis and reasoning over the built wiki
- **Claude Code** — the agentic loop that runs ingest, writes wiki pages, maintains index/log
- **Obsidian** — local markdown vault as the front-end; Graph View shows concept connections
- **Karpathy LLM Wiki schema** — the CLAUDE.md pattern (gist with 5,000+ stars); copied verbatim as the project schema
- **Opus 4.8** — recommended for the ingest step (Fable is overkill for reading/writing wiki pages)

---

## How It Works (Architecture)

- **`raw/` folder:** Drop source files here (PDFs, URLs, transcripts). Claude Code reads everything during ingest.
- **`wiki/` folder:** AI output — one source becomes 5–50 cross-linked wiki pages. Subfolders (concepts/, techniques/, tools/, entities/) emerge dynamically based on what the AI finds in the data.
- **`index.md`:** Table of contents with backlinks; AI navigation layer.
- **`log.md`:** Running ingest history — every ingest adds a dated entry.
- **CLAUDE.md schema:** Defines routing rules, folder conventions, ingest behavior. Based directly on the Karpathy gist.
- **Routing rules:** The key reason querying works — tell the AI exactly which file to check for which topic. Prevents the agent from having to scan the entire vault.
- **Flat vs. structured:** Wikis for meeting recordings stay flat (no subfolders). Topic-rich wikis (YouTube transcripts, research) grow structured subfolders dynamically.
- **Model split:** Opus 4.8 for all ingest writes; Fable 5 for reasoning and synthesis over the completed wiki.

---

## Build It Yourself

1. **Install Obsidian, create a new vault** — Point Obsidian at an empty folder on your machine.
2. **Open Claude Code inside the vault folder** — `cd path/to/your-vault`, then launch Claude Code.
3. **Copy the full Karpathy LLM Wiki gist** — https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f (5,000+ stars, April 2026). Copy the entire markdown content.
4. **Paste gist + setup prompt into Claude Code:**
   > "You are now my LM wiki agent. Implement this exact idea file as my complete second brain. Guide me step by step. Create the claude.md schema with my full rules. Set up the index, the log, define folder conventions, and show me the first ingest example. From now on, every interaction follows the schema."
5. **Claude creates the scaffold** — CLAUDE.md, index.md, log.md, raw/, wiki/ folders appear.
6. **Ingest first source** — Either drag a PDF into raw/ and say "ingest everything in raw", or paste a URL and say "read this article and ingest it into our wiki."
7. **Switch to Opus 4.8 for all future ingests** — Save Fable for synthesis and querying over the completed wiki.
8. **Reopen Obsidian Graph View** — See your wiki as a visual concept graph; grows with every ingest.

---

## Prompts, Commands & Configs

```
# SETUP PROMPT (paste after the full Karpathy gist text) — [7:21]
"You are now my LM wiki agent. Implement this exact idea file as my
complete second brain. Guide me step by step. Create the claude.md
schema with my full rules. Set up the index, the log, define folder
conventions, and show me the first ingest example. From now on, every
interaction follows the schema."

# INGEST PROMPT (URL variant) — [~10:30]
"Read this article: [URL] and ingest it into our wiki.
Also, I dropped a PDF in the raw folder. Ingest that too."

# SYNTHESIS PROMPT (Fable step, after wiki is built) — [1:13]
"Turn this wiki into an HTML that shows how all these concepts connect.
Make it simple enough for a beginner — not overwhelming, just clickable."
```

---

## Gotchas & Watch-Outs

- **Model drift breaks wiki structure** (community signal from @joehogans4494): Switching models mid-wiki destroys structural consistency. "Every model has its own signature. Model X generates 5 markdowns, model Y generates 20." Pick one model for ingest and never change it.
- **Large PDFs create sprawl:** The Claude Fable 5 system card ingestion took 10–12 minutes and created 20 wiki pages. Scale expectations accordingly.
- **Flat can be smarter than structured:** If the AI struggles to navigate, remove subfolders. Meeting-transcript wikis stay flat intentionally.
- **Obsidian is local-first:** No out-of-the-box mobile or cross-device sync; requires Obsidian Sync or a git-based workaround.

---

## Steal This For Your Org

1. **Decision wiki this week:** Collect 3–5 relevant docs on any re-litigated topic into raw/, run the setup prompt. Under 15 minutes to a cross-linked knowledge base.
2. **Auto-ingest meeting transcripts:** Every meeting transcript → raw/ → flat wiki. After 4 weeks, Fable can surface cross-meeting threads.
3. **Competitive-intelligence wiki:** Ingest system cards, press releases, analyst notes for every AI vendor you're evaluating. Cross-linking surfaces benchmark methodology discrepancies.
4. **Use the Karpathy gist as your enterprise CLAUDE.md template:** Adapt it for your team's folder conventions rather than writing from scratch — drops setup from days to 5 minutes.

---

## Mistake to Avoid

Running every ingest with Fable. Nate at [7:48]: *"Fable is probably overkill for this. It's about what Fable does **after** you have all that data in there. If you want to switch this back to Opus, run the ingest and ingest future documents with Opus — that's probably a better call."* Pattern: Opus 4.8 for all ingest, Fable for all synthesis and querying. Compound risk: model drift on ingest means switching models breaks wiki structural consistency.

---

## In His Words

> "The impressive thing about this isn't the fact that Fable was able to ingest all of it. It's what Fable can do once you've given it the power of all of this data. We all know that data is king. Context is king." — [1:13]

> "Inside the wiki, what happens is there are routing rules set up so that our agents are able to figure out where to look for what specific thing — like the data that it's looking for — because they can look at the index and look through potentially multiple wikis." — [12:38]

---

## Source & Resources

- **Video:** [Fable 5 + Karpathy's LLM Wiki is Basically Cheating](https://www.youtube.com/watch?v=hQvwMj7IJe4) · 14:35 · 44,622 views
- **Chapters:** 0:00 The LLM Wiki Demo · 1:13 What Fable Does With the Data · 2:58 Multiple Wikis in My AI OS · 5:09 Where This Started + Obsidian Setup · 7:05 The Setup Prompt · 7:59 Flat vs Structured Wikis · 9:49 Ingesting Two Sources · 12:38 Why It Works: Routing · 14:18 Final Thoughts
- **Karpathy LLM Wiki Gist:** https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f (5,000+ stars · April 2026)
