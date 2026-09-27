---
created: 2026-09-27
author: Rexan Wong (@rexan_wong)
tags: [ai-prompts, video, motion-graphics, claude, opus, workflow, twitter-thread]
---

# Rexan Wong's Motion Graphics Prompt Workflow (Claude Opus 5.5)

> Everyone's sharing motion graphic videos Opus 5.5 made, and it's genuinely insane. Everyone says they made it with "one prompt" — but a bare one-prompt attempt looks mid. Here's the workflow that actually gets pro-level results.
> — [@rexan_wong](https://x.com/rexan_wong)

![Rexan Wong thread on Opus 5.5 motion graphics workflow](https://screenshotit.app/https://x.com/rexan_wong/status/2103707054108299437)

## Links

- Tweet: https://x.com/rexan_wong/status/2103707054108299437
- Author: [@rexan_wong](https://x.com/rexan_wong)

## The Workflow

1. **Reference a style, don't describe one.** Pull 1–2 reference videos from [whatships.com](http://whatships.com) and tell Opus to match them by name. Naming a style beats describing it — without a reference, Opus falls back to its default look (centered text, gradient background, everything fading in), which is why so many AI motion graphics videos look the same.

2. **Give Opus a renderer, not just a canvas.** Install [HyperFrames](https://x.com/HyperFrames_) or [Remotion](https://x.com/Remotion) so Opus writes each scene as code and renders straight to mp4 — no video editor, no screen-recording an HTML page. Every frame is exact, and a requested change edits one line and re-renders instead of starting over.

3. **Use real UI components, not invented ones.** Install [21st.dev](https://x.com/21st_dev) for real buttons, cards, and components built by design engineers. Without it, Opus draws your product's UI from scratch — wrong spacing, placeholder boxes, fake-looking buttons — and the whole video reads as cheap.

4. **Dump full context, then ask for 3 storyboards.** Brand assets (logo, colors, fonts), real product screenshots, the chosen reference video, and a braindump of the vision — then ask for three storyboard variants. Without this, Opus guesses your colors, your fonts, and what your product even does. Three variants means picking a direction instead of patching the first idea it had.

5. **Approve a still frame per scene before anything animates.** Fixing a storyboard is far cheaper than fixing a render. Catching a wrong scene 4 only after the whole thing is animated means a full re-render; a still frame takes seconds to change.

6. **Direct with camera language, not vague notes.** "Slow every zoom to 0.7x," "hard cut here," "push in on the button" — specific, director-style notes get the last 20% that makes a render look pro. "Make it better" gets random changes.

## Why Interesting

Everyone has access to the same model — the context and tooling wrapped around it (a reference video, a code-based renderer, real components, a staged storyboard review) is what actually separates "one-prompt mid" from pro-level output. A reusable pattern for agent-driven creative work generally, not just video.

## Related

- [[moc-useful-prompts]]
