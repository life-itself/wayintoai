---
created: 2026-10-06
author: Nous Research
tags: [personal-ai, personal-agents, always-on, open-source, self-hosted, memory, skills, nous-research]
---

# Hermes Agent (Nous Research)

Open-source, self-hosted personal agent whose pitch is that it gets better the more you use it: it writes its own skills, remembers you across sessions, and runs scheduled jobs in the background.

![Hermes Agent](https://screenshotit.app/https://hermes-agent.nousresearch.com/)

## Links

- **Website & docs**: https://hermes-agent.nousresearch.com/docs/
- **GitHub**: https://github.com/NousResearch/hermes-agent (~251k ⭐, Oct 2026)
- **Discord**: https://discord.gg/NousResearch
- **Install**: `curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash`

> **User Experience Note (2026-10-06):**  
> Huge star count, but I've struggled to find it that useful beyond simple jobs like filing links I drop to it via Telegram (see [Bookmarking in the age of AI](/posts/2026-09-28-bookmarking-in-the-age-of-ai)). — Rufus Pollock

## Overview

Hermes is the main open-source rival to [[openclaw]] in the [[moc-personal-agents|always-on personal agent]] category. It launched in early 2026, a few weeks after OpenClaw's viral moment. It is MIT-licensed, written in Python, and works with any model (Nous Portal, OpenRouter, OpenAI, or your own endpoint).

OpenClaw bet on **breadth**: lots of channels and a big skills marketplace. Hermes bets on **depth**, through a *learning loop*. After a complex task it can save what it did as a reusable skill, refine that skill as it uses it, search its own past conversations, and build a model of you over time. The pitch is "the harness comes built in". With Claude Code you hand-craft the CLAUDE.md, skills and hooks yourself. Hermes tries to grow them for you.

## Key Features

- **Learning loop**: creates skills after complex tasks and improves them in use (compatible with the agentskills.io format)
- **Memory**: agent-curated persistent memory, full-text search over past sessions, user modelling (via Honcho)
- **Scheduler**: natural-language cron ("every Monday, audit…")
- **One gateway, many channels**: Telegram, Discord, Slack, WhatsApp, Signal, CLI, plus desktop and web UIs
- **Safer defaults than OpenClaw**: sandboxing, prompt-injection scanning, credential filtering

## Why so many stars?

- **Timing**: it rode the OpenClaw wave and became the place people switched to as OpenClaw's security problems piled up. By May 2026 it had overtaken OpenClaw in daily OpenRouter token usage, while still behind on stars.
- **Open and model-agnostic**: no lock-in, your data stays on your machine, you can run cheap or local models.
- **A compelling idea**: "an agent that grows with you" is an easy story to star.

## Why it may not click

If you already live in Claude Code with a tuned harness, Hermes's main selling point is something you already have. The learning loop also only pays off after weeks of steady use, so a quick trial underwhelms. Its natural user wants a 24/7 assistant they message from their phone, not a better coding agent.

## Related

- [[moc-personal-agents]]
- [[hermes-agent-playbook]]: Prajwal Tomar's setup playbook (SOUL.md, model tiers, profiles)
- [[openclaw]]
- [[openai-dots]]
- [[grok-bot]]
- [[skill-vs-agents-vs-claude-md]]
