# AI-Fluent Leader Wiki — Schema & Operating Manual

This is the schema file for an LLM-maintained personal wiki (second brain) focused on **becoming an AI-fluent leader**. It governs how the LLM agent (local Claude Code sessions AND remote routines) reads, writes, and maintains the wiki. Every interaction in this project follows these rules.

This wiki is the **knowledge layer** that sits behind three remote routines that email the user daily/weekly briefings:

1. **Weekly AI Leadership Stories** — Monday weekly digest of fresh AI-leadership stories (HN, Reddit, Substack, reports).
2. **Nate B Jones Daily Leader Briefing** — Daily summary of Nate B. Jones's latest strategy video/podcast/Substack post.
3. **Nate Herk Daily Implementation Playbook** — Daily summary of Nate Herk's latest implementation video.

After each routine sends its email, it also writes a Karpathy-style wiki page into this repo and pushes it. A local cron pulls the repo into the user's Obsidian vault.

---

## Tooling Conventions (BINDING)

All external side-effects performed by the remote routines — sending email and writing to this repo — MUST go through **Composio MCP via `COMPOSIO_MULTI_EXECUTE_TOOL`**. This is the single, consistent integration surface for the project. Do not use ad-hoc connectors or shell credentials.

| Action | Use | Do NOT use |
|--------|-----|------------|
| Send the briefing email | Composio `GMAIL_SEND_EMAIL` (with `is_html=true`) via `COMPOSIO_MULTI_EXECUTE_TOOL` | the standalone Gmail MCP connector |
| Commit + push wiki pages | Composio `GITHUB_COMMIT_MULTIPLE_FILES` via `COMPOSIO_MULTI_EXECUTE_TOOL` | embedded-PAT `git clone` + `git push` in the sandbox |

**Why git push was failing:** the routines previously did a `git clone $PAT_URL` + `git add/commit/push` inside the remote sandbox. That push silently failed (sandbox networking / PAT scope), so no content ever reached `origin/main` — only the initial scaffold. `GITHUB_COMMIT_MULTIPLE_FILES` commits through the GitHub API on the user's already-active Composio GitHub connection, removing the sandbox `git` dependency and the embedded PAT entirely.

**`GITHUB_COMMIT_MULTIPLE_FILES` call shape** (one atomic commit per ingest):

```
COMPOSIO_MULTI_EXECUTE_TOOL → tool_slug: GITHUB_COMMIT_MULTIPLE_FILES
  owner:   moinuddinmusbik
  repo:    ai-fluent-leader
  branch:  main
  message: "ingest: <routine> <YYYY-MM-DD>"
  upserts: [
    { path: "raw/emails-archive/<YYYY-MM-DD>-<slug>.md", content: "<email body>" },
    { path: "wiki/sources/<YYYY-MM-DD>-<slug>.md",        content: "<source page>" },
    { path: "wiki/entities/<name>.md",                    content: "<full file content>" },
    { path: "wiki/index.md",                              content: "<full updated index>" },
    { path: "wiki/log.md",                                content: "<full updated log>" }
  ]
```

Notes:
- `upserts` replace whole-file content (not patches). For append-style files (`index.md`, `log.md`) the routine must first read current content via `GITHUB_GET_REPOSITORY_CONTENT` (Base64-decode `data.content.content`), append, and upsert the full result.
- `branch` is `main` and already exists, so `base_branch` is not required.
- **Prerequisite:** Composio must have an ACTIVE **Gmail** connection for `GMAIL_SEND_EMAIL` (GitHub is already connected). If absent, the email step will fail until a Gmail account is linked in Composio.

---

## Directory Structure

```
.
├── CLAUDE.md              # This file — the schema (LLM + human co-evolve)
├── raw/                   # Immutable source documents
│   ├── assets/            # Downloaded images, PDFs, attachments
│   └── emails-archive/    # Plain-text copies of the emails the routines sent
├── wiki/                  # LLM-generated and maintained wiki pages
│   ├── index.md           # Master catalog of all wiki pages
│   ├── log.md             # Chronological record of all operations
│   ├── overview.md        # High-level synthesis of the entire wiki
│   ├── sources/           # One summary page per ingested source (each email = one source)
│   ├── entities/          # Pages for people, orgs, tools, projects
│   ├── concepts/          # Pages for ideas, frameworks, theories, topics
│   └── analyses/          # Comparisons, syntheses, query results
└── .obsidian/             # Obsidian config (not managed by LLM)
```

## Ownership Rules

| Layer | Owner | Mutability |
|-------|-------|------------|
| `raw/` | Human + routines (append-only) | Immutable once written |
| `wiki/` | LLM | LLM creates, updates, and deletes pages freely |
| `CLAUDE.md` | Both | Human and LLM co-evolve collaboratively |

---

## Page Conventions

### Frontmatter

Every wiki page MUST have YAML frontmatter:

```yaml
---
title: "Page Title"
type: source | entity | concept | analysis | overview
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [tag1, tag2]
sources: [filename1.md, filename2.md]  # raw/ sources this page draws from
routine: "Weekly AI Leadership Stories" | "Nate B Jones Daily Leader Briefing" | "Nate Herk Daily Implementation Playbook" | null
---
```

