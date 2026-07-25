---
title: "2026-07-24 · Nate B Jones Daily"
date: 2026-07-24
type: source
creator: "[[nate-b-jones]]"
lens: FRAMEWORK
video_url: "https://www.youtube.com/watch?v=EuVvLwWZ5wc"
substack_url: "https://natesnewsletter.substack.com/p/use-ai-sensitive-files"
duration: "13:40"
transcript: unavailable
tags: [nate-b-jones, framework, privacy, shadow-ai, data-minimization, airlock]
---

# 2026-07-24 · Nate B Jones Daily: How to Use AI on Files You're Not Allowed to Upload

**FRAMEWORK lens** · [[nate-b-jones]] · 2026-07-24

> *Transcript unavailable (Firecrawl panel did not render after two attempts); brief grounded on Substack preview and video description.*

---

## The Big Idea

"Don't upload sensitive files to AI" is good advice that doesn't answer the real question: *how do I finish the work?* Organizations have created a structural privacy gap — managers demand AI productivity gains while IT bans the tools that deliver them — and left employees to invent a file-by-file data-handling process without guidance. The solution is **[[task-driven-data-minimization]]**: deciding what the model needs to see based on the specific job at hand, then stripping everything else before any data leaves the machine.

---

## The Framework: Begin with the Job

Named framework: **[[task-driven-data-minimization]]** / "Begin with the Job"

- **Reframe the question:** Don't ask "what's sensitive in this file?" Ask "what does *this specific task* need the model to see?" Relevance is task-dependent — no single "clean copy" can be a permission slip for every future use.
- **Strip to the task, not to a template:** Nate's on-device Mac app *Airlock* implements this mechanically — it identifies protected terms, removes only what the model doesn't need for the defined job, and rebuilds a clean file without touching the original.
- **Route the clean copy appropriately:** A sanitized file is not authorization — it is a reduced-risk copy. You still decide which model tier it goes to (on-device, private cloud, frontier) based on residual data.
- **Design the approved path to win the clock:** The two-minute test — time the compliant route against the consumer tool — predicts what employees under deadline pressure will actually use. If the gap is large, shadow AI is the default.

---

## How It Works

1. Define the task output first (what must the model produce?)
2. Strip to necessary context only via Airlock or equivalent
3. Rebuild, don't redact — removes inference-enabling structure, not just visible values
4. Route the clean copy to the appropriate model tier by residual risk
5. Human reviews the output before it moves externally

---

## Where It Applies

- Professional services under dual mandate (auditors, lawyers, consultants with client files)
- Any enterprise where the approved AI path was designed for 2023-era capability
- High-sensitivity verticals: finance, HR, healthcare, legal
- Organizations scaling AI without updating governance

---

## Receipts

- **Auditor dilemma (community-sourced):** A community member called client-file AI "a game changer" blocked by privacy obligation; safe alternatives had "far less intelligence" or were "priced astronomically."
- **Verizon shadow AI data (chapter 09:26):** Enterprise research documenting shadow AI at work is widespread and accelerating.
- **The two-mandate dynamic:** Privacy consequence is abstract, delayed, shared. Manager disappointment is immediate, personal, and easy to understand. Under those incentives, employees follow the manager over IT policy.
- **Airlock (shipped product):** On-device Mac app that strips protected terms and rebuilds a clean copy — no cloud upload, no account required. The fact it shipped validates the framework at product level.

---

## What It Means For You

1. **Run the two-minute test.** Time the approved path vs. the consumer tool. If gap > 60–90s, compliance rate is lower than the policy assumes.
2. **Replace "don't upload" with task-level decision rules.** For top three sensitive workflows, document which fields the task requires vs. which can be stripped.
3. **Build or adopt a sanitization layer before the next AI rollout.** Mechanical data minimization must not depend on employee memory under deadline.
4. **Audit shadow AI before the compliance event.** Almost always caused by the approved path being too slow or too expensive — fixable before an incident.

---

## Mistake to Avoid

Treating "don't upload sensitive files" as a complete privacy policy. It names what must not happen but leaves employees to invent the process for how work gets done. Under deadline pressure, most reach for the fastest tool — rarely the approved one.

---

## Source

- **Video:** [How to Use AI on Files You're Not Allowed to Upload](https://www.youtube.com/watch?v=EuVvLwWZ5wc) · 13:40
- **Substack:** [Use AI on Sensitive Files You Can't Upload](https://natesnewsletter.substack.com/p/use-ai-sensitive-files) (preview; full post paid)
- **Chapters:** 00:00 The file I would never upload · 00:39 Why the warning stops too soon · 01:16 Airlock demo and protected terms · 02:39 Keep or cut: what the model actually needs · 04:03 Rebuild the file instead of redacting it · 04:50 Hand the clean copy to a frontier model · 05:57 Why this suddenly feels urgent · 07:45 What people in my community really do · 09:26 Verizon on shadow AI at work · 10:09 Security fatigue and better defaults · 11:06 Redaction that keeps the work useful · 12:44 Begin with the job
