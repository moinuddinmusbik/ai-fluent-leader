---
title: "App Intents"
type: concept
created: 2026-06-11
updated: 2026-06-11
tags: [apple, api, agent-integration, platform]
sources: ["2026-06-11-nate-b-jones-daily.md"]
---

# App Intents

Apple's OS-level API framework that makes third-party apps callable by system-level AI agents. Expanded at WWDC 2026 as a core developer primitive for the Apple Intelligence ecosystem.

## What It Does

Standardizes how apps expose their functionality to the OS — allowing Siri and other Apple agents to invoke app actions directly without the user opening the app. Nate B. Jones describes it as making every app on every Apple device an "OS-callable action."

## Why It Matters Strategically

App Intents makes Apple the **mandatory integration broker** for any AI agent that wants to reach an Apple user. Developers who don't implement App Intents cannot be reached by Apple's agent layer. This is structurally equivalent to owning a toll road for AI-to-app interactions on 1B+ devices.

## Analogy for Enterprise

Every enterprise should ask: "Do we have an App Intents equivalent for our internal systems?" — a standardized layer that makes internal tools callable by an AI agent. Organizations that own this integration layer control how AI interacts with their data; those that don't will pay rent to whoever does (Microsoft 365 Copilot, Salesforce Einstein, etc.).

## See Also

- [[apple-surface-strategy]]
- [[2026-06-11-nate-b-jones-daily]]