### Wikilinks

Use Obsidian-style wikilinks for all cross-references: `[[page-name]]`. This enables Obsidian's graph view and backlink tracking.

### File Naming

- All lowercase, hyphens for spaces: `chief-ai-officer.md`, `nate-b-jones.md`
- Source summaries match the email's date and routine slug: `wiki/sources/2026-05-21-nate-b-jones-daily.md`
- No spaces in filenames. No special characters except hyphens.

### Page Types

**Source pages** (`wiki/sources/`): One per ingested email/source. Contains:
- Metadata (routine name, date, original URL[s])
- Summary (2-5 paragraphs)
- Key takeaways (bulleted)
- Notable quotes / data points
- Links to entity/concept pages created or updated from this source

**Entity pages** (`wiki/entities/`): People, organizations, tools, projects. Examples: `nate-b-jones.md`, `nate-herk.md`, `openai.md`, `anthropic.md`, `mckinsey.md`. Contains:
- Description
- Key facts
- Relevance to AI-fluent-leadership themes
- Links to source pages and concept pages

**Concept pages** (`wiki/concepts/`): Ideas, frameworks, mental models. Examples: `ai-fluency.md`, `chief-ai-officer.md`, `ai-strategy-vs-implementation.md`, `claude-code-workflows.md`. Contains:
- Definition / explanation
- Key aspects or sub-topics
- Connections to other concepts
- Sources that discuss this concept

**Analysis pages** (`wiki/analyses/`): Filed query results, comparisons, syntheses. Contains:
- The question or framing
- The analysis
- Sources and pages consulted
- Conclusions or open questions

**Overview** (`wiki/overview.md`): High-level synthesis of the entire wiki. Updated periodically.

---

## Operations

### 1. INGEST (called by remote routines)

Triggered automatically after a routine sends its email (which itself goes through Composio `GMAIL_SEND_EMAIL` — see [Tooling Conventions](#tooling-conventions-binding)). The routine appends a STEP 7 to its workflow that does the following:

1. Assemble the email HTML/markdown body for `raw/emails-archive/YYYY-MM-DD-<routine-slug>.md`.
2. Assemble a source page for `wiki/sources/YYYY-MM-DD-<routine-slug>.md` with the structured summary.
3. Assemble create/update content for entity pages in `wiki/entities/` for any people, orgs, tools mentioned.
4. Assemble create/update content for concept pages in `wiki/concepts/` for key ideas covered.
5. Read current `wiki/index.md` (`GITHUB_GET_REPOSITORY_CONTENT`), append the new line(s) under the right section, keep the full text.
6. Read current `wiki/log.md`, append a dated entry, keep the full text.
7. Commit all of the above in ONE atomic commit via Composio `GITHUB_COMMIT_MULTIPLE_FILES` (`message: "ingest: <routine> <date>"`). No `git` CLI, no embedded PAT.

### 2. QUERY (called by local Claude Code sessions)

Triggered when the user asks a question against the wiki.

1. Read `wiki/index.md` to identify relevant pages.
2. Read the relevant wiki pages (not raw sources — the wiki IS the compiled knowledge).
3. Synthesize an answer with `[[wikilinks]]` to pages consulted.
4. Optionally file the answer as an analysis page in `wiki/analyses/`.
5. Log the query in `wiki/log.md`.

### 3. LINT

Checks:
- Orphan pages (no inbound links)
- Stub pages (created but underdeveloped)
- Contradictions between pages
- Stale claims superseded by newer sources
- Missing pages (concepts/entities mentioned but lacking their own page)
- Missing cross-references between related pages
- Index accuracy
- Broken wikilinks

### 4. EVOLVE

The human or LLM can propose changes to this schema file at any time.

---

## Index & Log

### index.md

```markdown
# Wiki Index

## Sources
- [[source-page]] — one-line summary (YYYY-MM-DD)

## Entities
- [[entity-page]] — one-line description

## Concepts
- [[concept-page]] — one-line description

## Analyses
- [[analysis-page]] — one-line description (YYYY-MM-DD)
```

### log.md

Append-only. Each entry:

```markdown
## [YYYY-MM-DD] operation | Title
- **Operation:** ingest / query / lint / evolve
- **Source:** routine name (if applicable)
- **Details:** what was done
- **Pages touched:** [[page1]], [[page2]]
```

---

## Themes This Wiki Tracks

The user's goal is to become an **AI-fluent leader** and crack AI leadership roles (CAIO, Head of AI, AI strategy). The wiki therefore prioritizes:

- **Strategy** (Nate B. Jones lane): enterprise AI trends, leadership frameworks, executive-focused analysis
- **Implementation** (Nate Herk lane): Claude Code workflows, automation, hands-on builds
- **Job market signals**: CAIO hiring, AI leadership requirements, skill-gap data
- **Reports**: IBM / Deloitte / Gartner / McKinsey / WEF on AI leadership

When ingesting, tag pages with `strategy`, `implementation`, `jobs`, or `report` as appropriate.

---

## Interaction Protocol

Every interaction in this project follows one of the four operations above. The LLM:

1. Determines which operation applies.
2. Follows the corresponding workflow.
3. Updates `index.md` and `log.md` as specified.
