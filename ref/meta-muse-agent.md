---
created: 2026-10-06
author: Meta
tags: [meta, muse, personal-agents, always-on, consumer, whatsapp, cloud-computer, security]
---

# Muse (Meta's personal agent)

Meta's consumer personal agent: it runs errands (shopping, booking, forms, email, even negotiating bills) from its own secure cloud computer, and it's mostly free.

![Muse](https://screenshotit.app/https://muse.ai)

## Links

- **Website**: https://muse.ai
- **VKTR coverage**: https://www.vktr.com/ai-platforms/meta-launches-muse-a-personal-ai-agent-that-browses-the-web-makes-purchases/
- **Launched**: 8 Sept 2026 (US)

## Overview

Muse opens a browser, moves through websites, fills in forms and negotiates for you. It keeps working after you close the app and comes back when something changes or it needs approval. It runs on [[meta-muse-spark-msl|Muse Spark]], Meta's flagship model.

Its security design is the most explicit of the big launches:

- **Muse Secure VM**: each user gets an isolated cloud machine with its own browser, storage and compute
- **Sentinel**: a separate agent on the same machine, isolated at system level, that must approve *everything* Muse sends to the internet
- Payments via Stripe Link one-time card numbers; Muse uses saved passwords without seeing them
- Sensitive actions need your confirmation; a "Confidential VM" with user-held keys is coming

## Availability

- US adults; iOS, Android, web; WhatsApp and AI glasses rolling out
- Free for most use; paid tiers (reported ~$20 and ~$100) for heavier use
- Reported 5M+ downloads by early October

## Why Interesting

It's the mass-market play: free, inside apps billions already use, aimed at errands rather than work. Its separate "Sentinel" approver is a concrete answer to the prompt-injection and rogue-action worries that dogged [[openclaw]].

## Related

- [[moc-personal-agents]]
- [[meta-muse-spark-msl]]
- [[openai-dots]]
- [[gemini-spark]]
