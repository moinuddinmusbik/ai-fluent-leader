---
title: "Nate Herk Daily Implementation Playbook — 2026-07-04"
date: 2026-07-04
routine: nate-herk-daily
recipient: moinuddin.musbik@gmail.com
subject: "Nate Herk Daily Implementation Playbook — 2026-07-04"
video_type: BUILD
---

# Nate Herk Daily Implementation Playbook — 2026-07-04

*Email sent: 2026-07-05 (routine run date)*

---

## Email Body (HTML — rendered as markdown copy)

**AI-Fluent Leader · Implementation Playbook**  
**Fable 5 + Karpathy's LLM Wiki is Basically Cheating**  
Nate Herk · Published: 2026-07-04 · 14:35 · BUILD

**Stack:** Fable 5 · Claude Code · Obsidian · Karpathy LLM Wiki schema · Opus 4.8

---

### What He Builds

- **An LLM wiki for your AIOS:** Local Obsidian vault where Claude Code ingests raw sources (PDFs, URLs, transcripts) and splits them into cross-linked markdown wiki pages. AI maintains index, log, and routing rules.
- **Live demo — YouTube transcript brain:** Ingested all his YouTube videos; Fable 5 turned raw connections into a clickable HTML visualization showing concept relationships — something Opus failed to produce cleanly after a full day.
- **Live demo — competitive benchmark wiki:** Ingested Claude Fable 5 system card (PDF) + OpenAI GPT-5.6 Soul article (URL) → 20 cross-linked wiki pages + surfaced: OpenAI benchmarked against Mythos *preview* (not final), different harnesses → numbers incomparable. That cross-source insight only emerged because both documents lived in the same wiki.

### How It Works (Architecture)

- `raw/`: Drop sources (PDFs, URLs, transcripts)
- `wiki/`: AI output — 1 source → 5–50 cross-linked pages; subfolders emerge dynamically
- `index.md` + `log.md`: AI navigation layer; routing rules tell agents exactly where to look
- Flat vs. structured: meeting wikis stay flat; topic-rich wikis grow subfolders
- Model split: Opus 4.8 for ingest, Fable 5 for synthesis/querying

### Build It Yourself (7 steps — see wiki source page for full detail)

1. Install Obsidian, create a new vault
2. Open Claude Code inside vault folder
3. Copy full Karpathy LLM Wiki gist
4. Paste gist + setup prompt into Claude (see Prompts below)
5. Ingest first source (PDF into raw/ or URL prompt)
6. Switch to Opus 4.8 for all future ingests
7. Reopen Obsidian Graph View

### Prompts

Setup: *"You are now my LM wiki agent. Implement this exact idea file as my complete second brain. Guide me step by step. Create the claude.md schema with my full rules. Set up the index, the log, define folder conventions, and show me the first ingest example. From now on, every interaction follows the schema."*

### Gotchas

- Model drift breaks structure — never switch models mid-wiki
- Large PDFs: 10–12 min, 20+ pages
- Flat can be smarter than structured
- Obsidian is local-first (no out-of-box mobile sync)

### Steal This For Your Org

1. Decision wiki this week (3–5 docs, 15 min setup)
2. Auto-ingest meeting transcripts → flat wiki
3. Competitive-intelligence wiki (vendor cross-linking)
4. Karpathy gist as enterprise CLAUDE.md template

### Mistake to Avoid

Using Fable for ingest. [7:48]: "Fable is probably overkill for this. If you want to switch this back to Opus, run the ingest and ingest future documents with Opus — that's probably a better call." Compound: model drift on ingest breaks structural consistency.

### In His Words

> "The impressive thing about this isn't the fact that Fable was able to ingest all of it. It's what Fable can do once you've given it the power of all of this data. We all know that data is king. Context is king." — [1:13]

> "Inside the wiki, what happens is there are routing rules set up so that our agents are able to figure out where to look for what specific thing." — [12:38]

### Source & Resources

- Video: https://www.youtube.com/watch?v=hQvwMj7IJe4 · 14:35 · 44,622 views
- Karpathy LLM Wiki Gist: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
