---
title: What I want from an agent control plane, and why nothing fits yet
description: Running two dozen agent sessions on a laptop is solved. Planning work so it can be handed off, and seeing what needs you across all of it, is not. Here's what I want, what exists, and where the gap is.
date: 2026-10-31
authors: [rufus-pollock]
publish: false
---

**TL;DR:** Running many agent sessions at once is solved; Claude Code does it. What isn't solved is the layer above: a graph of work across all my projects, where I plan, hand off, see what's stuck, and get reminded what I was doing. That's a control plane. Lots of tools run sessions; almost nothing holds the work. And the hard part isn't only software. It's learning to plan and structure work so an agent can pick it up.

## Twenty-three sessions

As I write this I have 23 sessions open in Claude Code. Some are writing code, some are drafting, one is waiting for me to approve a push, two finished hours ago and I haven't looked. It's overwhelming.

The running part is fine. Claude Code runs sessions in parallel, in the background and in the cloud. Agent View lists them all and shows which ones are waiting for me. Projects lets one conversation farm work out to many. Running lots of agents is now a built-in feature.

What's hard is everything around the sessions:

- **What should be running at all?** Which piece of work is next, across a dozen projects, and what does it depend on?
- **What state is the work in, not the session?** A session ending isn't the same as the work being done.
- **What needs me, and why?** When I come back to an agent that's stuck, I've forgotten the context. I need reminding what it was for and what I'm meant to decide.

This isn't only coordination. It's how you plan and structure work in the first place, so it can be handed off. A vague task given to an agent produces vague work, twenty times over. I've written about the individual version of this in [AI for Knowledge Work](/use/knowledge-work). This post is about the project level: planning and coordinating so that agents can pick the work up.

## What I want

Five things.

1. **A graph of work across all my projects.** Not a board per repo. One graph, with dependencies, where I start by planning and then hand off: "I've done the planning, now build the roadmap, now execute."
2. **An overview that tells me what needs me.** A dashboard where I can see "that agent isn't working", which reminds me of the context and what I need to do next. Ranked for me, not a wall of panes.
3. **Coordination between agents.** Agents that hand off to each other through the shared graph, so nobody does the same task twice and the state lives in the ledger, not in any one session.
4. **Harnesses, so more of it runs unattended.** A harness is the scaffolding around an agent run: the instructions, tools, budget and checks that take it from a work item to a result I can review without having watched. Planning, then roadmap, then execution, with less of me in the middle.
5. **A learning loop.** As the work runs, what we learn should flow back and improve the harness, the prompts and the process. Improvement should be part of the work graph too, not something I get round to on Sundays.

## What I do today

Some of this I can already do by hand, and it's where I'd start if you have 23 sessions too.

I keep all my work in [Beads](/ref/how-to-plan-with-beads), a small issue tracker that agents can read and write from the command line. Each project has an epic; under it, tasks with dependencies between them. Planning is its own step, done with an agent: we write the goal and what "done" looks like, break it into tasks, and order them. Only then do I hand off, often by telling a fresh session "pick up the next ready task in this epic".

What makes a task something an agent can pick up is mostly boring. It says what done looks like. It names the files or area. It says what's already been ruled out. It's small enough to finish in one session. A task that needs me to explain it again in chat wasn't ready.

That gets me points 1 and 3 within a project, and a little of point 4. What I don't have is the view across projects, anything that tells me which of the 23 needs me, or any of point 5.

## What exists

I looked at what Hacker News has seen and upvoted since January 2025, about 35 posts ([full survey](/ref/hn-agent-control-planes-survey)), plus the tools from my [fleet-of-agents survey](/posts/2026-08-10-fleet-of-agents-survey). They fall into four groups.

### Many sessions, one laptop

