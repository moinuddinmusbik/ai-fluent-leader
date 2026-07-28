---
title: "Nate B Jones Daily Leader Briefing — 2026-07-27"
type: email-archive
created: 2026-07-27
updated: 2026-07-27
routine: "Nate B Jones Daily Leader Briefing"
tags: [nate-b-jones, strategy, chinese-ai-models, cost-per-accepted-result]
---

# AI-Fluent Leader · Strategy Brief
## US AI Dominance Is Over: Here's Why

**Nate B. Jones** · Published: 2026-07-27 · YouTube · Substack · TAKE

---

## The Big Idea

The "US AI dominance is over" framing is both true and misleading. Five Chinese labs — DeepSeek, Qwen, GLM, Kimi, and MiniMax — now produce models capable of earning real money on bounded, high-volume, checkable work. But every conversation that frames this as a country vs. country contest prevents you from making the right call. Nate's central argument: the decision is never about a flag. It's always a job, an endpoint, and a check.

## Why It Matters Now

The cost gap has crossed a pressure threshold. DeepSeek charges $0.87 per million tokens; Kimi K3 charges $15; frontier models run $60–75+. Someone on your team is already building the "5× cheaper" argument to shift a workload. Without a rigorous evaluation framework, organizations will make this call on tribal allegiance rather than evidence — and discover the error after it's embedded in production.

## His Argument

- **"Chinese AI models" is not one thing:** Five labs, five distinct strategies, five different license structures, five different failure modes. DeepSeek and Qwen are not the same decision.
- **Token price and finished-work cost point in opposite directions:** A model at one-fifth the price that doubles your review time may cost more overall. The metric that replaces token price is *cost per accepted result* — what you actually pay to produce one output that clears your quality bar.
- **Mixture-of-experts changes the hardware calculus:** Downloading model weights does not solve serving. Hardware burden is a separate decision from API price.
- **The deployment path is its own variable:** API, third-party host, and self-host each carry different cost, license, hardware burden, and data-path implications — three different risk profiles even for the same model.
- **The selection rule:** Chinese models are worth real money on bounded, high-volume, checkable work where errors are catchable. They remain the wrong default anywhere a plausible error is expensive to catch.

## Receipts

- **Price spread (real data):** DeepSeek $0.87/M tokens · Kimi K3 $15/M tokens — cited by Nate with live pricing.
- **The Ringer run:** Nate's own 34-task live agent job (GLM-5.2, GPT-5.5, Grok 4.5, Composer 2.5 Fast). One worker reported 213 verified quotations — 13 were fabricated citations stitched together. Total cost: ~$8 USD.
- **CAISI evaluation:** Independent analysis of DeepSeek V4 Pro economics shows cost-per-accepted-result diverges significantly from the token-price headline.
- **Distillation signal:** If Chinese models were partly trained on frontier outputs, the capability gap closes faster than organic development suggests.
- **Data transparency:** Nate discloses an incomplete Qwen experiment from the Ringer build — no complete log of checkpoint, task mix, pass rate, or cost. He says so rather than blurring experiments.

## The Contrarian Edge

- **The binary is wrong on both sides.** The mainstream debate swings between cost-savings euphoria and security panic. Nate rejects both. The frame is a job, an endpoint, and a check — not a country.
- **His conclusion still favors American frontier on unbounded work** — but the reason is quality bars and error costs, not nationality. That distinction matters: as Chinese model quality closes the gap on specific work types, the equation changes.
- **He signals when the call gets harder.** Distillation allegations, if substantiated, compress the timeline for Chinese models to cross the threshold on edge-case work.

## What It Means For You

1. **Replace "best model" with "right model per job."** For every workload: What is the job? What is the endpoint? What is the check?
2. **Calculate cost per accepted result before approving any model switch.** Factor in review time, rejection rates, and rework.
3. **Run a structured bakeoff — not a vibe check — before committing any workload.** Use a validator, manifest, score sheet, and fixtures.
4. **Decide each deployment path separately from the model decision.** API, third-party hosting, and self-hosting are three different risk profiles.

## Mistake to Avoid

Letting one impressive output from a Chinese model push your org to switch — or letting one citation hallucination or censorship refusal disqualify an entire model family. You need a bakeoff on your actual task corpus before making either call.

## Source

- **Video:** [US AI Dominance Is Over: Here's Why](https://www.youtube.com/watch?v=JBzz53HqMEs) · 24:01
- **Substack:** [How to run a Chinese-model bakeoff](https://natesnewsletter.substack.com/p/chinese-ai-models-test) (preview; full post paid)
- **Chapters:** 00:00 Why Chinese models is not one thing · 00:47 Kimi K3 at $15, DeepSeek at $0.87 · 02:29 Where DeepSeek earns high-volume work · 04:17 Testing GLM, Kimi, Qwen, and MiniMax · 05:39 Five labs, five different strategies · 06:57 Mixture of experts and your hardware burden · 08:04 Why downloading weights does not solve serving · 09:10 What the CAISI evaluation found · 10:19 Cost per accepted result · 13:15 Distillation, and where the fight starts · 17:08 API, third-party host, or self-host · 20:05 The four questions I run before committing
