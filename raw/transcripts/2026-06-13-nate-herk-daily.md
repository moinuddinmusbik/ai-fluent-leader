---
title: "Claude Fable 5 Made This Entire Video By Itself. — Transcript"
source_video: "https://www.youtube.com/watch?v=ONmaDdOBGig"
duration: "5:47"
published: 2026-06-13
channel: "Nate Herk | AI Automation"
routine: nate-herk-daily
note: "Partial transcript extracted via Tavily (Firecrawl segment extraction unavailable — MCP timeout). Quotes are verbatim from the video's spoken content."
---

# Transcript: Claude Fable 5 Made This Entire Video By Itself.

**Source:** https://www.youtube.com/watch?v=ONmaDdOBGig  
**Duration:** 5:47 · Published: 2026-06-13

---

[Opening — approx 0:00–0:45]

So, I literally just opened up Claude Fable, gave it this goal, went down to the gym, and came back to this. What you're watching right now was not filmed. This avatar is AI. The voice you're hearing is a clone of mine. And every single word of this script was written by Claude. I didn't write this. I didn't film it. I didn't edit it. And while it was being made, I never saw a single frame of it. I just typed one prompt into Claude code and walked away. And everything else — the research, the script, the voice, the avatar, the motion graphics — all of it happened on its own.

So, this week, Anthropic released Claude Fable 5, and that's basically the only reason this video can exist. It's the first time a Mythos class model — that's the tier above Opus — has been available to anyone on a paid plan.

[Pipeline breakdown — approx 2:00–3:30]

[...script written] in my voice using a voice playbook built off my actual transcripts. Then the voice, it sent that script over to 11 Labs where I've got a voice clone trained on my real videos. And the trick is, you can't just generate like four straight minutes of audio because the longer a generation runs, the more the voice starts to drift. So Claude split the script into chunks, just under a minute each, and generated them separately.

Then every chunk went to HeyGen to render on my avatar on the Avatar 5 model, their newest motion engine. And for a while, you couldn't even select Avatar 5 through the API. So the workaround was Claude literally driving a browser with Playwright and flipping every video by hand. Their new API finally exposes it. So this one went straight through.

[Remainder of transcript not captured in this run.]

---

_Partial transcript only. Full Firecrawl extraction was unavailable (MCP timeout on browser actions). The quotes above are verbatim from the video's spoken content as extracted by Tavily._
