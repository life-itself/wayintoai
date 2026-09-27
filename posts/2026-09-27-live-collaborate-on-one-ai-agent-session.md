---
title: Is there a tool for two people to drive one AI agent session together, live?
description: I want VS Code Live Share, but for a coding-agent session — both of us typing into the same repo, same terminal, same prompt, at once. Here's what I found instead.
date: 2026-09-27
---

**TL;DR:** No single tool does "Live Share for agent sessions." Stitch two things: a raw shared terminal (**sshx**, or VS Code Live Share's read-write terminal mode) so you can both type into the same running `claude`/`codex` session, plus something separate for writing the prompt/spec together (**Claude Cowork's Docs**, or a shared doc). **Zed** is the one editor that already does true multiplayer editing and runs Claude Code side by side — untested by me whether two people can co-steer the *same* agent turn, or only watch it together.

## Situation

I was trying to work through a real question with a colleague — the kind of thing behind the [Cursor-alternative post](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai): what's the right tool, does something exist, let's figure it out together. In the old days that's a Google Doc, both of us typing into the same page. Now I wanted the same thing but agent-enabled: not just co-writing text, but co-driving an actual coding-agent session — same repo, same terminal, both of us able to type, at the same time.

I remembered VS Code used to have a "Live Share" feature: log in, and two people could edit and even drive the same session together. I don't know if that still exists, or if anything like it exists for AI agent sessions specifically.

## Complication

What I actually did was screen-share and narrate: "type this," "no, try that instead." That works, but only one of us can ever hold the keyboard. It's not collaboration, it's dictation.

The tools I already know from surveying this space — Superset, cmux, bb, Claude Projects — are all single-driver. One person's login, one person's keyboard, one pane. None of them have a second cursor.

And there's a second, separate want tangled up in this: **writing the prompt together**. Before you hand a task to an agent, you and a colleague are often drafting the spec, the bug report, the plan — and that's exactly the kind of thing you'd normally do in a shared Google Doc. I don't know of anything that's both agent-aware and lets two people type into the same prompt at once.

## Question

Is there a free or simple way for two people to co-drive one agent session — same repo, same terminal, same running `claude`/`codex` process — in real time, with both of us able to type? And separately: is there a "Google Docs but agent-aware" for writing the prompt itself together?

## What I found

I haven't tried any of these myself yet — this is "here's what looks promising," not a verdict.

**Raw shared terminal — agent-agnostic, should just work:**

- **[sshx](https://sshx.io)** — open source (Rust), share a terminal by link, multiplayer cursors and chat on an infinite canvas, end-to-end encrypted. Since it's just sharing the shell, running `claude` or `codex` inside it means both people can type into the same agent conversation. This looks like the closest match to what I actually want.
- **VS Code Live Share** — still exists. Its shared-terminal feature has a read-write mode where "everyone can type," not just the host. Same idea as sshx but inside an editor you may already have open, with file co-editing alongside it.
- Older, simpler alternatives in the same family: **Upterm** and **tmate**, both SSH-based instant terminal sharing, read-only or read-write links.

**Zed — native multiplayer editing, agent running alongside it:**

Zed has real multiplayer collaboration as a core feature (shared cursors, voice chat, true co-editing in one file) and, separately, an Agent Panel that runs Claude Code natively via the Agent Client Protocol. Zed's own marketing says you can "follow the agent as it navigates your codebase, with the same multiplayer infrastructure that powers human collaboration, now shared with AI." That's suggestive — it implies collaborators might be able to follow (or steer?) the same agent turn — but I couldn't confirm from the docs whether two humans can actually co-drive one agent conversation, or only watch it together the way you'd follow a teammate's cursor.

**Replit — multiplayer workspace, but not one shared agent:**

Replit's multiplayer mode puts several people in the same workspace with a shared terminal and console, and each person can start their own Agent thread that lands on a shared Kanban board. That's real-time collaboration *around* agent work, not two people driving *one* agent conversation.

**The other half — writing the prompt together:**

- **[Claude Cowork's Docs](https://claude.com/product/cowork)** feature is the closest thing to what I actually meant by "Google Docs but agent-enabled": multiple colleagues edit one document in real time, with Claude drafting sections and commenting alongside the humans. That's a good fit for co-writing a spec or a plan before it becomes agent work.
- **[Claude Tag](https://claude.com/docs/claude-tag/overview)** (Claude in Slack) is Anthropic's actual "multiplayer Claude": one shared Claude identity that everyone in a channel can give work to and steer, building context over time. It's async and channel-based rather than a live pair-programming session, but it's the one place a team already shares one Claude conversation.

## My take

Nothing packages this as one product yet. The pieces exist separately:

- **Want to literally co-drive one agent's terminal, live?** Try sshx or VS Code Live Share's read-write terminal — the agent doesn't care who's typing, so this should just work despite not being purpose-built for it.
- **Want to co-write the prompt or spec first?** Cowork's Docs is built for exactly that.
- **Want one Claude your whole team shares over time, not live pairing?** Claude Tag.
- **Want an editor where multiplayer and the agent panel are both first-class, in one app?** Zed — but verify yourself whether the agent side is actually co-steerable before counting on it.

Next step is to actually run `claude` inside an sshx session with a colleague and see whether it's as simple as it sounds, or whether output scrollback and interrupts make two-person typing chaotic in practice.

## Related

- [Is there a free, open-source Cursor alternative that uses my own AI subscriptions?](/posts/2026-09-26-free-cursor-alternative-control-pane-for-ai)
- [Claude Projects (redesigned)](/ref/claude-projects) — Anthropic's own coordinator, but single-user: no sharing a project or its threads with another person
