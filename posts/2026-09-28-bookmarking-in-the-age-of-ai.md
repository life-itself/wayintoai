---
title: Bookmarking in the age of AI
description: AI has quietly replaced my bookmarking apps — I now capture links straight into my knowledge bases via an agent. The capture is great; the routing and the context switch are the pain.
date: 2026-09-28
---

**TL;DR:** I don't use bookmarking apps any more. AI replaced them. I drop a link plus a quick note to an agent (via Telegram or my laptop), and it files it into one of my knowledge bases, like this site, with comments and links to related things. That's far better than a bookmark. The pain is the plumbing: a weak model on the mobile bot makes mistakes, deciding *which* knowledge base is friction, and on the laptop it's a full context switch every time. What I want is one keystroke to dump anything, then AI that routes it, confident guesses applied and the rest batched for a quick approve, and an agent that boots itself up when something needs more work.

## Situation

I've wanted a good bookmarking tool for at least a decade. My old notebooks are full of versions of it: "One research tool to rule them all," "Web clipper / scrapbook," "Bookmark on steroids," "MoodBoardIt." I cycled through Pinboard, buku, the Evernote clipper, Trello, Are.na, Airtable and Google Sheets. They all failed the same way: they broke my flow, or they locked my stuff in their system.

At some point I started what I call **papertrail**: a running section in my daily notes where I dump links, screenshots and one-line reactions as I go, with a link to whatever idea or project each one feeds. It's a trail of what I found and what I thought about it.

Over the last year, AI has quietly taken this over. I now do papertrail every day, all the time, and almost always via an AI agent: a [Hermes](/ref/hermes-agent) agent I talk to over Telegram when I'm on my phone, or Claude Code / Codex on my laptop. I give it a link and a quick verbal note, and it writes the entry into a git repo.

And it's more than bookmarking. The thing I'm really doing is curating **knowledge bases**, plural. I have one per area rather than one big one:

- [Way into AI](/) (this site): everything I'm learning about AI tools and agents. A lot of its references and [logs](/logs) started as exactly this kind of quick drop.
- [rufuspollock.com](https://rufuspollock.com): my personal site and logs, where the general papertrail ends up.
- Others for specific topics, e.g. collective action.

Maybe it should all go in one place. But I'm often curating a bit more than that, and the separate knowledge bases are worth it. With AI, the "bookmark" becomes a proper entry: a summary, a screenshot, my comment, and links to related things I already have. I often ask for exactly that: "make links between what I'm adding and other things." No bookmarking app ever did that.

## Complication

The capture has got heavy-duty. Three pain points:

1. **Weak model at the front door.** The Telegram bot runs on a cheap model and makes mistakes often. And there's a disjunction: I drop the note, then it asks me what I want doing with it. Meanwhile the repos I'm dropping into have good agent instructions a stronger model would follow.
2. **Routing is friction.** Each capture carries a small decision: which knowledge base does this go in? That decision is exactly what kills a fleeting capture.
3. **The laptop path is a full context switch.** Open the repo, `cd` to the directory, start an agent, paste the link, paste my commentary, hit submit, wait for it to process, wait for it to commit. Sometimes that's worth it. Most of the time I just want the thing captured.

I've actually built half of the answer before. [InboxApp](https://tryinbox.app/) is a hyper-minimal macOS inbox I made: one keystroke and you're on a blank page, capture in Markdown, "capture fast, process later." I used it and the capture part was great. The problem was the other half: **I didn't process the inbox reliably**. Items sat there. A capture tool is only as good as the processing that empties it, and I was the processing step.

## Question

What does bookmarking look like when AI does the processing? Capture should be as fast as InboxApp, and processing and routing into the right knowledge base should happen reliably, without me doing the chore.

## What I'm looking for

Split it into three separate parts, each doing one thing well:

1. **Capture: dumb and instant.** One key switch from anywhere (a hotkey on the laptop, Telegram on the phone). Dump anything: a link, an image, a screenshot, a bit of text, and a quick verbal note about what I want. No routing decision and no model in the loop at this point, so nothing can go wrong. It just lands in a queue.
2. **Process: a strong model, as its own step.** Read each item with my note, and know my knowledge bases: what goes in each and how each wants entries written. Suggest where it should go and what the entry looks like, with links to related things. If it's obvious, just do it and tell me, with undo. If it's not, batch it up so at the end of the day I can approve all of it in one go, or drop what isn't worth keeping. Some days I capture too much, and not everything should go in.
3. **Escalate: boot the agent for me.** When something needs polish or clarification, the system should open an AI agent in the right repo with the item already loaded, and tell me "I've booted this up for you, here you go." No more `cd`, start agent, paste.

The key design point, and the lesson from InboxApp: **capture and processing must be separate, and processing must not depend on me remembering to do it.** AI is finally good enough to be that processing step.

## My take

Bookmarking apps are over for me. Not because a better one arrived, but because an AI agent writing into my own git repos beats all of them: it's open, it's mine, and it connects things. What's missing isn't storage or search. It's the thin layer between "I saw something" and "it's in the right place, linked": fast capture, reliable AI routing, and an agent on hand for the cases that need me.

Next step is small: write down each of my knowledge bases with a line on what goes where, and try a strong model on a week of real drops to see how often its routing guess is right. If it's right most of the time, auto-apply becomes realistic, and I'll build the one-key capture on top.

If you know a tool that already does this, [tell me](https://rufuspollock.com).
