---
title: "Nate B Jones Daily Leader Briefing — 2026-07-24"
date: 2026-07-24
type: email-archive
routine: nate-b-jones-daily
lens: FRAMEWORK
---

# Nate B Jones Daily Leader Briefing — 2026-07-24

**AI-Fluent Leader · Strategy Brief**
**Title:** How to Use AI on Files You're Not Allowed to Upload
**Published:** 2026-07-24 · YouTube · Substack · FRAMEWORK

---

## The Big Idea

"Don't upload sensitive files to AI" is good advice that doesn't answer the real question: *how do I finish the work?* Nate argues that organizations have created a structural privacy gap — managers demand AI productivity gains while IT bans the tools that deliver them — and left employees to invent a file-by-file data-handling process without guidance, training, or tooling. The solution is not better compliance reminders; it is **task-driven data minimization**: deciding what the model needs to see based on the specific job at hand, then stripping everything else before any data leaves the machine.

---

## The Framework: Begin with the Job

- **Reframe the question:** Don't ask "what's sensitive in this file?" Ask "what does *this specific task* need the model to see?" Relevance is task-dependent; no single "clean copy" can be a permission slip for every future use.
- **Strip to the task, not to a template:** Nate's on-device Mac app *Airlock* implements this mechanically — it identifies protected terms, removes only what the model doesn't need for the defined job, and rebuilds a clean file without touching the original.
- **Route the clean copy appropriately:** A sanitized file is not authorization — it is a reduced-risk copy. You still decide which model tier it goes to (on-device, private cloud, frontier) based on what residual data it contains.
- **Design the approved path to win the clock:** The two-minute test — time the compliant route against the consumer tool — predicts what employees under deadline pressure will actually use. If the gap is large, shadow AI is the default, not the exception.

---

## How It Works

1. Define the task output first — what does the model need to produce?
2. Strip only what the task doesn't require; keep what's load-bearing for the model's reasoning.
3. Rebuild, don't redact — removes inference-enabling structure, not just visible values.
4. Route the clean copy to the appropriate model tier by residual risk.
5. Review the output before it moves externally — automation handles stripping; human judgment holds the final gate.

---

## Where It Applies

- Professional services under dual mandate (auditors, lawyers, consultants with client files)
- Any enterprise where the approved AI path was designed for 2023-era capability
- High-sensitivity verticals: finance, HR, healthcare, legal
- Organizations scaling AI without updating governance — most valuable before the compliance event

---

## Receipts

- **The auditor dilemma (community-sourced):** A Nate community member called client-file AI "a game changer" blocked by privacy obligation; safe alternatives had "far less intelligence" or were "priced astronomically."
- **Verizon shadow AI data (chapter 09:26):** Enterprise research documenting shadow AI adoption is widespread and accelerating.
- **The two-mandate dynamic:** Privacy consequence is abstract, delayed, shared. Manager disappointment is immediate, personal, and easy to understand. Under those incentives, employees follow the manager.
- **Airlock:** On-device Mac app that strips protected terms and rebuilds a clean copy — no cloud upload, no account required. Shipped product validates the framework.

---

## What It Means For You

1. **Run the two-minute test.** Time the approved path vs. the consumer tool. If the gap exceeds 60–90 seconds, compliance rate is lower than the policy assumes.
2. **Replace "don't upload" with task-level decision rules.** For your top three sensitive workflows, document which fields are necessary for the task vs. strippable. Give employees a decision tree, not a prohibition.
3. **Build or adopt a sanitization layer before your next AI rollout.** The mechanical part of data minimization must not depend on employee memory under deadline pressure.
4. **Audit shadow AI now — before the compliance event.** The reason is almost always that the approved path is too slow or too expensive: fixable before an incident, expensive after.

---

## Mistake to Avoid

Treating "don't upload sensitive files" as a complete privacy policy. It names what must not happen but leaves employees to invent, file by file, the process for how the work still gets done. Under deadline pressure, most will reach for the fastest tool — and the fastest tool is rarely the approved one.

---

## Source

- **Video:** [How to Use AI on Files You're Not Allowed to Upload](https://www.youtube.com/watch?v=EuVvLwWZ5wc) · 13:40
- **Substack:** [Use AI on Sensitive Files You Can't Upload](https://natesnewsletter.substack.com/p/use-ai-sensitive-files) (preview; full post paid)
- **Chapters:** 00:00 The file I would never upload · 00:39 Why the warning stops too soon · 01:16 Airlock demo and protected terms · 02:39 Keep or cut: what the model actually needs · 04:03 Rebuild the file instead of redacting it · 04:50 Hand the clean copy to a frontier model · 05:57 Why this suddenly feels urgent · 07:45 What people in my community really do · 09:26 Verizon on shadow AI at work · 10:09 Security fatigue and better defaults · 11:06 Redaction that keeps the work useful · 12:44 Begin with the job
- *Transcript unavailable (Firecrawl panel did not render after two attempts); brief grounded on Substack preview and video description.*
