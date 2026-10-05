---
created: 2026-09-28
author: Movez (@0xMovez)
tags: [ai-prompts, video, motion-graphics, opus-5-5, opus-5-5-demo-videos, claude, education, twitter-article]
---

# Movez's Opus 5.5 Motion Design Prompt

A reusable prompt template for getting Claude Opus 5.5 to plan and build a complete 75–90 second educational animation, from Movez's article "How to build motion design studio with Opus 5.5 (Full-course)".

## Links

- Article: https://x.com/0xMovez/status/2104216919033192746 (posted 2026-09-27)
- Author: [@0xMovez](https://x.com/0xMovez)

## Overview

The prompt fills in `[TOPIC]`, `[CORE IDEA]` and `[AUDIENCE]`, then fixes everything else: a visual identity (torn paper, gouache and crayon textures, a five-colour palette, a subtle stop-motion "boil", one coral pixel mascot as narrator, staged inside a dark terminal window), a seven-scene structure (hook, familiar world, disruption, mechanism, discovery, consequence, recap), and a per-scene spec covering learning purpose, visual, motion, voiceover, sound and transition.

Notable rules: no hard cuts (each transition is an object that becomes the next scene), one visual idea per shot, narration not duplicated on screen, and "do not stop at a mood board, style frame, or partial prototype" — build the full 1920×1080, 24 fps animation with captions.

## The Prompt

```markdown
## Purpose

Create a complete 75–90 second educational animation about `[TOPIC]`.

Teach `[CORE IDEA]` through one clear visual story, not a list of facts.

Make the difficult idea intuitive for `[AUDIENCE]` without losing accuracy.

## Visual Identity

Build the world from torn paper, dry gouache, crayon, and pencil texture.

Use coral, mustard, teal, cream, and charcoal with soft cardboard shadows.

Add a subtle stop-motion boil: shapes shift by 1–2 pixels every few frames.

Use one coral pixel mascot as the narrator and curious guide.

Keep its square silhouette, black eyes, scale, and proportions consistent.

Frame the lesson as a miniature stage inside a dark terminal window.

## Process

Reduce the subject to one central cause-and-effect relationship.

Create seven scenes: hook, familiar world, disruption, mechanism, discovery, consequence, and recap. Every scene must add new understanding.

For every scene provide:

### SCENE [N] — [START–END]

- **Learning purpose:** the exact idea being taught.
- **Visual:** composition, characters, objects, labels, and camera behavior.
- **Motion:** entrance, primary action, secondary reaction, and exit.
- **Voiceover:** the final spoken line, written for 125–145 words per minute.
- **Sound:** music cue, ambience, and synchronized tactile effects.
- **Transition:** the visible object that physically becomes the next scene.

Use no hard cuts. Let lines become paths, rays become diagrams, and particles regroup into objects. Every transition must carry meaning.

Keep one primary visual idea per shot and let key transformations breathe.

Write warm, precise narration. Use concrete language before technical terms.

Do not duplicate narration in on-screen text. Keep labels brief and readable.

## Delivery

Return the concept, visual system, character sheet, timestamped storyboard, final voiceover, transition map, sound plan, and technical implementation.

Then build the complete animation at 1920×1080, 24 fps, with captions.

Do not stop at a mood board, style frame, or partial prototype.

## Voice

Act as a senior motion director, educational storyteller, and animator.

Be playful in presentation, rigorous about clarity, and decisive in execution.

Preserve scientific accuracy, visual continuity, and the supplied identity.
```

## Related

- [[rexan-wong-motion-graphics-prompt]]
- [[moc-opus-5-5-demo-videos]]
- [[moc-useful-prompts]]