![Conductor](https://screenshotit.app/https://www.conductor.build/)

Desktop apps and terminals that run several Claude Code or Codex sessions side by side, usually one git worktree each, often as a kanban board: Conductor (228 points), Kanbots (263), Vibe Kanban (195), Emdash, Superset, cmux and a dozen more. They do well on HN and new ones arrive every month.

They give you panes, not a graph. The unit is the session, each scoped to a repo on your machine. Nothing plans, nothing coordinates, and when you close the laptop it stops. I covered the best of them in [the Cursor-alternative post](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai). Anthropic keeps building this layer into Claude Code itself.

### Run agents remotely

![Omnara](https://screenshotit.app/https://www.omnara.com/)

Omnara (310 points) and Boxes.dev let you run Claude Code from anywhere or in the cloud. That answers "my laptop is closed", not "what should be running".

### Sandboxes and runtimes

![NVIDIA OpenShell](https://screenshotit.app/https://github.com/NVIDIA/OpenShell)

The hot topic. NVIDIA's OpenShell got 508 points on 22 October, and YC has funded Runtime and OneCLI. They isolate agents, keep credentials out of them and scope what they can touch. That's the foundation for unattended runs, but a runtime is where agents run, not what they work on.

### Orchestrators

This is the group actually trying to be a control plane.

![Gas Town](https://screenshotit.app/https://github.com/gastownhall/gastown)

**Gas Town** (Steve Yegge; 354 points for the launch, 403 for Maggie Appleton's essay on it) was the breakthrough for me. Coordination lives on a shared ledger, Beads, not in any one session. Workers pick up work from the graph and hand off through it, and the graph survives when a session dies. It's the closest thing to points 1 and 3. It's also Claude-only, idiosyncratic (Mayors, Polecats, a Refinery), and built for one person at a terminal.

![Claude Code Agent Teams](https://screenshotit.app/https://code.claude.com/docs/en/agent-teams)

**Claude Code Agent Teams** (396 points) is Anthropic's own: a lead session and teammates sharing a task list and a mailbox. The coordination is real but lasts one bounded run; when the job is done the team is gone. Teamwork within a task, not a backlog across projects. (I'm not sure I'm using it well enough yet; that needs its own write-up.)

![Optio](https://screenshotit.app/https://github.com/jonwiggins/optio)

**Optio** (88 points) is the most concrete ticket-to-PR loop. It pulls a ticket, runs an agent in an isolated Kubernetes environment, feeds CI failures and review comments back, and merges when green. That's a proper harness. It's ticket-shaped rather than graph-shaped, and it assumes Kubernetes.

![Paperclip](https://screenshotit.app/https://github.com/paperclipai/paperclip)

**Paperclip** models a company as an org chart of agents with roles, goals, budgets and approvals. It has over 100,000 GitHub stars and never got past 4 points on HN. For my purposes HN is right: an org chart tells you who reports to whom, not what blocks what.

(There's also a cluster of "company brain" tools, Hyper, Almanac and OzBrain, that give agents shared memory. Useful context, but not planning.)

### How they score

| | Work graph across projects | What needs me | Coordination | Unattended harness | Learning loop |
|---|---|---|---|---|---|
| Laptop workbenches | no | sessions only | no | no | none seen |
| Remote runners | no | sessions only | no | partly | none seen |
| Sandboxes | no | no | no | the base for it | none seen |
| Gas Town | yes, on one machine | weak | yes | partly | none seen |
| Agent Teams | one run | no | yes, in one run | partly | none seen |
| Optio | tickets | PR state | no | yes | none seen |
| Paperclip | org chart | dashboard | yes | partly | none seen |

I wasn't looking for learning loops specifically, but I didn't come across one.

## What we tried

At Datopian, my open-data company, we hit the company-sized version of this: eight people, client and product work, and agents doing more of it every month.

We started on Gas Town, because the ledger was the right idea. It didn't survive a headless server. Gas Town starts agents by reviving tmux panes, and on a machine nobody has sat at there are no panes, so for ten days no work could reach an agent. Its patrol agents, the ones that watch the others, also cost about $13 a day while idle, because the watching was done by a model. The lesson I took: anything that can be plain code should be. Checking whether work is stuck doesn't need a model.

So we kept the ledger and replaced the rest with a plain runner and a monitor that makes no model calls. That became [OpenBases](https://github.com/datopian/openbases), our version for companies that want to run this layer on their own servers. It's alpha: one company, on staging. And it doesn't do point 5 either; the learning loop is designed, not built.

If you're one person with 23 sessions, it's not where you start. Your problem is the same, though, and so is the missing piece.

## Where the gap is

The edge, as I see it, is something like Gas Town plus a control plane: a shared ledger that holds the work, with a layer on top that plans, shows you what needs you, and learns.

**The work graph.** Planning is the step whose mistakes get multiplied by every agent that acts on it. A graph of work across projects, with dependencies and state, lets you plan once and hand off many times. It also makes "what needs me" answerable: a stalled task in the graph, with its context attached, rather than a terminal that's gone quiet. Harnesses hang off the graph. Each kind of task, such as a bug fix, a draft or a research note, gets its own instructions and checks, so it can run without me.

**The learning loop.** This is the part nobody has. Every run produces evidence: what was asked, what it cost, whether the PR merged, what the reviewer changed. That evidence should flow back into the harness for that kind of task, so the next run is better. Today it flows into my head, if I notice, and stays there.

Whoever builds that loop on top of a shared work graph builds the thing that matters. It might be Anthropic, if Agent Teams grows a backlog. It might be Gas Town, if it goes headless. It might be someone I haven't found.

If you're running a lot of agents and have found something that does this, or built your own, I'd like to hear about it.

## Related

- [HN survey: agent control planes](/ref/hn-agent-control-planes-survey): the evidence for "What exists".
- [Fleet of agents: a survey of orchestration tools](/posts/2026-08-10-fleet-of-agents-survey): tool-by-tool notes on Gas Town, Optio, Paperclip and Agent Teams.
- [Is there a free, open-source Cursor alternative?](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai): the laptop side of the question.
- [How to plan with Beads](/ref/how-to-plan-with-beads)
- [AI for Knowledge Work](/use/knowledge-work)
