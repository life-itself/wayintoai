---
created: 2026-10-30
tags: [survey, hacker-news, agent-orchestration, control-plane, coding-agents, work-graph]
---

# HN survey: agent control planes (October 2026)

What Hacker News has seen, and upvoted, in agent orchestration, workbenches and control planes since January 2025.

![Hacker News search for agent orchestrator](https://screenshotit.app/https://hn.algolia.com/?q=agent+orchestrator)

## Why I looked

I'm not after another way to run many agent sessions on one laptop; Claude Code already does that well. What I want is a **control plane**: a graph of work across many projects, where I plan, hand off to agents, see which agent is stuck, and get reminded of the context and what I need to do. Gas Town was the breakthrough here, because it put coordination on a shared ledger ([[2026-08-10-fleet-of-agents-survey|fleet survey]]). This survey checks whether anyone has shipped that yet.


I searched HN (via Algolia) on 2026-10-30 for stories since January 2025 with more than 40 points. Points and comments as of today. Links go to the HN thread.

## What's going on

- **Running many sessions on a laptop is crowded and does fine.** A desktop app or terminal that runs several Claude Code or Codex sessions in parallel, often as a kanban, typically gets 100–260 points. There are a dozen of these, and new ones keep coming.
- **Sandboxed runtimes for agents are the hot topic right now.** NVIDIA's OpenShell got 508 points on 22 Oct, and YC has funded several (Runtime, OneCLI). The question has moved from "how do I run ten agents" to "how do I let a team run them safely".
- **Real orchestration posts do worse than you'd expect.** Optio got 88 points and Hephaestus 81, and Paperclip never got past 4. The exceptions are first-party (Claude Agent Teams, 396) or a famous name (Gas Town, 354–403).
- **The essays get the best discussion.** Simon Willison on parallel agents, "your orchestrator is a bad clone of Elixir", and the Gas Town critiques all drew long threads. The recurring complaints: review is the bottleneck, costs run away, and handoff and memory between sessions are poor.
- **Nobody owns the shared graph of work.** Almost everything is one person's sessions on one machine. Hardly anything runs headless, holds the work for a whole team of people and agents, costs each task, and shows a person what needs them. That's the gap I keep running into (see "Why I looked"). Even Beads has competition: "I replaced Beads with a simpler Markdown tracker" got 84.

## Many sessions, one laptop

| Pts | Comments | Date | Post |
|---|---|---|---|
| 263 | 166 | 2026-05 | [Kanbots – Kanban desktop app that runs parallel agents on every card](https://news.ycombinator.com/item?id=48239413) |
| 228 | 115 | 2025-07 | [Show HN: Conductor – run a bunch of Claude Codes at once (Mac)](https://news.ycombinator.com/item?id=44594584) |
| 206 | 71 | 2026-02 | [Show HN: Emdash – open-source agentic development environment](https://news.ycombinator.com/item?id=47140322) |
| 195 | 132 | 2025-07 | [Show HN: Vibe Kanban – kanban board to manage your coding agents](https://news.ycombinator.com/item?id=44533004) |
| 176 | 85 | 2025-09 | [Show HN: Sculptor – a UI for Claude Code (Imbue)](https://news.ycombinator.com/item?id=45427697) |
| 103 | 52 | 2025-10 | [Show HN: FleetCode – open-source UI for running multiple coding agents](https://news.ycombinator.com/item?id=45518861) |
| 99 | 50 | 2026-03 | [Show HN: VS Code Agent Kanban](https://news.ycombinator.com/item?id=47307169) |
| 96 | 90 | 2025-12 | [Show HN: Superset – terminal to run 10 parallel coding agents](https://news.ycombinator.com/item?id=46368739) |
| 78 | 68 | 2026-10 | [Show HN: Offrun – manage every coding agent from one workspace](https://news.ycombinator.com/item?id=49942434) |
| 75 | 49 | 2026-01 | [Show HN: 1Code – open-source Cursor-like UI for Claude Code](https://news.ycombinator.com/item?id=46637723) |

## Run agents remotely or in the cloud

| Pts | Comments | Date | Post |
|---|---|---|---|
| 310 | 168 | 2025-08 | [Show HN: Omnara – run Claude Code from anywhere](https://news.ycombinator.com/item?id=44878650) (also a Launch HN, 147, and an "open-source alternative to Claude Managed Agents", 114, Oct 2026) |
| 105 | 79 | 2026-06 | [Show HN: Boxes.dev – run Claude Code and Codex in the cloud](https://news.ycombinator.com/item?id=48399358) |

## Sandboxes and runtimes for teams

| Pts | Comments | Date | Post |
|---|---|---|---|
| 508 | 218 | 2026-10 | [NVIDIA OpenShell – safe, private runtime for fleets of autonomous agents](https://news.ycombinator.com/item?id=50198675) |
| 110 | 32 | 2026-07 | [Show HN: OneCLI – credential gateway that keeps secrets out of agents](https://news.ycombinator.com/item?id=49023427) (Launch HN as a team harness, 88) |
| 103 | 30 | 2026-05 | [Launch HN: Runtime – sandboxed coding agents for everyone on a team](https://news.ycombinator.com/item?id=48225040) |
| 60 | 43 | 2026-02 | [Show HN: Klaw.sh – Kubernetes for AI agents](https://news.ycombinator.com/item?id=47025478) |

## Orchestrators: breaking up work and handing it off

| Pts | Comments | Date | Post |
|---|---|---|---|
| 403 | 433 | 2026-01 | [Gas Town's agent patterns, design bottlenecks, and vibecoding at scale (Maggie Appleton)](https://news.ycombinator.com/item?id=46734302) |
| 396 | 224 | 2026-02 | [Orchestrate teams of Claude Code sessions (Agent Teams)](https://news.ycombinator.com/item?id=46902368) |
| 354 | 224 | 2026-01 | [Welcome to Gas Town (Yegge)](https://news.ycombinator.com/item?id=46458936); also [Gas Town Decoded](https://news.ycombinator.com/item?id=46624883) (219), [Does Gas Town 'steal' usage from users' LLM credits?](https://news.ycombinator.com/item?id=47785053) (253) and [From Clown Show to v1.0](https://news.ycombinator.com/item?id=47770124) (113) |
| 230 | 62 | 2026-04 | [Google open-sources agent orchestration testbed Scion](https://news.ycombinator.com/item?id=47675213) |
| 175 | 112 | 2025-08 | [Show HN: Project management system for Claude Code (ccpm)](https://news.ycombinator.com/item?id=44960594) |
| 88 | 60 | 2026-03 | [Show HN: Optio – orchestrate coding agents in K8s, ticket to PR](https://news.ycombinator.com/item?id=47520220) |
| 84 | 51 | 2026-01 | [Show HN: I replaced Beads with a simpler Markdown-based task tracker](https://news.ycombinator.com/item?id=46487580) |
| 81 | 14 | 2025-11 | [Show HN: Hephaestus – autonomous multi-agent orchestration framework](https://news.ycombinator.com/item?id=45796897) |
| 45 | 21 | 2026-02 | [Show HN: Mission Control – task management for AI agents](https://news.ycombinator.com/item?id=47165602) |
| ≤4 | – | 2026 | Paperclip (several posts, none took off) |

## Company knowledge for agents

| Pts | Comments | Date | Post |
|---|---|---|---|
| 93 | 59 | 2026-08 | [Show HN: OzBrain – shared brain between agents and your team](https://news.ycombinator.com/item?id=49394827) |
| 79 | 78 | 2026-06 | [Launch HN: Hyper – company brain for agentic development](https://news.ycombinator.com/item?id=48387095) |
| 59 | 48 | 2026-08 | [Launch HN: Almanac – AI that knows your company](https://news.ycombinator.com/item?id=49511007) |

## Essays and discussions

| Pts | Comments | Date | Post |
|---|---|---|---|
| 189 | 131 | 2026-03 | [Parallel coding agents with tmux and Markdown specs](https://news.ycombinator.com/item?id=47218318) |
| 174 | 138 | 2025-10 | [Embracing the parallel coding agent lifestyle (Simon Willison)](https://news.ycombinator.com/item?id=45489884) |
| 149 | 51 | 2026-02 | [Your agent orchestrator is just a bad clone of Elixir](https://news.ycombinator.com/item?id=47067395) |
| 128 | 32 | 2026-01 | [Agent orchestration for the timid](https://news.ycombinator.com/item?id=46746681) |
| 106 | 120 | 2026-02 | [Building SQLite with a small swarm](https://news.ycombinator.com/item?id=47031268) |
| 41 | 60 | 2026-02 | [Ask HN: Are you using an agent orchestrator to write code?](https://news.ycombinator.com/item?id=46993479) |

## Related

- [[moc-agent-workbenches]]
- [[2026-08-10-fleet-of-agents-survey]] — tool-by-tool notes on Paperclip, Gas Town, Optio and Agent Teams
- [[2026-09-26-free-cursor-alternative-control-pane-for-ai]] — the laptop-side "control pane" question
- [[paperclip]]
