---
newsletter_sent: 2026-11-18
newsletter_url: https://wayintoai.com/weekly/2026-w47
title: "AI is the interface: how to use AI for knowledge work"
description: A short manifesto and day-to-day practice for moving knowledge work onto AI, starting with the AI as the interface.
order: 2
date: 2026-10-16
status: v1
authors: [rufus-pollock]
---

# AI is the interface: how to use AI for knowledge work

A short manifesto, then the day-to-day practice. The patterns hold whatever AI or tools you use.

## The manifesto: AI and knowledge work

**AI is transforming how we work. We used to work in apps. Now we work in the AI.**

1. **The AI is the interface.** Start there, not in Asana, GitHub or Docs.[^interface]
2. **Talk to it.** Speak, don't type. It makes starting easier and rich context cheap to give. Don't tidy; say more.[^voice]
3. **Let it build the view.** Ask for the table, plan or graph you need. You don't need an app's screens.
4. **Apps are storage: choose tools more for the AI than you.** We used to pick tools for their interfaces. Now pick them for how well your AI can read and write them. For example, [Beads](https://github.com/steveyegge/beads) is a simple task tracker built to suit AI.[^storage]
5. **Develop processes for both you and your AI.** Develop processes for people and for AI, so that it can take on more of the work over time.
6. **Plan and coordinate through the AI.** Think out loud to plan, report by talking, ask it what's next.
7. **Land the plane.** End a planning or collaborative session by updating the tasks and plans: what got done, what didn't work, where to start next time.[^landing]
8. **You still think and steer.** Working with AI is a collaboration, not a delegation. What we hand over is the job apps used to do: building interfaces for us. The thinking and the decisions stay with us. And if you need to know what's going on underneath, ask the AI, and ask it to show its sources.[^steer]

**It's a new way of working. We need to give ourselves time to practise and adapt.**

## The big picture: interface and storage

Before, each tool was its own interface. You went to Asana for tasks, GitHub for issues, Google Docs for documents, and worked in each one's own screens, one at a time.

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

Now there are two layers. The AI is the interface: you work with it, talking in, and it builds the views you need. Behind it is storage, the shared memory that both people and AI read and write.

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
 │ Storage (memory)          │
 ├╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┤
 │ Reference                 │
 │ docs and plans            │
 │ usually Markdown in git   │
 ├╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┤
 │ Tasks                     │
 │ e.g. Beads, GitHub issues,│
 │ Asana                     │
 └───────────────────────────┘
```

Storage has two main parts, often kept in separate places:

- **Reference:** background, decisions and plans. Usually Markdown files kept in git. It changes slowly.
- **Tasks:** what needs doing, by whom, and what depends on what. These might be in Beads, GitHub issues, Asana or elsewhere. They change constantly.

The tools named here are examples; the patterns hold whichever ones you use.

A project normally has both: reference material (at least a plan) and tasks. The quality of your storage, how well it is structured and how easily the AI can read and write it, now matters more than the screens of any app. The AI amplifies what it reads: messy storage gives tidy-looking views that are wrong.

## Chapters

1. **AI as work interface** (planning and coordinating your work, and the team's). Below, in progress.
2. Later: AI for planning, AI for design, AI for research, AI for automation.

## Chapter 1: AI as work interface

How do you find out what to work on today?

Most of us answer that the way we learned to: open the task app, scan the issues, check email, and piece it together in our heads. This chapter walks through four everyday situations in planning and coordinating work, each told the old way and then the new way.

1. What's on today, or this week?
2. Turning a mess into a plan
3. Updating progress
4. Others picking up the work

They are not separate steps but a loop:

```
 What's on today / this week?      ┌─────────────┐
             │                     │ Storage     │
             ▼                     ├╌╌╌╌╌╌╌╌╌╌╌╌╌┤
        Is it clear?               │ Reference   │
         │        │                │ (and plans) │
        yes       no               ├╌╌╌╌╌╌╌╌╌╌╌╌╌┤
         │        ▼                │ Tasks       │
         │   Make a plan           └─────────────┘
         │        │
         ▼        ▼
        Do the work
             │
             ▼
      Update progress
             │
             └─▶ back to top
```

You ask what's on. If it's clear, you do the work. If it isn't, you stop and make a plan, then do the work. As you go, you update progress, and the loop starts again. Storage sits alongside all of it, and the AI reads and writes it throughout. Because everything lands there, anyone, a colleague or an AI session, can pick up the work.

### 1. What's on today?

**The old way.** You open Asana, then GitHub, then your inbox. Each shows its own slice in its own layout. You hold the whole picture in your head, or copy bits into a list. A colleague of ours, doing it half the new way, asked the AI for their tasks, had it write them into a GitHub issue, and then opened the issue to read them.

**The new way.** You open your AI and say: "What's on for me today?" It reads your portfolio, the list of your projects, which says where each project's documents and tasks live, goes and looks there, and shows you the answer in the form you need: a short list, a table by project, a plan for the next five hours. You talk back: "I've got a call at three and a colleague needs the contracts by Friday. Reshuffle." It does. A good plan for the day starts from your calendar, so it knows how much time you really have, and names the one thing you'd do if you did nothing else. Then stop planning and start. If you're about to work on one project, you open a session in just that project's folder so it isn't wading through everything else.[^torres]

Often the honest answer to "what's on?" is "it isn't clear": a project has no next step, or nothing can be finished today. That's the cue to plan.

**What changed.** You never opened an app. The AI is the interface (1) and built the view you needed (3); you talked to it (2). It could do this because the storage it reads, a portfolio and task lists with dependencies, was chosen to work for it (4).

### 2. Turning a mess into a plan

**The old way.** You write a document about the problem, then type tasks one by one into a tracker, setting fields and ticking boxes as you go. It's slow, so plans stay thin, or never get written down.

**The new way.** You talk it through. A few sentences is enough to start. What's the situation? What has changed or gone wrong? So what question are we actually trying to answer? Say it messily and say a lot; don't go back and tidy. The AI plays it back to you as a clear situation, complication and question, breaks the question into sub-questions, and proposes a plan of work. Let it be opinionated and draft first; your job is to react. You push back, it revises. When you, and anyone the plan affects, agree, it writes the tasks into the shared plan: who owns each, priority or deadline, and what depends on what, so the next "what's on?" already knows.

**What changed.** Planning happens in conversation (6). The AI does the writing up and the filing; the thinking is still yours. Check that the question it plays back is the one you actually meant (7).

### 3. Updating progress

**The old way.** You open the issue, tick the box, write a comment, maybe update a status field in a second tool. Mostly you don't get round to it, so the tracker drifts: tasks done weeks ago still show as open, and nobody trusts it.

**The new way.** Progress gets recorded as part of the work, not after it. There are two kinds:

- **As you go.** Most updates come out of the session itself. You're working with the AI, something gets done or decided, and you say: "OK, now write an update." It updates the task, the plan or the reference document. With AI you find tasks being updated constantly, across many sessions.
- **Landing the plane.** At the end of a planning or collaborative session, a short routine: update the tasks, note what got done and what didn't work (dead ends matter too), say where the next session should start, and ask "what did we learn that should be written down?" If something the AI did needs a person to review it, log that as a task. Whoever picks it up next, you tomorrow, a colleague or an AI session, starts from there.
- **Periodically.** At the end of the week, a more systematic pass: what got done, what's stuck, what's stale. The AI builds this from the same records, so nobody writes a status report from memory.

**What changed.** Updating is a sentence, not a chore, so it actually happens (2, 6, 7). That keeps the plan true, which is what makes every "what's on?" work. A process that is easy for you and readable by the AI (5).

### 4. Others picking up the work

*To discuss.* Handing work to someone else, whether a colleague or an AI session, comes down to the same thing: the work is written up in enough detail that anyone can pick it up. How much detail, and in what form, is still an open question. Talking is still better for judgement, relationships, and anything not yet written down.

## Glossary

- **Storage (memory).** Where work is kept so that people and AI can read and write it. Two main parts: reference and tasks.
- **Reference.** Documents that explain the work: background, decisions, plans. Changes slowly.
- **Tasks.** The things to do, who is doing them and what depends on what. Changes constantly. For example Beads, GitHub issues or Asana.
- **Project.** A piece of work with a goal. It normally has reference material (at least a plan) and tasks, wherever they are stored.
- **Plan.** For us, usually a situation, complication and question (SCQ: what is going on, what has changed or gone wrong, so what are we trying to answer), an issue tree breaking the question into sub-questions, and a plan of work.
- **Portfolio.** An index of your projects saying where each one's reference and tasks live, so the AI knows where to look.
- **Session.** One working conversation with the AI, usually on one piece of work.
- **Landing the plane.** The end-of-session routine of updating tasks and plans so the next session can start cleanly.
- **Beads.** A simple task tracker, kept alongside your files, that records dependencies between tasks and is fast and cheap for AI to use. See [Beads on GitHub](https://github.com/steveyegge/beads).

[^torres]: Others are converging on the same practice. For example, Teresa Torres uses a `/today` command that builds her day's list from task files, having left Trello to do it ([How I AI, January 2026](https://www.chatprd.ai/how-i-ai/teresa-torres-claude-code-obsdian-task-management)).

[^interface]: Others see the same shift. Ethan Mollick on working through agents rather than apps: [Claude Code and what comes next](https://www.oneusefulthing.org/p/claude-code-and-what-comes-next) (January 2026). Matt Webb on services going "headless", with your own AI as the front end: [Headless](https://interconnected.org/home/2026/04/18/headless) (April 2026).
[^voice]: Chris Blattman finds the main benefit of dictation is that it makes starting easier, not that it is faster: [Voice dictation](https://claudeblattman.com/essentials/wispr-flow/).
[^storage]: On apps becoming storage that agents read and write: Jamin Ball, [Long live systems of record](https://cloudedjudgement.substack.com/p/clouded-judgement-121225-long-live) (December 2025), and Steven Lin, [SaaS is becoming long-term memory for AI agents](https://stevenlin.substack.com/p/saas-is-becoming-long-term-memory) (January 2026).
[^landing]: "Landing the plane" is a phrase from the Beads community: see [Beads: memory for coding agents](https://paddo.dev/blog/beads-memory-for-coding-agents) (paddo.dev, December 2025).
[^steer]: Why steering matters. AI output can look finished and be hollow: about 40% of workers say they received such "workslop" in the past month ([Harvard Business Review, September 2025](https://hbr.org/2025/09/ai-generated-workslop-is-destroying-productivity)). Feeling faster is not the same as being faster: in one study experienced developers were 19% slower with AI while believing they were 20% faster ([METR, July 2025](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/); METR has since published a follow-up). And Ethan Mollick argues that working with AI is a management skill: knowing what to hand over and how to check it ([Management as AI superpower](https://www.oneusefulthing.org/p/management-as-ai-superpower), January 2026).

---

*Drawn from Rufus Pollock's notes on AI as the new interface and from practice at Life Itself, October 2026. This is a first version: comments and corrections welcome.*

## Next

[Try it: two exercises →](/use/knowledge-work/try-it)
