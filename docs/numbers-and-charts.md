# Paragraphs, numbers and charts

House rules for every page we publish (posts, refs, weekly issues) and for the
email. Voice lives in [brand.md](brand.md); this is about making dense material
readable, especially on a phone.

## Paragraphs

- At most about 60 words or four sentences.
- Break where the thought turns: from what happened to the caveat, or from the
  facts to our take ("We think…").
- A bold lead sentence plus one long block is still a wall. Split it.

## Numbers: table first

Three or more comparable figures (scores, prices, speeds, counts) go in a small
Markdown table, not a sentence. Two figures stay in prose.

```markdown
| Terminal-Bench 4.0 | Score |
|---|---|
| **Claude Opus 5.5** | **66.4%** |
| GPT-6 Astra | 57.9% |
| Claude Opus 5 | 52.3% |

*Vendor figures; GPT-6 Astra as reported by OpenAI.*
```

- One measure per table: first header is the measure, second the unit.
- At most five rows (eight in a ref), best first.
- The subject of the story in **bold** (label and value).
- A one-line italic source caption straight after the table. Say whose
  figures they are.
- Wider tables (several measures) are fine in refs; keep them out of the
  weekly.

In the email, a two-column table whose values are all percentages renders as a
bar chart (0–100% scale, bold row in blue). Other tables render as hairline
rows. The table is always the source of truth.

## Charts: small, where they earn it

Aim for a small chart when a picture shows the point faster than the table:

- **Bars:** 3–8 items on one measure (benchmarks, prices, adoption).
- **Line:** one measure over time, four or more points (scores by release,
  cost per token by month).
- **Before/after:** one pair per item when change is the story.

Skip a chart for two numbers, mixed units, or figures we can't source.

On posts and refs, add the chart as an SVG in `assets/` named
`<topic>-<yyyy-mm>.svg`, embedded with a descriptive alt text, and keep the
table (or the figures in prose) next to it. The weekly email never carries SVG
or images for data: Gmail and Outlook drop SVG, and the newsletter renderer
rejects HTML. Use the Markdown table there; it becomes the bar chart.

### Chart style ("blue pencil")

- About 720 px wide, short (bars: 32–40 px per row). Fits a 44rem column.
- Background `#fbfbf9` or transparent; ink `#1b1b1d`; muted text `#5f5f66`;
  rules `#e2e2de`.
- One accent: the subject in editor's blue `#2140c4`, everything else grey
  `#c4c4bf`. No rainbow palettes, no gradients, no 3D, no rounded bars.
- Labels in `'IBM Plex Mono', ui-monospace, SFMono-Regular, Menlo, monospace`
  (an SVG in `<img>` cannot load web fonts, so the fallbacks matter).
- Label things directly (value at the bar end, name at the line end); no
  legend when direct labels fit. Baseline only, no gridlines unless reading
  values off a line needs them.
- Honest scales: bars start at zero; percentages on 0–100% unless the caption
  says otherwise.
- Title goes in the Markdown (heading or caption), not inside the image.
  Include `<title>` and `<desc>` with the figures for screen readers.
- Dark mode: add a `prefers-color-scheme: dark` block (paper `#0e0e10`, ink
  `#e9e9e6`, accent `#93a6ff`, grey `#4a4a50`).
