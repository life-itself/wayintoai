---
title: "Draft: Chapter 1, AI as work interface"
created: 2026-10-11
status: draft for Rufus's review (not yet in the main guide)
beads: lip-d4l.1
draft: true
publish: false
moved_from: life-itself/planning guides/drafts/ (2026-10-19)
---

*Draft chapter for [How we use AI](https://wayintoai.com/use/knowledge-work/how-to-use-ai). Critiqued 11 Oct; not yet reviewed by Rufus; see [the drafting plan](https://github.com/life-itself/planning/blob/main/docs/plans/2026-10-11-ai-guide-chapter-1-drafting.md) (in planning). Terms such as storage, portfolio and landing the plane are in the guide's glossary.*

# Chapter 1: AI as work interface

A colleague showed me how they were getting through their tasks. They had asked the AI to find everything assigned to them. Good. Then they had it write the list into a GitHub issue (a page in one of our task trackers). Then they opened the issue to read it.

I said: no, stay in the conversation. The list was already there, made for them. They could have asked for it as a table, by deadline, or just the three things that mattered.

It's a natural mistake. We all learned to work in apps, and the habit carries over. This chapter is about breaking it for one kind of work: planning and coordinating, yours and the team's. It starts with a simple question: **how do you find out what to work on today?**

## The loop

Four situations come up again and again:

1. What's on this week?
2. Turning a mess into a plan
3. Updating progress
4. Others picking up the work

They form a loop:

```
 What's on today / this week?      ┌─────────────┐
             │                     │ Storage     │
             ▼                     ├╌╌╌╌╌╌╌╌╌╌╌╌╌┤
        Is it clear?               │ Reference   │
         │        │                │ docs, plans │
        yes       no               ├╌╌╌╌╌╌╌╌╌╌╌╌╌┤
         │        ▼                │ Tasks       │
         │   Make a plan           └─────────────┘
         │        │                  anyone, person
         ▼        ▼                  or AI, picks
        Do the work                  up from here
             │
             ▼
      Update progress
             │
             └─▶ back to top
```

You ask what's on. If it's clear, you do the work. If not, you make a plan first. As you go, you update progress, and round again. Storage sits alongside: the AI reads and writes it throughout, and because everything lands there, someone else can pick up the work.

To make it concrete, we'll follow one project round the loop: **organising a team retreat**. It starts the way most projects do, as "we should really do a retreat".

## 1. What's on this week?

**The old way.** Monday morning. You open Asana, then GitHub, then your inbox, then your calendar. Each shows its own slice in its own layout. You assemble the week in your head, or copy bits into a list that's out of date by Wednesday.

**The new way.** You open your AI and say:

> "What's on for me this week?"

It reads the portfolio (our list of projects, and where each one's documents and tasks live), your tasks and your calendar, and shows you something like this:

| This week | Notes |
|---|---|
| ⭐ Funder report, due Thursday | Draft half done |
| Contracts for Sylvie | Waiting on two signatures |
| Newsletter | Copy ready, needs images |
| Team retreat | **No next step** |

Tuesday is full of meetings, so it suggests the report for Monday afternoon and Wednesday morning. The star marks the one thing to do if you do nothing else.

You talk back: "Sylvie needs the contracts by Friday, move them up. Push the newsletter images to next week." It reshuffles. Then you stop planning and start.[^torres]

Notice the retreat: no next step. When the honest answer to "what's on?" is "it isn't clear", that's the cue to plan.

**What changed.** You never opened an app (1). You talked (2), and it built the view you needed (3). It could do that because the storage it reads was chosen to work for it (4).

**Try this:** "What's on for me this week? Show it as a table and star the one thing that matters most."

## 2. Turning a mess into a plan

**The old way.** Someone starts a document called "Retreat?". It gets three bullet points and stalls. Or the tasks get typed one by one into a tracker, fields and checkboxes, and the thinking never happens.

**The new way.** You talk for three minutes, messily:

> "We should really do a retreat. The last one was over a year ago. People are all over the place, money's tight, two people are away early November. Not sure it even needs to be in person. Someone mentioned a venue near Paris…"

Don't tidy; say more.

The AI plays it back as a situation, a complication and a question:

> **Situation:** the team is spread across countries; the last retreat was over a year ago.
> **Complication:** no dates, no budget, and two people are away in early November.
> **Question:** what retreat can we run before December?

Then it breaks the question into sub-questions (an issue tree) and drafts a plan:

```
What retreat can we run before December?
├── When can everyone come?
├── What can we spend?
└── Where? (depends on when, and on budget)
```

Now the important part. You read it and say: "No. The real question is whether it's in person at all this year." It redrafts:

> **Question:** should this year's retreat be in person or online, and what can we run before December?

That one change reshapes the plan: the tree gains a new first branch, "In person or online?", and the venue question now waits on it. The AI drafted; you saw what mattered. That's the division of labour: it drafts first, with opinions; you judge.

When you agree, it writes the tasks into storage, with what depends on what: the venue waits on dates and budget. Back to "what's on?", which now has a next step for the retreat: ask everyone for dates.

**What changed.** Planning happened in conversation (2, 6). The AI did the writing and the filing; the thinking stayed yours (8).

**Try this:** "Here's a mess I need to sort out: [talk]. Play it back as situation, complication and question, then propose a plan."

## 3. Updating progress

**The old way.** You open the task, tick the box, write a comment, update a status field somewhere else. Mostly you don't get round to it. The tracker drifts: things done weeks ago still show as open, and nobody trusts it.

**The new way.** Updating becomes part of the work, at three moments:

- **As you go.** In the middle of a session: "Dates agreed, 14–16 November. Update the plan and close that task." One sentence. Smaller things work the same way: "Contracts are signed, close it." With AI, tasks get updated constantly, so the plan stays true.
- **Landing the plane.** At the end of a planning or collaborative session, ask the AI to land the plane. It updates the tasks and the plan, and leaves a short note:

  > **Done:** dates agreed (14–16 November), in person.
  > **Didn't work:** the Paris venue is booked that week.
  > **Next, start here:** shortlist two venues.
  > **Learned:** November venues book up early; contact them as soon as dates are fixed.

  Whoever comes next, you tomorrow, a colleague or an AI session, starts from there.
- **Each week.** A more systematic pass: what got done, what's stuck, what's stale. The AI builds it from the same records, so nobody writes a status report from memory.

**What changed.** Updating is a sentence, not a chore, so it happens (2, 6, 7). The same routine works for you and for the AI (5), and it keeps every "what's on?" honest. And when someone else needs to carry on, that's the next situation.

**Try this:** at the end of your next session, "Land the plane: what got done, what didn't work, and where to start next time."

## 4. Others picking up the work

*This is what we're trying now. Still open: how much detail is enough, and in what form.*

**The old way.** A handover email or a call. It's out of date within a week, and only one person heard it.

**The new way.** A colleague, Fae, is taking over the retreat logistics. You say:

> "Fae's taking over the retreat logistics. Write a pick-up note for Fae."

The note points into storage rather than repeating it, and covers:

- the goal;
- where things stand;
- the next step;
- what it depends on;
- where the plan lives;
- who to ask.

Fae opens an AI session, points it at the task, and finds all of that, plus the last landing note. An AI session can pick it up the same way: "Shortlist two venues for the retreat" needs nothing from you but the request.

**A test anyone can run.** Open a fresh AI session and say: "Pick up the retreat." If it finds the next step on its own, the records are good enough. If it can't, fix the records, not the session.

Talking is still better for judgement, relationships, and anything not yet written down.


**What changed.** Handing over is a property of the records, not a meeting. Good storage (4) and shared routines (5) mean a person or an AI can carry on.

**Try this:** "Write a pick-up note for [project]: goal, where it stands, next step, what it waits on, where the plan lives, who to ask."

## Recap

| Situation | What you say | What you get back |
|---|---|---|
| What's on this week? | "What's on for me this week?" | Your week as a view, one thing starred |
| A mess into a plan | Talk it through, messily | Situation, complication, question; a plan; tasks with dependencies |
| Updating progress | "Dates agreed, update the plan." "Land the plane." | A plan that stays true; a note for whoever is next |
| Others picking up | "Write a pick-up note." | Work anyone, person or AI, can continue |

Through all of it, you still think and steer (8). The AI builds the views and does the filing. What matters, and what to do about it, is still your call.

It's a new way of working. We need to give ourselves time to practise and adapt.

[^torres]: Others are converging on the same practice. For example, Teresa Torres uses a `/today` command that builds the day's list from task files, having left Trello to do it ([How I AI, January 2026](https://www.chatprd.ai/how-i-ai/teresa-torres-claude-code-obsdian-task-management)).
