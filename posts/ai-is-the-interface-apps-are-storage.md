---
newsletter_sent: 2026-10-21
newsletter_url: https://wayintoai.com/weekly/2026-w43
title: AI is the interface, apps are storage
description: We used to work in apps, each with its own screens. Now we work in the AI, which builds the views we need, and apps become storage that people and AI read and write.
date: 2026-07-15
authors: [rufus-pollock]
---

**AI is the interface. Apps are storage.** That's the shift I keep coming back to, and I think it's bigger than the obvious story about AI automating tasks. For knowledge work, what's changing is *where you work*. We used to work in apps. Now we work in the AI.

## The old way: an app for everything

For decades we built applications to make knowledge work easier. Word processors, then Google Docs. Spreadsheets. Asana and Trello for tasks, GitHub for issues. Companies spent tens or hundreds of millions of dollars building screens so that humans could manage their work a bit more efficiently.

So each tool was its own interface. You went to Asana for tasks, GitHub for issues, Docs for documents, and you worked in each one's screens, one at a time, holding the overall picture in your head.

```
              You
      ┌────────┼────────┐
      ▼        ▼        ▼
 ┌────────┐ ┌────────┐ ┌────────┐
 │ Asana  │ │ GitHub │ │ GDocs  │
 └────────┘ └────────┘ └────────┘
  own        own        own
  screen     screen     screen
```

## The new way: you work in the AI

Now there are two layers. The AI (Claude, ChatGPT, whichever you use) is the interface: you talk to it, and it builds the views you need. Behind it is storage: the documents and tasks that both people and AI read and write.

```
              You
            ▲     │
      views │     │ talk
            │     ▼
      ┌───────────────┐
      │    Your AI    │   the interface
      └───────────────┘
            ▲     │
       read │     │ write
            │     ▼
 ┌───────────────────────────┐
 │ Storage                   │
 │ docs, plans, tasks        │
 │ (git, Beads, GitHub,      │
 │  Asana, Drive...)         │
 └───────────────────────────┘
```

It's a two-way interface, and both directions are better than what apps gave us.

**In:** you can talk to it. Most of us typed because we had to: dictation was slow and rubbish. Now it works, and talking does something typing doesn't. You give far more context, because it costs you almost nothing. My tip to colleagues is: talk, don't type, even if it's messy. And don't go back and tidy what you said. Just say more.

**Out:** it builds the interface back to you. Your AI can write HTML, so it can render more or less any view you want in real time. A table instead of bullet points. A graph of what depends on what. A plan for the next five hours. For most knowledge work, that bespoke view is now better than the fixed screens of an app, because it's built for the question you're actually asking.

So Asana, GitHub and Google Docs become filing cabinets. You'll still open them sometimes, and there are things they're still best at (real-time co-editing a document, for one). But mostly you won't go and work in them. They're where the work is kept, not where it's done.

## What it looks like in practice

The example that made this click for me: a colleague asked her AI for her tasks, had it write them into a GitHub issue, and then opened the issue to read them. She was halfway there. The AI had already done the work. The issue was just a worse screen to read it on. Stay in the AI.

Here's what working this way actually looks like:

- **"What's on for me today?"** The AI reads my list of projects, goes to where each project's tasks live, and gives me the answer in the shape I need: a short list, a table by project, a plan that fits around my calendar. I talk back: "I've got a call at three and someone needs the contracts by Friday. Reshuffle." It does.
- **"I finished X."** Updating progress is a sentence, not a chore of opening issues and ticking boxes. Because it's easy, it actually happens, so the tasks stay true.
- **"Look at the dependency graph and tell me what's blocking the launch."** Things that used to need a senior executive with two full-time assistants who understood what you were up to.
- **"Turn this mess into a plan."** I talk it through, messily. The AI plays it back as a clear question, proposes a plan, and once I agree, writes the tasks into storage, so the next "what's on?" already knows.

None of this needed me to open an app.

## Choose tools for the AI, not for you

This changes the question you ask of your tools. It used to be: is this a nice interface for me? Now it's: **how well can my AI read and write it?** Is it fast, reliable, cheap in tokens, and well structured?

My own example is task tracking. I've largely moved my tasks from GitHub issues to [Beads](https://github.com/steveyegge/beads), a simple tracker that lives alongside my files. GitHub is slow for my AI: every read or write is an API call, which takes time and burns tokens, and it has no clean way to say "this task depends on that one, which depends on that one". Beads is local, fast, and built around exactly that dependency graph. The funny part is that I've hardly ever used Beads directly myself. I don't need to. I know it works extremely well for my AI.

## Storage matters more than ever

If the app is no longer the interface, you might think it matters less. The opposite is true. **The quality and structure of your storage now matters more than the screens of any app.**

The AI amplifies what it reads. Good, well-structured storage gives you good views and good plans, instantly, on demand. Messy storage gives you tidy-looking views that are wrong. Tasks that were done weeks ago but still show as open, plans scattered across five places, no record of what depends on what: the AI will faithfully turn all of that into a confident, nicely formatted answer.

