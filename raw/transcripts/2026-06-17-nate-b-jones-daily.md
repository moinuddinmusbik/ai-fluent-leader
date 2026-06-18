---
title: "Nate B Jones Daily — 2026-06-17 — Transcript"
type: source
date: 2026-06-17
creator: "[[nate-b-jones]]"
tags: [transcript, nate-b-jones]
---

# Don't build more AI agents until you watch this — Transcript

[[nate-b-jones]] · 2026-06-17 · https://www.youtube.com/watch?v=BOXK2XFLA-E · 18:25

**0:00** Verso made its agent better by deleting 80% of its tools. You heard that right.
**0:05** And that sentence can sound wrong if you've been following a lot of the hype around new tools and new skills for agents. So, I want to set the record
**0:12** straight. The usual story we hear is that agents get better as you give them more stuff, right? More context, more
**0:19** memory, more tools, more integrations, more access, more autonomy. Let the agent touch the CRM. Let it use Slack.
**0:25** Let it browse the web. Let it update the record. Verscel's example is a really healthy counter example in that process.
**0:33** And no, it's not just about context window, which is the usual reason people dump out tools. Messages came in, some were real leads, some were spam, some
**0:40** were support questions dressed up as sales questions, some came from little companies, some came from accounts that might matter to Versel. Some deserved a
**0:48** really quick reply, and some needed research, and some needed routing. It's the usual messy inbox. So Versell studied one of its best reps. They watch
**0:56** the workflow closely enough to turn pieces of it into an agent. I love that part. You have to study what people are already doing. What did the rep ignore?
**1:04** What did they answer? What made a lead real? What research happened before the reply? When was a message actually a support issue? Where did the human still
**1:11** need to make a judgment call? Then they built the agent around the actual observed workflow, not the paper workflow. Again, love that. The agent
**1:19** filtered inbound messages. It qualified leads. It researched companies. It drafted responses. It routed support questions away from sales. A human still
**1:27** reviewed the work because the goal was not to let a bot roam around the company, right? The goal was to take a repeatable workflow from a strong employee and make that repeatable bit
**1:35** run fast. And that's already a great story. But the more important lesson is what happened after the agent existed.
**1:43** The agent did not get better when the team kept piling on tools. It got better when they took away tools. And this is
**1:51** something that I think that a lot of folks who are excited about agents need to sit with more. And this goes for skills too. If you got a pile of skills
**1:59** in your codeex or claw, pay attention because most of us are building agents the opposite way in practice. We're so enthused about building, right? We start
**2:07** with one task and add a tool and add another tool and add a memory file and add a Slack integration, add a browser and add a CRM action, add another exception, and after a while, the agent
**2:15** will look super powerful and muscled up, but it's going to become harder to trust. The beginner instinct is to add.
**2:22** The maintenance instinct is to ask what should be removed. That is the real agent story of 2026. Not can you build
**2:29** an agent. Look, I've got a video on that. There's dozens of videos out there on that. Of course, you can build an agent. The harder question is whether
**2:37** you can keep the setup around the agent healthy as the work changes and the model evolves. People call that setup a harness. If that word feels super technical, you can call it a workbench.
**2:46** It's kind of the same thing. The agent is the worker. The harness is the workbench. It's what the agent reads.
**2:51** It's what it remembers. It's what tools it can touch. It's what it's allowed to change. It's what proof it has to bring back. It's what stops it when the work
**2:59** gets risky. Versel sales agent had a workbench or a harness. It had a documented workflow from a top performer. It had tools. It had handoffs. It had human review. It had
**3:08** feedback. And then the team learned that part of maintaining that workbench or harness is pruning. And that is a much more important lesson than AI replaced
**3:17** the sales process which is what all the headlines were about. The real lesson is that useful agents desperately need good maintenance. And I think there are four
**3:25** first principles here that I want to lay out that are going to be durable for 2026. The first is that agents themselves are moving. The model
**3:33** underneath the agent is not stable. It's getting better. It's getting better at tool use. It's better at reasoning across steps. It's better at
**3:41** understanding messy instructions. It's better at reading files. It's better at remembering what matters. It's better at moving through work without needing every step spilled out. So, Asians get
**3:50** better. And that sounds purely good. And mostly it is. But it also means yesterday's harness can become very wrong very quickly at the price of an
**3:58** update. A tool that helped a weaker model can confuse a stronger one. A a rule that protected you from an unreliable model's mistakes can trap a
**4:08** better model. A workflow that forced structure around a clumsy agent can become drag when the model can handle a lot more of the work itself. These are
**4:16** all real examples. We are used to software breaking when it gets worse.
**4:20** That's our mental model. Agents can also break when the model gets better and that is a different and new thing. It's a strange new maintenance problem.
**4:31** Imagine the first version of an agent is not very reliable. It overreaches. It invents patterns. It treats one example like a trend. So you build a really
**4:38** careful harness around it. You give it strict tools and narrow the prompt and say only use these sources. Don't infer.
**4:44** Don't create records. Don't recommend a next step. Just summarize what you see.
**4:48** And that may be exactly right for that model. And then 3 months later, the model improves. Again, real examples here. Now it can compare sources better.
**4:56** It can understand the workflow better.
**4:57** It can tell the difference between a weak signal and a real pattern. It can draft a useful next step. I am describing November to March of this
**5:05** past 6 or eight months. But your harness still treats it like the old model. So the Asian is underused. Or the opposite happens, right? The old model was
**5:13** clumsy. So you give it broad access because you knew a human would catch everything. Then the model gets better.
**5:18** Now it can take 20 plausible actions in a few minutes. Now they look real. They look organized. They create work that a human has to unwind. So the model
**5:26** improved. The harness did not. And that is a massive driver of agent breakage in 2026. Normal systems drift. Prompts
**5:35** drift. Wikis gets stale. Dashboards break. Automations keep running long after the process changes. SOPs describe how the company worked months ago. Slack
**5:43** channels become junk drawers. Templates survive long after the reason for the template disappeared. None of that started with AI, right? Every company already has this problem. The product
**5:52** wiki, it's a little or a lot wrong. The CRM field means something slightly different than it used to. The dashboard, it still says activation, but the team changed what activation needs.
**6:02** The support tags have evolved. The roadmap moved. the owner changed, the process changed, the docs didn't. With normal software, this is vaguely annoying and you sometimes get messages
**6:10** saying, "Please update your wiki." With agents, it's very dangerous because agents don't sit. They produce work. They're proactive. That's their job.
**6:18** They summarize. They recommend. They draft. They route. They update. And sometimes, of course, they act. That's the value. So, a stale wiki that is
**6:26** annoying to you is incredibly dangerous to an agent because it doesn't know that and it just keeps on working. And this
**6:35** is the second principle I want to communicate. Agents inherit all of the crud of the systems around them. If your wiki is stale, your agent reads and
**6:44** ingest stale truth. If your process changed, your agent will follow old process unless you update your docs. If
**6:52** your prompt is written for last quarter's company and model, the agent may keep serving last quarter's company and not realize everything's changed. If
**7:00** your dashboard definition is incorrect now, the agent will make the wrong number feel very convincing. This is not a model failure in the simple sense,
**7:08** right? The agent did its job. It's the old maintenance problem with a machine that now can produce work from that mess that is sometimes very convincing. And
**7:17** this is why Stuart Brand's maintenance of everything. I think it's the right frame for agents. Brand is writing about sailboats and vehicles and weapons and
**7:26** manuals and corrosion and the work that keeps important systems alive after the launch moment is over. Agents are a lot less like apps and more like sailboats.
**7:34** I love this book. This is like one of my favorite books of the year. You don't just launch agents and walk away. The weather changes. The lines loosen. Salt
**7:42** gets into everything. And yes, this is all from that book. The same setup that worked yesterday can be wrong tomorrow.
**7:48** A sailboat is not maintained because it was badly designed. It is maintained because it lives in motion. Agents live
**7:56** in motion, too. The model changes inside them. The world changes around them. In that sense, they are much more like
**8:04** traditional vehicle maintenance than anything else we've seen in software in a long time. The harness has to keep up with the model changes and the world
**8:13** changes. And so few of us really have a good system for that. Now the third principle I want to call out is that the biggest AI companies already know this.
**8:22** A lot of the implicit bet from the frontier labs and platform companies is not just that their models will get better. It is that they can use those
**8:29** better models to ship and evolve the harness faster. And I think that's one reason why it's really important to talk about Codeex in the strategic context of
**8:38** OpenAI's long-term strategy. And I think that's one reason Codeex matters so much. Codex is strong not just because
**8:45** the model is strong. Codeex is strong because open AI keeps maintaining the harness around the model. So it feels
**8:52** intuitive and native as the model and the world evolve around it. It is becoming closer to an operating surface for work as it's evolved. So it has a
**9:01** terminal and a desktop app and an IDE and a browser and computer use and files and plugins and memory and automations and approvals and sandboxing and network
**9:09** controls and keychain storage and managed configs and logs. This is way beyond a chat box with a smarter brain.
**9:16** It's a very carefully maintained workbench around machine work. And the Claude code team is doing the same thing, right? They're investing heavily
**9:25** in their harness. I'm really excited to do the Claude code is as amazing as codeex review guys. So, please give me something that cool. And to go back to
**9:33** the workbench analogy, every tool in that workbench is carefully chosen with codecs, right? The terminal matters because real work lives in commands and
**9:41** repos and files and tests and local tools. This was Claude Code's original insight, by the way. The browser matters because real work happens on interfaces
**9:50** that humans see. And both Anthropic and OpenAI are building that way. Computer use matters because not every tool has a clean API. Plugins matter because work
**9:59** lives in a bunch of other systems, GitHub, Google Drive, Jira, Slack, etc.
**10:04** Memory matters because preferences and corrections should not have to be rebuilt every day, right? Approvals and
**10:11** sandboxing matter because a capable agent still needs boundaries. Logs matter because when an agent does something weird, someone needs to know what happened. This whole surface
**10:19** together is the harness. It's an art to build a good harness. And there are really two teams in the world building good harnesses. The anthropic team and
**10:27** the OpenAI team right now. And this is where the hyperscaler and frontier platform bet gets super interesting. If the model can help you ship the harness
**10:34** and test the harness and refactor the harness and observe the harness and prune the harness, then capability gain is going to start to compound real fast
**10:42** because better agents can help build more effective harnesses. Better harnesses can make the agents more useful and then better agents can help
**10:49** rebuild that harness once more. That is why the Verscell story is not just a quirky sales automation story. It's a pattern we all need to learn from. The
**10:57** companies that win are not the ones that build the perfect rapper once. They're the ones that keep rebuilding the wrapper as the model and the work
**11:05** change. They rebuild that workshop. They rebuild that harness. And this is why the direction of codeex over time feels really significant to me. If codeex
**11:13** keeps getting more capable, and that's an if. And the codec harness keeps getting closer to the operating system of work. Another if, then open AI is not
**11:22** only selling intelligence, they are selling the environment in which intelligence becomes useful. And that's the same betanthropic is making with cloud code and cloud co-work. The
**11:30** harness evolves, the model evolves, the harness lets the model touch more real work over time. More real work creates more pressure to improve the harness.
**11:39** And that loop is ignited like a flywheel. And that loop matters and it raises the bar for all of the rest of us because if you're building your own
**11:47** agent setup, you are now not just choosing a model. You're choosing how much harness maintenance you are choosing to own versus how much harness
**11:56** maintenance you're outsourcing. A light custom harness might be a clean set of instructions and memory and source folders and repeatable methods around
**12:03** codecs or quad. That can be enough. Here are the sources. Here's the job. Here's what you can't touch. Here's the proof I
**12:10** need. Here's when a human decides. A deeper custom harness is a very different thing. Because now you have a
**12:18** data feed, a review screen, permission levels, logs, model choice, escalation paths, approval rules, and a plan for what happens when the model changes. And that can be very worth it to invest in.
**12:29** But now you're not just building an agent. You are investing in the long-term maintenance of an agent and
**12:36** harness system. You are taking responsibility for evolving the system around the agent over time. And the more
**12:43** custom the harness, the more you own the upkeep. And this is not abstract for me.
**12:49** So now I'm thinking about my delegation model differently. And part of it is just the ordinary mess of work, right?
**12:53** Folders move, drafts change, source packets get updated, memory gets stale, and the way I want the agent to use local context changes as the agent gets
**13:01** better. So the thing I maintain is a lot more than a prompt. It's it's the whole way the agent meets my files. Where should it look first? Which folders are
**13:08** a source of truth? What should it ignore? What should it ask about before touching? What should it remember? What should it forget when it searches memory? Is that right? When does it
**13:18** actually go read the file? That is a harness question for me. And that's a tiny personal harness question, right?
**13:23** I'm not even talking about team harnesses here. And it has changed because the agents have changed because the models have updated. And this brings
**13:31** me to the fourth principle and it's the one that I think matters the most. You need to ask I think all of us need to
**13:38** ask what is my harness? What is my workshop? Not in a sort of technical way that makes it feel scary, but in a very
**13:46** practical way. If you use Chad GBT or claude or or codecs or any other agentic tool, your harness is the setup that
**13:53** makes that model useful for your real work. Maybe it's project folders, maybe it's your memory, your prompts, your source docs, your approval habits, your
**14:01** browser access, your file rules, your tools, your verification loop, your way of asking for proof, your habit of
**14:08** making the agent read the actual source instead of guessing from context. If you're a product leader, your harness might be the sources your agent reads before planning. Right? If you're in
**14:17** sales, your harness might be the CRM fields or the call notes or the routing rules and the human approval steps.
**14:23** Maybe you're in support, right? Your harness might be the policy store and escalation paths and refund rules. If you're a writer, your harness might be
**14:31** your drafts and your transcripts and your voice notes and your editorial rules and your archive and the instruction that the agent has to show where an idea came from. If you're an
**14:40** engineer, of course, your harness would be uh repo, test, terminal, permissions, work trees, logs, review rules. That in many ways is the most mature example of
**14:48** a harness we have today. But that's the real question for all of us, whether we're engineers or not. What is your harness? What are you doing to ship it?
**14:56** What are you doing to rebuild it? Do you know when to rebuild it? Do you know how to rebuild it? What are you doing to evolve it as the models improve? The
**15:04** more useful question is, can I maintain this sailboat over a voyage? What harness does this agent
**15:12** need? Those are the same questions. And then the really mature question is, what part of this harness will I need to delete later? And and Brand gets into
**15:20** this. He talks about simplicity is a key to maintenance. And I love that. This is the Versel lesson. The agent got better when the workbench got cleaned up. And
**15:28** once you start to realize that your your maintenance question is not just a modification question, but potentially a
**15:37** deletion question, the whole agent conversation becomes a lot more complex.
**15:42** You stop treating the harness as a one-time rapper. You treat it as a living system where you do have to add sometimes and you do have to take away.
**15:49** You have to think about the systems health overall. So for any serious agent, I would check these five things first. What's it eating right? What's it
**15:56** reading? Are the sources current? Did the workflow move? Did a new source become important? Did an old source become misleading? Second, I would test
**16:03** its reach. What can it touch? Can it only read? Can it draft? Can it create tickets? Can it post in Slack? Can it update records? Can it spend money? Can
**16:12** it publish? A permission that was harmless for a weaker model may be too broad for a strong one. A restriction that made sense for an unreliable model
**16:19** may hold back a better one. Third, I would check its job. Is this still a summary agent? Is that useful? Is it becoming a planning agent because agents
**16:27** are getting better and it can be? Is it supposed to find themes? Is it supposed to recommend tradeoffs? Is it supposed to route work? Do not let the job change
**16:36** silently. Change the job on purpose if you're going to do it at all. Fourth, check the proof. The agent shouldn't
**16:44** just say customers are frustrated with onboarding. It needs to link to the tickets. It should link to sales notes.
**16:50** It should quote customer language and have a source. And it should say which sources it checked and where and which ones it could not access. So the proof
**16:59** is not just the agent saying it. The proof is an a linkable trail a human can inspect. Fifth and last, check the
**17:08** agents value. I don't think this gets done enough. It's like asking if the sale bill got there, right? Does anyone read the output? Does it change the work? Does it save time after review?
**17:17** Does it create another pile of work? Is it duplicating a report? Has the model improved enough that the agent ought to be rebuilt? Has the business changed enough that the agent should be retired?
**17:25** That can happen. Agents, unlike almost anything else, break in two directions.
**17:31** They break because the world around them drifts. And they break because the model inside them improves. And maintenance is
**17:38** the work of keeping the harness fit between those two moving things. That delicate art, that sailing art is the future of agents. It's not just more
**17:46** capability, it's better maintained capability. The work changes around the agent, the model changes inside it. And if you ignore either of those, the agent
**17:54** does not have to fail very loudly to become quite dangerous. All the agent has to do is to keep working and it will start to haunt your business. And before
**18:03** I forget, yes, I'm going to say it again, read The Maintenance of Everything. If I could recommend one book on agents that isn't about AI, I
**18:11** would recommend this one. It's a phenomenal book. It's out of Stripe Press. I love what Stripe Press is doing. Thank you guys. It's by Stuart Brand. Go get it and read it. It will
**18:19** teach you a lot about how to think about the maintenance of technical systems. Have fun.
