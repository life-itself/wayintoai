---
title: Bookmarking in the age of AI
description: Why use a bookmarking app when AI plus a markdown repo does it better? Capture is simple, the gardening is now largely automatic, and bookmarks become papertrails and knowledge bases.
date: 2026-09-28
---

**TL;DR:** AI has changed bookmarking, like so much else. I don't need a dedicated app or service any more: an AI agent plus a plain markdown repo does it, and does more. The part that always made bookmarks useful over time, the gardening (tagging, weeding, linking, summarising), is something I never kept up with. It can now be largely automatic if things are set up well. So bookmarks become something richer: **papertrails** of what I found and thought during a session, feeding curated **knowledge bases**. Starting was easy (paste to an AI, or drop via Telegram). Now that I do it all the time, I'm hitting some real tensions, and they point to what the next step looks like.

## Why an app, when you have AI and a repo?

This is a pattern I keep noticing. Lots of things that used to need a dedicated app or service now reduce to *AI + a folder of markdown* (or a spreadsheet, or a git repo). Bookmarking is a clear case.

A bookmarking app does three things: capture a link, store it, and help you find it again. Capture is now "paste the link to an AI with a sentence about why." Storage is a markdown file in a git repo I own, open, portable and versioned, and not locked into anyone's system. Finding it again is the AI reading the repo. Nothing there needs a special service.

And the AI does something no bookmarking app ever did well for me: it writes a proper entry. A summary, a screenshot, my comment, and links to related things I already have. I often just say "make links between this and other things," and it does.

## The gardening is now (mostly) automatic

Here's the honest bit. Bookmarking never quite failed me, but I failed bookmarking. I've wanted a good tool for at least a decade (Pinboard, buku, the Evernote clipper, Are.na, Trello, Airtable, spreadsheets). The capture was never really the problem. The problem was that bookmarks only become valuable over time if someone gardens them: tags them, weeds out the dross, groups them, connects them to what you're working on. I never kept up with that, so they piled up and went stale.

That gardening is exactly the kind of work AI is now good at. If the knowledge base has clear instructions (what goes here, how entries look, how to link), then an agent can file, tag, summarise and cross-link as it goes, and tidy up later. The chore that made bookmarks worthless in my hands is the part that's become cheap.

## Papertrails, not bookmarks

What I actually want isn't a pile of individual bookmarks. It's a **papertrail**: the trail of a session. I was looking into X, found this, then this, thought that, took a screenshot here. The sequence and the commentary matter as much as the links, because it's how I retrace my thinking later.

I've kept papertrails for years as a section in my daily notes. The difference now is that AI can take that raw trail and turn it into something structured and linked, without me stopping to do the filing.

## Knowledge bases, plural

Where these trails end up is a set of knowledge bases, one per area rather than one giant one:

- [Way into AI](/) (this site): what I'm learning about AI tools and agents. A lot of its references and [logs](/logs) started as exactly this kind of quick drop.
- [rufuspollock.com](https://rufuspollock.com): my personal site and logs, where the general papertrail lands.
- Others for specific topics, e.g. collective action.

Maybe it should all go in one place. But I'm curating, not just saving, and separate knowledge bases with their own conventions are worth it. That's the real shift: **bookmarking has turned into knowledge-base building**, and AI makes that affordable for one person.

## How it's going: easy to start, now some tensions

Getting started was easy. At first I'd simply paste a link and a comment into an AI session, or drop it via Telegram to an agent ([OpenClaw](/ref/openclaw) at first, now [Hermes](/ref/hermes-agent)), which wrote it into the right repo. It worked well enough that I now do it every day, all the time.

Doing it all the time has surfaced some tensions:

1. **Weak model at the front door.** The Telegram bot runs on a cheap model and makes mistakes often. There's also a disjunction: I drop something, then it asks what I want done with it. Meanwhile the repos themselves have good agent instructions a stronger model would follow.
2. **Where does it go?** Each capture carries a small routing decision: which knowledge base? That decision is exactly what kills a fleeting capture.
3. **The laptop path is a context switch.** Open the repo, `cd`, start an agent, paste the link, paste my commentary, submit, wait for it to process, wait for it to commit. Sometimes that's worth it. Mostly I just want the thing captured.
4. **Some days I capture too much.** Not everything should go in. I'd like a quick end-of-day look at the lot, rather than everything being committed as it comes.

I've actually built half of an answer before. [InboxApp](https://tryinbox.app/) is a hyper-minimal macOS inbox I made: one keystroke and you're on a blank page, "capture fast, process later." I used it, and the capture part was great. But I didn't process the inbox reliably, which is the same lesson as bookmarking. Capture is easy. Processing is where it falls down if it depends on me.

## What's now possible

Put those together and the shape of the next step is clear, and it's genuinely new, because AI can be the processing step:

1. **Capture, dumb and instant.** One key switch from anywhere (a hotkey on the laptop, Telegram on the phone). Dump a link, an image, a screenshot, some text, or a quick verbal note about what I want. No routing decision and no model at this point. It just lands.
2. **AI processing, as its own step.** A strong model reads each item with my note, knows my knowledge bases and their conventions, and suggests where it goes, what the entry looks like, and what to link it to. If it's obvious, it just does it and tells me (with undo). If not, it batches it for a quick approve-all at the end of the day.
3. **The agent boots itself when needed.** When something needs polish or clarification, it opens an agent in the right repo with the item already loaded: "I've booted this up for you, here you go."

All of it stays as markdown in my own repos. No new service needed, just AI, some good instructions, and a thin layer of glue.

Next step is small: write down my knowledge bases with a line on what goes where, and try a strong model on a week of real drops to see how often its routing guess is right. If it's right most of the time, auto-apply becomes realistic, and I'll build the one-key capture on top.

If you're doing something like this, or know a tool that already does, [tell me](https://rufuspollock.com).
