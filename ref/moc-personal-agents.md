---
created: 2026-10-06
featured: true
tags: [moc, guide, personal-agents, always-on, openclaw, hermes-agent, openai-dots, grok-bot, gemini-spark, claude-cowork, meta-muse]
---

# Always-on personal AI agents: a guide

**TL;DR:** An *always-on personal agent* is an AI that lives on a computer (yours or the vendor's), keeps running when you walk away, remembers you, and is something you *message* rather than *open*. OpenClaw made the idea go viral in January 2026, and Hermes became the open-source favourite. Over the year every big lab shipped a hosted version: Claude Cowork, Gemini Spark, xAI's Grok Bot, Meta's Muse and, most recently, OpenAI's Dots. This page explains the idea, compares the options, tells the story so far and maps our entries.

![OpenClaw: the project that started the wave](https://screenshotit.app/https://openclaw.ai)

## What is an "always-on personal agent"?

Everything is an "agent" now, so the word alone tells you little. Claude Code is an agent, ChatGPT runs agents, and so on. What sets this category apart is **how you relate to it**, not how smart it is:

| | Chatbot | Coding agent | **Always-on personal agent** |
|---|---|---|---|
| Examples | ChatGPT, Claude.ai | Claude Code, Codex, Cursor | OpenClaw, Hermes, Dots, Grok Bot |
| How you use it | Open a chat, ask, read | Open a session, drive it on a task | **Message it** (Telegram, Slack, WhatsApp, email…) and leave |
| Runs when you're away? | No | Only while the session is open | **Yes**: background jobs, schedules, "heartbeats" |
| Memory | Mostly per-chat | Per-project files (CLAUDE.md) | **Of you**, across everything, growing over time |
| Has its own computer? | No | Uses yours, in a repo | **Yes**: a home server, a Mac mini, or a vendor's cloud VM |
| Mental model | Oracle | Pair programmer | **Assistant / coworker** |

The key test is: **does it keep working, and keep remembering, when you're not looking at it?**

Other names in use: *personal AI agents* (most common), *24/7 agents*, *AI coworkers/teammates* (the enterprise pitch from Grok Bot and Dots), *claws* (community slang after OpenClaw and its many forks).

## The landscape (October 2026)

The big split is **self-hosted and open** versus **hosted and commercial**.

| Agent | Who | Launched | Runs where | Talk to it via | Cost | Distinctive bet |
|---|---|---|---|---|---|---|
| [[openclaw]] | OpenClaw Foundation (OpenAI-backed) | Jan 2026 | Your machine | WhatsApp, Telegram, iMessage, Signal, Slack… | Free + model costs | **Breadth**: most channels, huge skills marketplace |
| [[hermes-agent]] | Nous Research | Feb–Mar 2026 | Your machine / VPS | Telegram, Slack, Discord, WhatsApp, CLI, desktop | Free + model costs | **Depth**: learns, writes its own skills |
| [[claude-cowork]] (+ [[claude-dispatch]]) | Anthropic | Jan 2026 (GA Apr) | Your desktop, or Anthropic's cloud | Claude desktop, web, mobile | All paid Claude plans (from $20/mo) | Claude Code for non-code work; visible, steerable steps |
| [[gemini-spark]] | Google | May 2026 (I/O) | Google Cloud | Email it; Gmail, Docs, Gemini app | In $100/mo AI Ultra | Already lives in your Google data |
| [[grok-bot]] | xAI | Aug 2026 | Vendor cloud computer | Grok app, Cursor | SuperGrok / Cursor tiers | Learns from demonstration; sold via Cursor too |
| [[meta-muse-agent]] | Meta | Sep 2026 (US) | Meta "Secure VM" | Muse app, web, WhatsApp | Mostly free; ~$20/$100 tiers | Mass-market errands; a separate "Sentinel" agent approves anything sent out |
| [[openai-dots]] | OpenAI | 29 Sep 2026 | Vendor cloud computer | ChatGPT, Codex, Slack, Teams | ChatGPT Pro / Business Premium | Pursues goals; "teams of Dots" promised |

Not covered yet: Microsoft Copilot Autopilot (private preview in M365) and the many OpenClaw forks (NanoClaw, ZeroClaw, PicoClaw, IronClaw…).

### Screenshots

| | |
|---|---|
| ![Hermes Agent](https://screenshotit.app/https://hermes-agent.nousresearch.com/) **Hermes Agent** | ![Claude Cowork](https://screenshotit.app/https://claude.com/product/cowork) **Claude Cowork** |
| ![Gemini Spark](https://screenshotit.app/https://thenextweb.com/news/google-gemini-spark-agentic-assistant-gmail-io-2026) **Gemini Spark** | ![Grok Bot](https://screenshotit.app/https://x.ai/news/introducing-grok-bot) **Grok Bot** |
| ![Muse](https://screenshotit.app/https://muse.ai) **Meta Muse** | ![OpenAI Dots](https://screenshotit.app/https://techcrunch.com/2026/09/29/openai-launches-dots-its-bubbly-agentic-avatar/) **OpenAI Dots** |

## How to choose

- **You want control, privacy, any model, and you're happy tinkering:** Hermes. It's the current open-source default, with safer defaults and more active use than OpenClaw. Expect weeks before the learning loop pays off.
- **You want it inside the tools you already use:** pick the one from your ecosystem: Gemini Spark for Google Workspace, Dots for ChatGPT, Slack and Teams, Cowork if you already pay for Claude, Muse if you live in WhatsApp and want errands done for free.
- **You mostly code:** you may not need one. A well-tuned coding agent (Claude Code + skills + a task tracker) already has much of the "memory", and the personal-agent pitch adds less. Remote access ([[claude-dispatch]]) and scheduled runs cover most of the gap.
- **Security:** these agents hold your email, calendar and credentials, and act without you watching. OpenClaw's skills marketplace was hit by malware, and it had over 130 CVEs by April 2026. Start with read-only access and add permissions slowly. See [[moc-ai-security-incidents]].

## A short history

### 1. The hype wave (January–February 2026)

Peter Steinberger, an Austrian developer, started what became OpenClaw in November 2025 as a side project, first called Warelay, then Clawdbot. In late January 2026 it went viral, for the same reasons the category exists. It ran on your own computer, you texted it from apps you already used, it remembered you, and it *did things*: cleared inboxes, checked you into flights, built websites from your phone. Testimonials called it "the first time I have felt like I am living in the future since ChatGPT" and "feels like early AGI". People bought Mac minis just to run it.

The week was chaotic. After a trademark complaint from Anthropic it became Moltbot on 27 January and OpenClaw three days later. Matt Schlicht launched Moltbook, a social network where these agents posted to each other, and it fed the frenzy. GitHub stars peaked at about 40,000 a week in early February, and forks multiplied (NanoClaw, ZeroClaw, PicoClaw, IronClaw…).

Quietly, the labs were already on the same track: Anthropic had launched [[claude-cowork]] as a research preview on 12 January.

### 2. The comedown (February–May)

The problems came quickly:

- **Security.** In the "ClawHavoc" incident, over 1,400 malicious skills with look-alike names on the ClawHub marketplace were found spreading info-stealing malware. Audits later found about 12% of sampled skills were malicious. Nine CVEs landed in four days in March (one scored 9.9/10), with 138 by April. China restricted state bodies from using it.
- **Misbehaviour.** In the "MoltMatch" case, a student's agent created dating profiles on its own initiative, a vivid example of what goes wrong when an agent acts unsupervised.
- **The founder left.** On 14 February Steinberger joined OpenAI "to drive the next generation of personal agents", and OpenClaw moved to a nonprofit foundation.
- **Reliability.** Frequent releases often broke a messaging channel, and running it meant being your own sysadmin.

Search interest peaked in late January and declined after that. Momentum moved to [[hermes-agent]], which launched with a "learning loop" pitch and safer defaults. On 10 May Hermes passed OpenClaw in daily OpenRouter token usage, while still behind on stars. OpenClaw kept going (2.0 shipped on 30 August) and it still has the most stars, but the excitement had moved on.

### 3. Commercialisation (March–October)

The labs absorbed the idea and removed the setup:

- **17 Mar**: Anthropic's [[claude-dispatch]]: send Cowork tasks from your phone, the most direct answer to OpenClaw
- **19 May**: Google's [[gemini-spark]] at I/O: a 24/7 agent on Google Cloud that you email
- **11 Aug**: xAI's [[grok-bot]]: agent "teammates" with their own cloud computers, also sold through Cursor
- **8 Sep**: Meta's [[meta-muse-agent|Muse]]: free, mass-market, with a separate approval agent
- **29 Sep**: OpenAI's [[openai-dots]] at DevDay: always-on agents that pursue goals, from the company that hired OpenClaw's creator

The hosted products have converged on one shape: **a hosted computer per user, persistent context, broad tool access, and a human checkpoint before risky actions.** They answer the open-source projects' weaknesses (setup, security, reliability) and give up their strengths: your machine, your data, any model.

### What it tells us

- **The idea was right; the packaging wasn't.** OpenClaw showed real demand for an assistant you text and that keeps working. Within nine months every major lab had shipped one.
- **Trust is now the main constraint.** Capability is similar across products. What differs is permissions, approval steps, isolation (Meta's Sentinel, Microsoft's Agent 365 controls) and who holds your data.
- **Open source moved from novelty to niche.** Hermes thrives among people who want control and cheap or local models. Most users will probably get theirs from a lab.

## Entries

**Open source, self-hosted**

- [[openclaw]]: the original; multi-channel gateway and skills hub
- [[alfred-portable-openclaw]]: portable OpenClaw fork for solopreneurs
- [[telegram-topics-openclaw]]: organising OpenClaw with Telegram topics
- [[hermes-agent]]: Nous Research's self-improving agent
- [[hermes-agent-playbook]]: a practical Hermes setup guide

**Hosted, commercial**

- [[claude-cowork]]: Anthropic's agent for files, tools and scheduled work
- [[claude-dispatch]]: hand Cowork tasks from your phone
- [[gemini-spark]]: Google's 24/7 agent inside Workspace
- [[grok-bot]]: xAI's cloud-computer agent "teammates"
- [[meta-muse-agent]]: Meta's free errand-running agent
- [[meta-muse-spark-msl]]: the model behind it
- [[openai-dots]]: OpenAI's always-on goal-pursuing agents

## Related maps

- [[moc-coding-harnesses-skills-frameworks]]: the coding-agent side of the split
- [[moc-agent-workbenches]]: environments for running many coding agents
- [[moc-ai-security-incidents]]: what goes wrong when agents act on their own
- [[skill-vs-agents-vs-claude-md]]: the files these agents are configured with
