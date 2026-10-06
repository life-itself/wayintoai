---
created: 2026-10-06
featured: true
tags: [moc, guide, personal-agents, always-on, openclaw, hermes-agent, openai-dots, grok-bot]
---

# Always-on personal AI agents: a guide

**TL;DR:** An *always-on personal agent* is an AI that lives on a computer (yours or the vendor's), keeps running when you walk away, remembers you, and is something you *message* rather than *open*. OpenClaw made the idea go viral in January 2026. Hermes became the open-source favourite. Since August, every big lab has shipped a hosted version: xAI's Grok Bot, Gemini Spark, Claude Cowork, Meta's Muse and OpenAI's Dots. This page explains the idea, compares the options and maps our entries.

![OpenClaw: the project that started the wave](https://screenshotit.app/https://openclaw.ai)

## What is an "always-on personal agent"?

Everything is an "agent" now, so the word alone tells you little. Claude Code is an agent, ChatGPT runs agents, and so on. What sets this category apart is **how you relate to it**, not how smart it is:

| | Chatbot | Coding agent | **Always-on personal agent** |
|---|---|---|---|
| Examples | ChatGPT, Claude.ai | Claude Code, Codex, Cursor | OpenClaw, Hermes, Dots, Grok Bot |
| How you use it | Open a chat, ask, read | Open a session, drive it on a task | **Message it** (Telegram, Slack, WhatsApp…) and leave |
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
| [[openclaw]] | Community (foundation, OpenAI-backed) | Jan 2026 | Your machine | WhatsApp, Telegram, iMessage, Signal, Slack… | Free + model costs | **Breadth**: most channels, huge skills marketplace |
| [[hermes-agent]] | Nous Research | Early 2026 | Your machine / VPS | Telegram, Slack, Discord, WhatsApp, CLI | Free + model costs | **Depth**: learns, writes its own skills |
| [[grok-bot]] | xAI | Aug 2026 | Vendor cloud computer | Grok app, Cursor | SuperGrok / Cursor tiers | Bots that learn from demonstration; also sold via Cursor |
| Gemini Spark | Google | May 2026 (I/O) | Google Cloud | Gmail, Docs, Gemini app | In $100/mo AI Ultra | Lives in your Google data; you email it like a colleague |
| Claude Cowork (with [[claude-dispatch]]) | Anthropic | Mar 2026 → GA Sep 2026 | Vendor cloud + your Mac | Claude web/desktop/mobile | Claude Max ($100–200/mo) | Visible, steerable work; approval on risky steps |
| Muse agent | Meta | Sep 2026 (US) | Meta "Secure VM" | Meta AI app, WhatsApp | Free tier; ~$20/$100 plans | Mass-market errands; a separate "Sentinel" agent approves outbound actions |
| [[openai-dots]] | OpenAI | 29 Sep 2026 | Vendor cloud computer | ChatGPT, Codex, Slack, Teams | ChatGPT Pro / Business Premium | Goal-pursuing; "teams of Dots" promised |

Not covered yet: Microsoft Copilot Autopilot (private preview in M365) and the many OpenClaw forks (NanoClaw, ZeroClaw, PicoClaw, IronClaw…).

### Screenshots

| | |
|---|---|
| ![Hermes Agent](https://screenshotit.app/https://hermes-agent.nousresearch.com/) **Hermes Agent** | ![Grok Bot](https://screenshotit.app/https://x.ai/news/introducing-grok-bot) **Grok Bot** |
| ![Claude Cowork](https://screenshotit.app/https://www.anthropic.com/product/claude-cowork) **Claude Cowork** | ![Gemini Spark](https://screenshotit.app/https://thenextweb.com/news/google-gemini-spark-agentic-assistant-gmail-io-2026) **Gemini Spark** |
| ![Meta Muse](https://screenshotit.app/https://www.vktr.com/ai-platforms/meta-launches-muse-a-personal-ai-agent-that-browses-the-web-makes-purchases/) **Meta Muse** | ![OpenAI Dots](https://screenshotit.app/https://techcrunch.com/2026/09/29/openai-launches-dots-its-bubbly-agentic-avatar/) **OpenAI Dots** |

## How to choose

- **You want control, privacy, any model, and you're happy tinkering:** Hermes. It's the current open-source default, with safer defaults and more active use than OpenClaw. Expect weeks before the learning loop pays off.
- **You want it inside the tools you already use:** pick the one from your ecosystem: Gemini Spark for Google Workspace, Dots for ChatGPT, Slack and Teams, Cowork if you already pay for Claude Max.
- **You mostly code:** you may not need one. A well-tuned coding agent (Claude Code + skills + a task tracker) already has much of the "memory", and the personal-agent pitch adds less. Remote access ([[claude-dispatch]]) and scheduled runs cover most of the gap.
- **Security:** these agents hold your email, calendar and credentials, and act without you watching. OpenClaw's skills marketplace was hit by malware, and it had over 130 CVEs by April 2026. Start with read-only access and add permissions slowly. See [[moc-ai-security-incidents]].

## A short history (draft)

*To expand. Outline:*

1. **The hype wave (Jan–Feb 2026).** Clawdbot → Moltbot → OpenClaw goes viral ("feels like early AGI"). People buy Mac minis to run it, Moltbook appears, forks multiply. Stars peak at about 40k a week in early February.
2. **The comedown (Feb–May).** Creator Peter Steinberger joins OpenAI (Feb), and OpenClaw moves to a foundation. The ClawHavoc malware incident and a run of CVEs follow. Search interest falls after late January. Hermes overtakes OpenClaw in daily OpenRouter usage in May.
3. **Commercialisation (Mar–Oct).** The labs absorb the idea. Anthropic ships Dispatch and Cowork, Google ships Spark at I/O, xAI ships Grok Bot, and in late September Meta's Muse agent and OpenAI's Dots arrive. The common shape is a hosted computer, persistent context, tool access and human checkpoints. Competition shifts from demos to distribution and trust.

## Entries

- [[openclaw]]: the open-source original; multi-channel gateway and skills hub
- [[alfred-portable-openclaw]]: portable OpenClaw fork for solopreneurs
- [[telegram-topics-openclaw]]: organising OpenClaw with Telegram topics
- [[hermes-agent]]: Nous Research's self-improving open-source agent
- [[hermes-agent-playbook]]: a practical Hermes setup guide
- [[grok-bot]]: xAI's cloud-computer agent "teammates"
- [[claude-dispatch]]: Anthropic's phone-to-desktop task handoff, part of Cowork
- [[openai-dots]]: OpenAI's always-on goal-pursuing agents
- [[meta-muse-spark-msl]]: the Meta model behind the Muse agent

## Related maps

- [[moc-coding-harnesses-skills-frameworks]]: the coding-agent side of the split
- [[moc-agent-workbenches]]: environments for running many coding agents
- [[skill-vs-agents-vs-claude-md]]: the files these agents are configured with
