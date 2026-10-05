---
created: 2026-09-18
author: TypeSafe AI
tags: [ai-models, structured-outputs, automation, uncertainty]
newsletter_sent: 2026-10-05
newsletter_url: https://wayintoai.com/weekly/2026-w40
---

# TypeSafe Jev and System One models

A model family for fast decisions inside software, returning typed answers and probabilities.

![TypeSafe introduces System One models and Jev](https://screenshotit.app/https://typesafe.ai/blog/introducing-system-one-models-and-jev)

## Links

- [Launch announcement by Diogo Almeida, September 15, 2026](https://typesafe.ai/blog/introducing-system-one-models-and-jev)
- [Website and early-access signup](https://typesafe.ai/)
- [System One documentation](https://docs.typesafe.ai/concepts/system-one)
- [Workflow evaluations](https://evals.typesafe.ai/)
- [LLM comparison adapter](https://github.com/typesafe-ai/system-one-adapter-python)
- [Known limitations of Jev 1.13](https://docs.typesafe.ai/model-jaggedness/jev-1.13)
- [Our full write-up: Jev makes the case for AI inside ordinary software](../posts/2026-09-18-typesafe-jev-system-one.md)

## What it is

Jev is TypeSafe's first System One model. It accepts text, including structured state expressed as JSON, and produces constrained decisions. It does not generate prose, code, or explanations; current inputs exclude images, audio, and video. The name System One draws on the fast, intuitive thinking described by Daniel Kahneman. [Model overview](https://docs.typesafe.ai/concepts/system-one).

The interface exposes three question types: **Choice** selects among supplied options, **Score** evaluates against defined levels, and **Noul** estimates the probability that a statement is true. Independent questions can share a request; code combines their answers. [Primitives](https://docs.typesafe.ai/primitives).

## Why it matters

The interesting possibility is making semantic judgment cheap and predictable enough to use throughout an application: routing requests, checking relevance, or deciding which cases need review. That could give developers a useful middle ground between brittle hand-written rules and handing an entire workflow to a general-purpose agent.

TypeSafe's launch pricing is $0.042 per million input tokens, with outputs free, and its reported response-time range is 70–500 milliseconds. These are vendor claims for the service at launch, not measurements from our own testing. [Announcement](https://typesafe.ai/blog/introducing-system-one-models-and-jev).

## What to keep in mind

A schema-valid answer can still be wrong. TypeSafe documents weaknesses in numerical tasks, indirect questions, distracting context, and adversarial input for Jev 1.13. Its advice is to retain exact computation and workflow rules in code. [Known limitations](https://docs.typesafe.ai/model-jaggedness/jev-1.13).

The longer post examines the performance evidence, calibration, and implications for application design. This entry and the post reflect documentation checked on September 18, 2026; neither is a hands-on review.
