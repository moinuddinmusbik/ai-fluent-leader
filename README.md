# AI-Fluent Leader Vault

A Karpathy-style LLM-maintained personal wiki for becoming an AI-fluent leader.

This is both:

- An **Obsidian vault** — open `/Users/moinuddinmohammed/Documents/ai-fluent-leader/` as a vault in Obsidian.
- A **git repo** — three remote Claude Code routines commit wiki pages here after sending their daily/weekly emails; a local cron pulls the latest into your machine.

See [`CLAUDE.md`](CLAUDE.md) for the full operating manual.

## Routines that write to this repo

| Routine | Schedule | What it adds |
|---------|----------|--------------|
| Weekly AI Leadership Stories | Mondays | 1 source page + entity/concept updates per fresh story |
| Nate B Jones Daily Leader Briefing | Daily | 1 source page per new episode + concept/entity updates |
| Nate Herk Daily Implementation Playbook | Daily | 1 source page per new video + concept/entity updates |

## Directory map

```
raw/                # immutable source archive
  assets/
  emails-archive/   # plain-text copies of the emails routines sent
wiki/               # LLM-maintained pages
  index.md
  log.md
  overview.md
  sources/          # one page per email
  entities/         # people, orgs, tools
  concepts/         # ideas, frameworks
  analyses/         # syntheses, queries
```