So the work shifts. Less time learning each app's screens; more care over how your documents and tasks are organised, where they live, and whether the AI can find them. A simple index of your projects saying where each one's documents and tasks are kept goes a long way.

## You still think and steer

This is not "hand everything to the AI". Working this way is a collaboration, not a delegation. What we're handing over is the job apps used to do: building interfaces for us, and doing the filing. The thinking, the judgement and the decisions stay with us.

And you still need to understand something about your tools underneath. Things go wrong, and you want to know what's possible. The good news is that you can ask the AI to explain what's going on, and to show its sources.

It's a new way of working, and it takes practice. But once you've worked in the AI for a while, going back to clicking around an app's screens feels like going back to typing when you could just talk.

*I've written up the practice side of this, with the four everyday situations, in [AI is the interface: how to use AI for knowledge work](/use/knowledge-work/how-to-use-ai).*

## Others saying this

*I'm adding to this list over time as I find others making the same point. Last updated: 2026-10-16.*

I'm far from the only one seeing this, and that's encouraging: convergence is evidence. Here are others making the same or a closely related point.

- **Satya Nadella**, interview on the BG2 podcast with Bill Gurley and Brad Gerstner, December 2024 ([coverage, Outlook Business, Jan 2025](https://www.outlookbusiness.com/artificial-intelligence/microsoft-ceo-satya-nadella-reveals-how-ai-agents-will-disrupt-saas-models)). Business apps are "essentially CRUD databases with business logic", and the logic moves to agents: apps as storage, from the CEO of one of the biggest app makers.
- **Andrej Karpathy**, [Software Is Changing (Again)](https://www.ycombinator.com/library/MW-andrej-karpathy-software-is-changing-again), YC AI Startup School talk, June 2025. Build software for agents, not just humans (llms.txt, agent-readable docs). *(Summarised from secondary write-ups; I haven't rewatched the talk.)*
- **Google Research**, [Generative UI: A rich, custom, visual interactive user experience for any prompt](https://research.google/blog/generative-ui-a-rich-custom-visual-interactive-user-experience-for-any-prompt/), 18 November 2025. The model writes a custom interface for each request instead of you picking an existing app: the "let it build the view" half of the thesis.
- **Jamin Ball**, [Long Live Systems of Record](https://cloudedjudgement.substack.com/p/clouded-judgement-121225-long-live), Clouded Judgement, 12 December 2025. Agents separate the interface for work from the source of truth, and that raises the bar for systems of record rather than killing them. Same point as "storage matters more than ever".
- **Steven Lin**, [SaaS Is Becoming Long-Term Memory for AI Agents](https://stevenlin.substack.com/p/saas-is-becoming-long-term-memory), 15 January 2026. Human, then agent, then local files as short-term memory, then SaaS as long-term memory; choose apps for their APIs and data models. Very close to "choose tools for the AI".
- **Anthropic**, [Cowork research preview](https://claude.com/blog/cowork-research-preview), January 2026. Brings the Claude Code way of working (an AI working directly on your files) to non-developers; the vendor betting that people will work in the AI for "almost everything".
- **Teresa Torres** (via ChatPRD's How I AI), [Claude Code + Obsidian task management](https://www.chatprd.ai/how-i-ai/teresa-torres-claude-code-obsdian-task-management), 19 January 2026. Left Trello for Markdown task files and a `/today` command that builds her day: "what's on today?" in practice.
- **Ethan Mollick**, [A Guide to Which AI to Use in the Agentic Era](https://www.oneusefulthing.org/p/a-guide-to-which-ai-to-use-in-the), One Useful Thing, 18 February 2026. For real work, use agentic apps that work on your files and manage rather than prompt; you still steer.
- **Matt Webb**, [Headless](https://interconnected.org/home/2026/04/18/headless), 18 April 2026, and **Simon Willison**'s [commentary](https://simonwillison.net/b/9416), 19 April 2026. Services will go headless, exposing APIs, CLIs and MCP for personal AIs; Willison notes Salesforce's "Headless 360" and the threat to per-seat pricing.
- **Navin Chaddha** (Mayfield), [The Rise of Personalized and Headless Software in the AI Era](https://www.mayfield.com/the-rise-of-personalized-and-headless-software-in-the-ai-era/), May 2026. Your agent becomes the single interface and SaaS goes headless; as he quotes Salesforce, "the agent interface is the head now".
- **Aaron Levie** (Box), reported in [RuntimeWire, 21 June 2026](https://runtimewire.com/article/aaron-levie-says-agents-will-use-software-100x-more-than-people-and-force-new-sa). Agents will use software "100X more than people", turning enterprise apps into high-volume infrastructure that agents query. *(Secondary report of his X posts and a CXOTalk interview; original not checked.)*
- **Citrix**, [The 7 stage roadmap for human-AI collaboration, 2026 edition](https://www.citrix.com/blogs/2026/06/10/the-7-stage-roadmap-for-human-ai-collaboration-2026-edition/), June 2026. Describes the "second brain" as plain-text files that both person and AI read and write, the same architecture. *(Not yet read in full; seen via search summaries.)*

Know of others? Tell me and I'll add them.
