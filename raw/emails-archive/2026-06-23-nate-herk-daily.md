---
date: 2026-06-23
routine: nate-herk-daily
type: DEEP-DIVE
title: "I Battle Tested Sakana Fugu's Fable Killer"
url: https://www.youtube.com/watch?v=GpSqBjW6hR4
duration: 12:16
transcript_available: false
---

# Nate Herk Daily Implementation Playbook — 2026-06-23

*Email sent to moinuddin.musbik@gmail.com on 2026-06-23*

```html
<div style="margin:0;padding:0;background:rgb(244,244,244);font-family:Georgia,serif">
<table width="100%" cellpadding="0" cellspacing="0" style="background:rgb(244,244,244);padding:32px 0;font-family:Georgia,serif"><tbody><tr><td align="center">
  <table width="700" cellpadding="0" cellspacing="0" style="max-width:700px;border-radius:8px;overflow:hidden;font-family:Georgia,serif"><tbody>
    <tr><td style="background:rgb(26,26,46);padding:28px 36px 22px">
      <p style="margin:0 0 6px;font-size:11px;letter-spacing:2px;text-transform:uppercase;color:rgb(136,136,170)">AI-Fluent Leader · Implementation Playbook</p>
      <h1 style="margin:0 0 10px;font-size:22px;line-height:1.3;color:rgb(255,255,255)">I Battle Tested Sakana Fugu's Fable Killer</h1>
      <p style="margin:0;font-size:13px;color:rgb(170,170,204)">Nate Herk &nbsp;·&nbsp; Published: <strong style="color:rgb(224,224,255)">2026-06-23</strong> &nbsp;·&nbsp; 12:16 &nbsp;·&nbsp; <span style="display:inline-block;padding:2px 9px;border:1px solid rgb(74,108,247);border-radius:10px;font-size:11px;letter-spacing:1px;text-transform:uppercase;color:rgb(170,190,255)">DEEP-DIVE</span></p>
    </td></tr>
    <tr><td style="background:rgb(248,249,255);padding:12px 36px;border-bottom:1px solid rgb(238,238,238)">
      <p style="margin:0;font-size:12px;line-height:1.9;color:rgb(51,51,51)"><strong style="text-transform:uppercase;letter-spacing:1px;font-size:11px;color:rgb(26,26,46)">Stack:</strong> <span style="display:inline-block;margin:2px 4px 2px 0;padding:2px 9px;background:rgb(26,26,46);color:rgb(224,224,255);border-radius:4px;font-family:'Courier New',monospace;font-size:12px">Sakana Fugu Ultra</span><span style="display:inline-block;margin:2px 4px 2px 0;padding:2px 9px;background:rgb(26,26,46);color:rgb(224,224,255);border-radius:4px;font-family:'Courier New',monospace;font-size:12px">Claude Opus 4.8</span><span style="display:inline-block;margin:2px 4px 2px 0;padding:2px 9px;background:rgb(26,26,46);color:rgb(224,224,255);border-radius:4px;font-family:'Courier New',monospace;font-size:12px">Claude Code</span><span style="display:inline-block;margin:2px 4px 2px 0;padding:2px 9px;background:rgb(26,26,46);color:rgb(224,224,255);border-radius:4px;font-family:'Courier New',monospace;font-size:12px">Codex</span><span style="display:inline-block;margin:2px 4px 2px 0;padding:2px 9px;background:rgb(26,26,46);color:rgb(224,224,255);border-radius:4px;font-family:'Courier New',monospace;font-size:12px">Open Router Fusion API</span></p>
    </td></tr>

    <!-- WHAT IT IS -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">What It Is</h2>
      <p style="margin:0;font-size:16px;line-height:1.7;color:rgb(34,34,34)">Sakana AI dropped Fugu Ultra with viral claims that it matches Fable and Mythos. The key nuance Nate unpacks: <strong>Fugu is not a new model</strong>. It is a single API that automatically orchestrates and routes tasks across existing frontier models — Claude Opus 4.8, GPT, and Gemini — similar to how Claude Code spins up sub-agents, but fully automated. The headline question the video answers: do you get better results by letting Fugu decide which model handles each sub-task, or does a well-configured Opus 4.8 still win? Nate ran 38 structured tasks to find out.</p>
    </td></tr>

    <!-- HOW IT WORKS -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">How It Works</h2>
      <ul style="margin:0;padding-left:20px;font-size:15px;line-height:1.8;color:rgb(51,51,51)">
        <li style="margin-bottom:10px"><strong>Single API endpoint:</strong> Fugu Ultra receives a task and automatically routes sub-tasks to whichever frontier model it judges best — Opus 4.8 for heavy reasoning, GPT or Gemini for others.</li>
        <li style="margin-bottom:10px"><strong>Dashboard + Claude Code integration:</strong> Fugu has a web dashboard for monitoring; at the 2:32 chapter Nate demonstrates running it directly inside a Claude Code session as the model endpoint.</li>
        <li style="margin-bottom:10px"><strong>The Orchestration Spectrum (3:30):</strong> Nate maps out the range from fully-manual model selection through Fugu's fully-automatic routing — helping you see where your current workflow sits before adding a layer.</li>
        <li style="margin-bottom:10px"><strong>Versus Open Router Fusion API (5:07):</strong> Open Router already offers a comparable multi-model fusion approach; Nate compares the two so you can weigh alternatives before committing to Fugu.</li>
        <li style="margin-bottom:10px"><strong>Speed &amp; Cost Reality (5:39):</strong> The orchestration overhead has a measurable price — some tasks that complete in 6 seconds on Opus alone took over 2 minutes through Fugu's routing layer.</li>
      </ul>
    </td></tr>

    <!-- THE VERDICT -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">The Verdict</h2>
      <p style="margin:0;font-size:16px;line-height:1.7;color:rgb(34,34,34)">After 38 tasks, Nate is <strong>not switching off Claude Code and Codex</strong>. Fugu's automated routing does not consistently outperform a tuned Opus 4.8 setup at the workflow level. The orchestration overhead introduces latency (up to 20× slower on some tasks) and cost unknowns that erode the theoretical multi-model quality gain. The viral "matches Fable and Mythos" framing was benchmarked under conditions that don't hold when you test on real, representative workloads.</p>
    </td></tr>

    <!-- WHEN TO USE IT (AND WHEN NOT) -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">When To Use It (and When Not)</h2>
      <ul style="margin:0;padding-left:20px;font-size:15px;line-height:1.8;color:rgb(51,51,51)">
        <li style="margin-bottom:10px"><strong>Consider Fugu when:</strong> You have exploratory or research-heavy tasks where quality matters far more than speed, you want to experiment with multi-model routing without manual wiring, or you want to use the free trial to benchmark against your actual stack before making a call.</li>
        <li style="margin-bottom:10px"><strong>Avoid Fugu when:</strong> You need predictable, sub-30-second task completion; you already have a tuned Opus 4.8 workflow in Claude Code that clears your quality bar; or you are already paying for Claude Pro + Codex and need to justify every additional cost layer.</li>
        <li style="margin-bottom:10px"><strong>The OpenCode alternative:</strong> Community members pointed out that OpenCode + the OMO plugin achieves similar multi-model routing using your own API keys — worth exploring before adding Fugu's pricing layer.</li>
      </ul>
    </td></tr>

    <!-- SET IT UP -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 14px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">Set It Up</h2>
      <ol style="margin:0;padding-left:20px;font-size:15px;line-height:1.8;color:rgb(51,51,51)">
        <li style="margin-bottom:12px"><strong>Start the free trial</strong> — Go to the Fugu dashboard (available free through end of June 2026) and create an account to get your API key.</li>
        <li style="margin-bottom:12px"><strong>Connect to Claude Code (2:32)</strong> — Configure Fugu Ultra as the model endpoint in your Claude Code session, substituting it for the direct Opus 4.8 call.</li>
        <li style="margin-bottom:12px"><strong>Run your own baseline benchmark</strong> — Select 5–10 tasks representative of your real workload. Run them through Fugu Ultra and through Opus 4.8 directly. Log quality, wall-clock time, and estimated cost per task.</li>
        <li style="margin-bottom:12px"><strong>Review the Orchestration Spectrum (3:30)</strong> — Map each of your task types onto the spectrum Nate outlines. Tasks that already land in "Opus wins solo" territory don't need the routing layer.</li>
        <li style="margin-bottom:12px"><strong>Compare vs Open Router Fusion API (5:07)</strong> — Before committing, price-compare Fugu against the Open Router alternative for the same task mix.</li>
      </ol>
    </td></tr>

    <!-- GOTCHAS & WATCH-OUTS -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">Gotchas &amp; Watch-Outs</h2>
      <ul style="margin:0;padding-left:20px;font-size:15px;line-height:1.8;color:rgb(51,51,51)">
        <li style="margin-bottom:10px"><strong>Speed cliff is real:</strong> Community reviewers noted tasks that took 2+ minutes through Fugu vs. 6 seconds direct on Opus. For any user-facing or time-sensitive pipeline, this is a blocker, not a footnote.</li>
        <li style="margin-bottom:10px"><strong>Recursive abstraction risk:</strong> Fugu on top of Claude Code on top of Opus creates three layers of orchestration. Each layer adds failure modes, latency, and debugging surface. The community's top comment — "another harness that harnesses different harnesses" — names this precisely.</li>
        <li style="margin-bottom:10px"><strong>Benchmark framing gap:</strong> Viral "matches Fable/Mythos" claims were generated under specific test conditions. Nate's 38-task structured test showed the delta doesn't hold across diverse real-world workloads.</li>
        <li style="margin-bottom:10px"><strong>Cost opacity:</strong> The Speed and Cost Reality chapter (5:39) surfaces pricing unpredictability — routing across multiple frontier APIs means variable cost per task that's harder to budget than a single-model subscription.</li>
      </ul>
    </td></tr>

    <!-- STEAL THIS FOR YOUR ORG -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238);background:rgb(248,249,255)">
      <h2 style="margin:0 0 14px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">Steal This For Your Org</h2>
      <ol style="margin:0;padding-left:20px;font-size:15px;line-height:1.8;color:rgb(51,51,51)">
        <li style="margin-bottom:12px"><strong>Run the 38-task structure on your actual use cases.</strong> Pick 10 real tasks from your team's AI usage. Test Fugu Ultra vs. your current best single-model setup. Track quality, latency, and cost per task — not marketing benchmarks.</li>
        <li style="margin-bottom:12px"><strong>Map your workloads on the Orchestration Spectrum.</strong> Before adopting any auto-router, identify which task types genuinely benefit from model routing and which are "just Opus" tasks. This prevents adding overhead where it won't show up.</li>
        <li style="margin-bottom:12px"><strong>Evaluate Open Router Fusion API as your alternative.</strong> It targets the same use case. Compare pricing, integration complexity, and latency profile against Fugu before choosing a multi-model routing layer.</li>
        <li style="margin-bottom:12px"><strong>Define your quality floor before trialing new orchestration.</strong> If Opus 4.8 already clears 90%+ of your tasks at your quality bar, the case for automated routing layers weakens significantly. Set the bar first — then test whether Fugu clears it.</li>
      </ol>
    </td></tr>

    <!-- MISTAKE TO AVOID -->
    <tr><td style="padding:24px 36px 20px;border-bottom:1px solid rgb(238,238,238)">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(192,57,43)">Mistake to Avoid</h2>
      <p style="margin:0;font-size:15px;line-height:1.7;color:rgb(51,51,51)">Treating viral benchmark framing as your evaluation. Fugu's "matches Fable and Mythos" announcement spread fast — but Nate's structured 38-task test showed the gap disappears at the workflow level, with some tasks regressing 20× on speed. The lesson: always benchmark a new tool against <em>your</em> baseline on <em>your</em> tasks. A 2-minute completion that Opus handles in 6 seconds is a regression, not a win, no matter what the launch blog says.</p>
    </td></tr>

    <!-- SOURCE & RESOURCES -->
    <tr><td style="padding:22px 36px 28px">
      <h2 style="margin:0 0 12px;font-size:15px;text-transform:uppercase;letter-spacing:1px;color:rgb(26,26,46)">Source &amp; Resources</h2>
      <p style="margin:0 0 8px;font-size:14px;color:rgb(51,51,51)"><strong>Video:</strong> <a href="https://www.youtube.com/watch?v=GpSqBjW6hR4" style="color:rgb(74,108,247)" target="_blank">I Battle Tested Sakana Fugu's Fable Killer</a> &nbsp;·&nbsp; 12:16</p>
      <p style="margin:0 0 8px;font-size:13px;color:rgb(102,102,102)"><strong>Chapters:</strong> 0:00 Intro &amp; Fugu Dashboard Demo · 1:00 How Fugu Actually Works · 2:32 Running Fugu In Claude Code · 3:30 The Orchestration Spectrum · 5:07 vs Open Router Fusion API · 5:39 Speed And Cost Reality · 6:28 The 38-Task Test · 10:27 Final Takeaway · 11:45 Outro</p>
      <p style="margin:0 0 8px;font-size:13px;color:rgb(102,102,102)"><strong>Linked:</strong> No substantive article/doc links in description (sponsor/affiliate links only).</p>
      <p style="margin:0 0 8px;font-size:13px;color:rgb(136,102,102)"><em>Note: Transcript unavailable for this video — YouTube, youtubetranscript.com, and Firecrawl stealth all blocked. Content grounded on description, chapters, and top comments (74K views, 1,825 likes).</em></p>
      <hr style="border:none;border-top:1px solid rgb(238,238,238);margin:18px 0">
      <p style="margin:0;font-size:11px;color:rgb(153,153,153)">Generated by AI-Fluent Leader pipeline &nbsp;·&nbsp; 2026-06-23 &nbsp;·&nbsp; <a href="https://github.com/moinuddinmusbik/ai-fluent-leader" style="color:rgb(170,170,170)" target="_blank">ai-fluent-leader wiki</a></p>
    </td></tr>
  </tbody></table>
</td></tr></tbody></table>
</div>
```
