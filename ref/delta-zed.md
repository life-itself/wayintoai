---
created: 2026-10-05
author: Zed Industries
tags: [zed, multiplayer, collaboration, coding-agents, agent-threads, version-control, agent-workbenches]
---

# Delta (Zed) — multiplayer for the AI age

Zed's new multiplayer development environment where the unit of work is a shared *thread*: agent conversation and code changes live together, and teammates can join the same thread live.

![Delta homepage](https://screenshotit.app/https://delta.dev/)

## Links

- Website: https://delta.dev/ (also https://delta.zed.dev)
- Docs: https://delta.zed.dev/docs
- Status: public beta (from 2026-09-16)

> **Rufus's note (2026-10-05):**
> I've been looking for how to collaborate on an AI thread the same way we could with code via VS Code Live Share etc. Multiplayer for the AI age … and Zed have built it. — Rufus Pollock

## Overview

Delta is built by Zed Industries, the team behind the Zed editor, which was multiplayer from the start. Delta takes that idea and moves it up a level: from sharing a cursor in a file to sharing the whole agent session.

- **Collaborative threads** — several people can join one thread to watch, steer, review and comment while the agent works.
- **Conversation anchored to code** — every change stays linked to the conversation and decisions that produced it. As one early user puts it: "Git remembers the commit. This remembers everything between them, including the conversation that wrote the code."
- **DeltaDB** — the version-control layer underneath records work as fine-grained deltas, not snapshots, so comments and references stay attached to specific changes as the code moves.
- **In-context review** — comments stay anchored to lines and follow the code as it evolves.
- **Desktop, web and cloud runners**, all looking at the same synced thread.

## Why it matters

Today almost all agent work is single-player. One person sits with Claude Code or Codex in their own terminal; the conversation, where most of the reasoning now happens, stays on their laptop and disappears. What reaches the team is a diff and a PR description written after the fact. Code review then has to rebuild the intent that was in the thread all along.

Delta treats the thread as a first-class shared artifact, not a private chat log. That changes three things:

1. **Pairing comes back.** You can pair with a colleague *and* an agent at once: one person drives, another watches and steps in when the agent goes off track. This is the Live Share / Google Docs moment for agentic work.
2. **Provenance.** "Why is this code like this?" can be answered by the conversation that produced it, not by archaeology through commit messages.
3. **Version control built for agents.** Git was designed for humans making a few deliberate commits. Agents make many small edits quickly. DeltaDB's bet is that the agent era needs a finer-grained history, where intent sits alongside the change.

## Our take

The direction is right, and it is the missing piece in the [[moc-agent-workbenches]] category: most workbenches help one person run many agents, but Delta helps many people share one agent session. Expect the big labs and IDEs to converge here: shared and hand-off-able sessions are a natural next step for Claude Code, Codex and Cursor.

Open questions:

- **Lock-in.** Delta runs on its own VCS layer. How cleanly does it round-trip to Git and GitHub, where everyone else still lives?
- **Which agents?** Does it work with whatever agent you already use (Claude Code, Codex, ACP agents), or only with Zed's own?
- **Beyond code.** The same need exists for non-code AI work (writing, research, planning), where threads are even more of the output. Delta is code-first; the general "multiplayer AI thread" is still open.
- **Noise.** Full conversation history is valuable but long. Its usefulness will depend on good summarisation and navigation, not just storage.

## Related

- [[moc-agent-workbenches]]
- [[claude-projects]]
