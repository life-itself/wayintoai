---
created: 2026-10-21
author: Anthropic
newsletter: weekly
tags: [launch, anthropic, claude, personal-agents, always-on, proactive, cloud-computer, opus-5-5]
---

# Claude Duet

Anthropic's proactive personal agent: a separate app where Claude briefs you each morning, does tasks in its own cloud computer while you're away, and asks before it sends, pays, signs or deletes anything.

![Claude Duet product page: "Get back to what needs you"](/assets/claude-duet-2026-10-21.jpg)

*The Duet product page on launch day, 21 October 2026.*

## Links

- **Announcement**: https://claude.com/resources/articles/claude-duet (21 Oct 2026)
- **Product page and waitlist**: https://claude.com/product/claude-duet
- **Launch post on X**: https://x.com/claudeai/status/2112984664256241837

## Overview

Anthropic describes Duet as "a new app where Claude works as a proactive agent". It "comes to you with what needs your attention, completes tasks you ask of it, keeps working even when you step away, and checks with you before it acts on your behalf." It is aimed at professionals and small-business owners.

You talk to it by text or voice in **one ongoing thread**, in its own iOS and Android app or on claude.ai. Each morning it sends a short brief from your connected apps. After that it checks them **every few hours**, not nonstop, which Anthropic says protects your usage limits. It runs on Opus 5.5 in a cloud VM with its own browser, so your laptop and phone can be off.

It carries over your memory, skills and connectors from your Claude account. Anthropic says it has 6,000+ connectors and plugins. Example jobs: finding unpaid invoices in QuickBooks or Stripe and drafting reminders, preparing payroll in Gusto, sending contracts through Docusign, and building forecasts, decks and small web apps. It can pay through Stripe's Link with a virtual card, or check out with Shop Pay. Both need your approval.

## Safety

- **Approval for consequential actions**: before it sends a message, makes a payment, signs a document or deletes anything, it shows you exactly what it will do and waits.
- **Hard limits**: some things are blocked even with approval, such as trading securities or moving money between accounts.
- **Credentials**: it "never directly sees your passwords or sign-in tokens" (the same design as Claude Managed Agents).
- **Classifiers**: Claude Code's auto-mode classifier checks its actions. A new classifier blocks sharing card numbers and government IDs. It shares health and finance details only when you explicitly tell it to.
- Red-teamed and penetration-tested by an outside firm, and covered by Anthropic's bug bounty.

## Availability

- Research preview by **waitlist**, starting 21 Oct 2026
- **US only**, Pro and Max plans; uses your normal Claude limits (background checks count too)
- Not yet on Team or Enterprise plans

Anthropic's own caveats: it "might misread a thread or miscalibrate what's urgent", personal errands like booking tickets are weaker, and you can't yet watch its browser.

## Why interesting

Duet is Anthropic's entry in the crowded [[moc-personal-agents|always-on personal agent]] market. It follows xAI's [[grok-bot]] (August), Meta's [[meta-muse-agent|Muse]] (September) and OpenAI's [[openai-dots]] (29 September). It has the same shape as the others: a hosted computer per user, your context, broad tool access and a human checkpoint. Its distinctive bets are being **proactive** and **quiet**. It pings you, but only every few hours.

The idea isn't new. With Duet, Anthropic is catching up with the others on the message-first kind of agent, and the more interesting story is the wave as a whole (see the [[moc-personal-agents|guide]]).

It is also a separate product from [[claude-cowork]], which is still the "work on my files and tools while I watch" agent. Duet is the one you *message*, closer to [[openclaw]] than to Claude Code.

## Related

- [[moc-personal-agents]]
- [[claude-cowork]]
- [[claude-dispatch]]
- [[openai-dots]]
- [[meta-muse-agent]]
- [[grok-bot]]
