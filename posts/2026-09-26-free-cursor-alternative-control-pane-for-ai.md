---
title: Is there a free, open-source Cursor alternative that uses my own AI subscriptions?
description: I want one place to watch many AI agents at once, on the Claude and ChatGPT plans I already pay for, with Beads in the loop. Here's what exists and what doesn't.
date: 2026-09-26
---

**TL;DR:** Yes, but the useful question isn't "which editor replaces Cursor". It's "which app runs the official Claude Code / Codex CLIs side by side and tells me when one needs me". Right now that's **Superset** (free, source-available), **cmux** (free, and it has a Beads plugin) or **bb** (MIT, plugin-extensible, no Beads plugin yet). Almost nothing shows the *graph* of work, and Anthropic's rules mean many "open-source Cursor" tools can't use your Claude plan at all.

## Situation

I run a lot of AI work at once: several Claude Code and Codex sessions, across projects, each at a different stage. I pay for the subscriptions and I don't want to pay twice through API keys or a middleman. I track the work itself in [Beads](/ref/how-to-plan-with-beads) (`bd`), so the plan already lives as a graph of issues.

Cursor has the shape I want: many agents in tiled panes, with a GUI rather than a terminal. As [poteto put it](https://x.com/poteto/status/2058975157503570132), a GUI can offer a lot over a TUI for agentic coding. Being able to open your app in the browser pane and make design changes directly "felt intuitive".

## Complication

Three things get in the way.

1. **Cursor is proprietary and runs on its own credit model.** It's the thing I'm trying to avoid paying for on top of my subscriptions.
2. **A single terminal runs out of room.** I can stack tmux panes, but that doesn't tell me which pane is waiting on me, which finished, and which I forgot.
3. **"Bring your own model" usually means an API key.** In February 2026 Anthropic [clarified](https://gigazine.net/gsc_news/en/20260220-anthropic-third-party-block/) that Pro/Max OAuth tokens are for Claude Code and Claude.ai only, and from April 2026 subscriptions [no longer cover third-party tools](https://www.mindstudio.ai/blog/anthropic-openclaw-ban-oauth-authentication). That rules out most of the open-source editors people recommend as Cursor replacements (Cline, Roo, OpenCode and the like) *if* you want to spend your Claude plan rather than an API budget.

So the constraint is sharper than "open source and free". The tool has to **launch the official CLI** and leave authentication to it.

## Question

Which free tool lets me run many official-CLI agents in parallel panes, shows their state and when they need me, and hooks into Beads so I can see the work behind them?

## What I found

### The pattern that works: wrap the CLI, don't replace it

The tools that fit are terminals or workspaces that *spawn* `claude` and `codex` as they are. Your login and your plan stay untouched, so there's no API key and no policy problem. They add the parts a bare terminal lacks: panes, worktrees and notifications.

| Tool | Free? | Open source? | Runs your own subscription? | How it shows "needs me" | Beads |
| --- | --- | --- | --- | --- | --- |
| **Superset** | Yes ("free forever" on your own machine) | Source-available, [Elastic License 2.0](https://github.com/superset-sh/superset) — not OSI open source | Yes, launches 20+ CLI agents (Claude Code, Codex, Gemini CLI…) | Sidebar status, working indicators, completion chimes, dock badges | No |
| **bb** | Yes | Yes, [MIT](https://github.com/get-bb/bb) | Yes, reuses provider CLI logins (Claude Code, Codex, Cursor, ACP agents) | Live threads you can follow, steer or hand off; task board. Attention alerts not documented | **Not yet**, but plugins can add it (see below) |
| **cmux** | Yes | Yes | Yes, any CLI agent | Notification rings around panes, unread badges, desktop notifications | **Yes**, via [cmux-beads](https://github.com/RaviTharuma/cmux-beads) |
| **Vibe Kanban** | Yes | Yes | Runs CLI agents | Kanban board of tasks and their state | Requested, [closed as not planned](https://github.com/BloopAI/vibe-kanban/issues/1394) |
| **Claude Squad** | Yes | Yes | Yes, tmux-based | Tmux panes | No |
| **Nimbalyst** | Yes | Yes | Says it works with Claude Code and Codex (untested by me) | Session kanban | Own task tracker |
| **Conductor** | Yes | No (closed, macOS) | Claude Code sessions | Dashboard | No |

Caveats: I've read the docs and repos and haven't run all of these. Superset's stars (14.7k) and Vibe Kanban's (28.2k) tell you they're widely used, not that they're good. "Uses your subscription" here means "runs the vendor's own CLI", which is the reason it's allowed. I haven't checked each tool's terms against your plan.

### Beads is the differentiator

Beads is where I want the graph to live, and this is where the field thins out.

- **cmux + cmux-beads** is the only combination I found that puts Beads in the app you're already working in. It adds a Beads board to the cmux right sidebar (kanban or list) with live status pills that update as `bd` changes. It needs `bd` v0.60+, is MIT-licensed, and is early: version 0.2.4, 25 commits, no stars yet. Install with `cmux sidebar plugin install https://github.com/RaviTharuma/cmux-beads.git`.
- **Vibe Kanban** was asked to integrate Beads, with a read-only MVP proposal. The maintainers closed the request without comment.
- **Standalone Beads UIs** exist ([beads-ui, bdboard, a Beads web monitor](https://github.com/xiaotiantakumi/bdboard)), but they sit beside your agent panes rather than inside them.
- **Gas Town** is built on Beads and treats it as the control plane, but it's Claude-only and idiosyncratic. It's covered in [the fleet survey](/posts/2026-08-10-fleet-of-agents-survey).

- **bb** ([my notes](/ref/bb)) is the one that most closely matches "Cursor, but free and mine". It's an MIT-licensed agent IDE with desktop app, web app, CLI and HTTP API. Its core features (side chat, crons, inline previews, remote access) are themselves plugins, and its own blog post lists a task-management GUI as an example a user can ask an agent to build. That makes a Beads plugin plausible rather than something to wait for. Nobody has built one that I could find, and neither the repo nor the blog mentions Beads. It's young: a "passion project" by its own description, macOS-first with Linux alpha. I couldn't find documentation of attention alerts, which is the feature cmux and Superset are best at.

### Flagging "needs a human" across the graph

This part needs two things wired together, and no single tool does both:

- **Per-agent**: cmux rings the pane, or Superset chimes and badges it, when a session is waiting on input. This is the "come back to this" signal.
- **Per-task**: Beads has `bd human <id>` to flag an issue for a human decision, and `bd ready` / `bd blocked` for what's unblocked or stuck. That's the graph-level view.

Nothing I found joins the two, so a pane that's waiting doesn't automatically appear as a flagged bead. That link is the gap. It looks small enough that a hook or plugin could close it.

### What about an actual editor?

If you want an editor rather than a workspace, the honest answer today is VS Code with the official Claude Code extension, or Zed running Claude Code as an external agent (I haven't verified Zed's current setup). Both use your plan because the vendor's own agent does the work. The editors people usually name as free Cursor replacements are mostly BYO-API-key, which is why they fall out here.

## My take

- **Want it now, and want it to look like Cursor's agent panes?** Superset. It's the nearest free match, and it keeps your subscriptions. The licence is the catch: source-available, not open source.
- **Want Beads in the same window?** cmux plus cmux-beads. It's rough and early, but it's the only one that does it. I already have cmux installed.
- **Want a genuinely open-source GUI you can bend to fit?** bb. Fully MIT, uses your subscriptions, and the plugin model is the most credible route to a Beads-aware control pane, but you'd be building that plugin yourself.
- **Want a simple board?** Vibe Kanban, but without Beads.

Next step is to run cmux-beads against a real backlog for a week and see whether the sidebar tells me what to come back to, or whether I still need something that turns "this pane is waiting" into a flagged bead.

## Related

- [How do I run a fleet of coding agents?](/posts/2026-08-10-running-a-fleet-of-agents)
- [Fleet of agents: a survey of orchestration tools](/posts/2026-08-10-fleet-of-agents-survey)
- [How do I run multiple threads in Claude at the same time?](/posts/2026-08-26-run-multiple-threads-in-claude)
- [cmux](/ref/cmux)
- [bb](/ref/bb)
- [Claude Projects (redesigned)](/ref/claude-projects) — Anthropic's own coordinator-plus-threads answer, Claude Code only, no Beads
