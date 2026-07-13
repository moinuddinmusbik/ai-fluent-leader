---
title: "Nate Herk Daily Implementation Playbook — 2026-07-12"
date: 2026-07-12
type: email-archive
lane: implementation
video_title: "Claude Code + Clay Makes Lead Generation Actually Fun"
video_url: https://www.youtube.com/watch?v=zyvdl__Ywfk
duration: "18:03"
video_type: BUILD
---

# Implementation Playbook — 2026-07-12

**Video:** [Claude Code + Clay Makes Lead Generation Actually Fun](https://www.youtube.com/watch?v=zyvdl__Ywfk) · 18:03 · BUILD

**Stack:** Claude Code · Clay · Clay Plugin (Marketplace) · /goal (Dynamic Workflow) · Sub-Agents · VS Code

---

## What He Builds

- **The System:** A plain-English lead generation machine connecting Claude Code to Clay. Claude Code orchestrates in natural language; Clay sources and enriches B2B leads through its multi-vendor waterfall.
- **The Demo:** Live HVAC example — 50 fully enriched leads (emails, phone numbers, pain points, recent signals, personalized subject lines and bodies) delivered as a CSV for under $12 in Clay credits.
- **The Full Loop:** Prompt → CSV → import to Clay → map variables → set up sender domains → launch campaign. Two windows, no new UI to learn.

## How It Works (Architecture)

- **Claude Code = Orchestrator:** Reads the goal prompt, understands Clay's API endpoints via the installed plugin, spawns parallel sub-agents by geography.
- **Clay = Data Layer:** Waterfall checks primary B2B data provider → cascades through additional vendors on miss → pushes email match rates from ~30% (single vendor) to 80–90%.
- **Context Files = Voice:** Business profile, case studies, FAQs, proof, offer, website copy — loaded into the Claude Code project. Hard prerequisite for good outreach copy.
- **/goal + Dynamic Verification:** `/goal` keeps Claude working until the end condition is met. Sub-agents debate subject-line quality in verification passes — full enrichment run took ~1 hour; quick pull ~5 min.
- **Clay Campaign Close:** Import CSV → create campaign → map subject/body variables → buy pre-warmed sender domains inside Clay (capped at 30/day) → launch with follow-up sequence.

## Build It Yourself

1. **Create a Clay account** — clay.com, free trial, grab your API key.
2. **Install Clay plugin via terminal only** — `/marketplace` → Install plugin from marketplace → paste Clay marketplace URL → reload plugins.
3. **Authenticate** — Ask Claude: "I just installed this Clay plugin. Can we connect my account? Can you help me authenticate?" Copy-paste auth URL manually if terminal wraps it.
4. **Build your context files** — business-profile.md, case-studies.md, faqs.md, proof.md, offer.md, website-copy.md in a `/context` folder.
5. **Fire the /goal prompt** — specify target avatar, enrichment fields, CTA, "do not stop until done."
6. **Let it run** — Claude spawns parallel sub-agents by city. Quick pull: ~5 min. Full enrichment + verification: ~1 hour. Output is a CSV.
7. **Import CSV into Clay** — Import Data → CSV → new blank table → create campaign → map email subject and body variables → preview.
8. **Set up sending accounts** — Buy pre-warmed domains in Clay's Sender Accounts tab (30 sends/day limit). Add follow-up sequences (day 3, day 7).

## Prompts, Commands & Configs

```
# Install Clay plugin (terminal only)
/marketplace → Install plugin from marketplace → paste Clay URL → reload

# Authenticate
"I just installed this Clay plugin. Can we go ahead and connect my account? Can you help me authenticate?"

# Verify connection
"Check if you can use Clay and tell me what available actions and tools you have."

# /goal prompt (Nate's verbatim HVAC example, 9:08)
/goal
I am looking for some leads. I want 50 enriched leads that are HVAC or home
service companies and we are looking to get in front of decision makers —
business owners, presidents, people that might be decision makers at these companies.
We want fully enriched leads: email addresses, business pain points, anything that's
recently happened in their business, any notable achievements, so that you can also
get me the subject lines and the body for the email. Everything should be super
personalized. The CTA: we want the recipient to say yes to us sending over a
90-second Loom video that explains how our business can help them. Do not stop
until you have all 50 of these leads. Use a dynamic workflow to verify that you've
done everything correctly. Deliver a CSV file — no blank columns. Every lead
should have an email, a subject line, and a body, enriched with other data.

# Context folder structure (prereq)
/context/business-profile.md
/context/case-studies.md
/context/faqs.md
/context/proof.md
/context/offer.md
/context/website-copy.md
```

## Gotchas & Watch-Outs

- **Install via terminal only:** Plugin marketplace install only works in Claude Code CLI terminal — not desktop app or VS Code extension (though those can run it after install).
- **URL wrapping breaks auth link:** Terminal may wrap the auth URL — copy-paste it manually into browser.
- **Verified ≠ deliverable:** Clay marks emails "verified" but bounce rate can still be significant. Run through ZeroBounce or NeverBounce before sending at volume. (Community: @aboutsupplies)
- **$12/50 leads ≠ cheap at scale:** Cold outreach needs 1,000+ contacts/week at ~1% conversion. At $12/50 that's $240+/week minimum in data costs. (Community: @sgladue8346)
- **Clay MCP server gaps:** As of recording, Clay's MCP can't manage campaigns, follow-ups, or sender accounts — those require the Clay UI.
- **Context files are a hard prereq:** Without them Claude produces generic, low-quality copy regardless of data quality.

## Steal This For Your Org

1. **Run a $12 proof-of-concept this week.** Pick one target vertical. Build three context files. Run the /goal prompt. Evaluate the CSV — copy quality tells you immediately if your context is working.
2. **Build your AI context folder like a sales deck.** Business profile + case studies + CTA once in your Claude Code project root → every future campaign inherits it. Highest-leverage doc you can write this week.
3. **Use /goal + "do not stop until done" for overnight runs.** Set a delivery condition (CSV, N records, no blank columns) and let it run while you sleep.
4. **Apply Clay's waterfall logic to any data problem.** Wherever you rely on a single B2B data vendor with poor match rates, adopt the cascade-through-providers pattern — stop on first verified hit.

## Mistake to Avoid

Firing the lead gen machine before you have context files. Even with 90% email match rates, Claude writes mediocre copy if it knows nothing about your business. Build the context files first — campaign quality lives or dies on them.

## In His Words

> "Clay is going to fix the data problem and Claude Code is going to fix the tool problem." — 0:56

> "Do not stop until you have all 50 of these leads for me. Use a dynamic workflow to verify that you've done everything correctly and verify that everything is accurate." — 9:08

## Source & Resources

- **Video:** [Claude Code + Clay Makes Lead Generation Actually Fun](https://www.youtube.com/watch?v=zyvdl__Ywfk) · 18:03
- **Chapters:** 0:00 What We're Building · 0:58 The Data Problem vs The Tool Problem · 3:01 Why Clay and the Waterfall · 4:25 Setting Up Clay and the Plugin · 6:06 Connecting Your Account · 7:26 The Goal Prompt · 9:37 How It Runs and What It Cost · 11:40 The Enriched Data and Email Copy · 13:32 Launching the Campaign in Clay · 17:02 Final Thoughts
- **Linked:** Clay free credits — https://bit.ly/4gzSl9L · Full demo project markdown in Nate's free Skool community
- **Transcript:** [[2026-07-12-nate-herk-daily-transcript]]
