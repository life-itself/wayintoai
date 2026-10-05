# Way Into AI email design

How Way Into AI Weekly looks in the inbox. It adapts the site's "blue pencil"
identity ([DESIGN.md](../DESIGN.md), [brand.md](brand.md)) to email. Writing
rules for paragraphs, tables and charts are in
[numbers-and-charts.md](numbers-and-charts.md).

The template is code, not per-issue HTML: the CRM renders every issue from its
Markdown through `services/mailer/scripts/lib/way-into-ai-email.mjs` (selected
by the `way-into-ai` publication profile). Change the look there, update its
regression in `test-node/newsletter-package.test.mjs`, and record the rule
here. Never hand-edit an issue's HTML.

## Anatomy

1. **Masthead:** blue `A→]` mark (HTML, not an image, so it shows with images
   off) and "Way Into AI" in mono; "Read on the web →" on the right (hidden
   below 600px). Hairline beneath.
2. **Eyebrow:** `WAY INTO AI WEEKLY · WEEK <n>, <yyyy>`, mono, uppercase,
   muted. The week comes from the issue key `weekly-<yyyy>-w<ww>`.
3. **Headline:** the email subject, serif, 40px (32px on mobile).
4. **Lede:** the first paragraph, 21px, softer ink.
5. **Sections:** `##` headings in mono with a blue `##` marker and a hairline
   above.
6. **Items:** serif body 19px/1.6 (18px on mobile). Bold lead sentence. A short
   link that ends a paragraph after a full stop ("Read more", "Our write-up")
   becomes a mono blue call to action with `→` (also after a closing quote
   or bracket).
7. **Tables:** a two-column table whose values are all percentages becomes a
   bar chart on a 0–100% scale; the bold row gets the blue bar, others grey.
   Other tables render as mono hairline rows. An italic-only paragraph right
   after a table becomes a small mono source caption.
8. **Images:** full column width with a hairline border, one or two per
   issue, placed above the item they illustrate (rules in the weekly-roundup
   skill).
9. **Lists:** blue mono `→` bullets with a hanging indent.
10. **Footer:** dark rule, name and promise, then "Read on the web ·
   wayintoai.com · Unsubscribe" (Resend unsubscribe placeholder).

## Tokens

Paper `#fbfbf9`, ink `#1b1b1d`, muted `#5f5f66`, rule `#e2e2de`, blue
`#2140c4`, inactive bar `#c4c4bf`, code background `#f2f2ee`. Single 600px
column, fluid below that.

Fonts: Newsreader and IBM Plex Mono via a Google Fonts `<link>` (Apple Mail,
iOS Mail). Elsewhere the fallbacks render: Charter / Iowan Old Style / Georgia
for prose, ui-monospace / SF Mono / Menlo / Consolas for mono. Never Courier.

## Email constraints

- Inline styles on every element; the `<style>` block only carries the
  mobile media query and Apple data-detector reset.
- Presentation tables for layout and bars; no flexbox, grid, SVG, background
  images or web components.
- Light only (`color-scheme: light only`); the template does not attempt dark
  mode.
- Data never goes in images or SVG; write a Markdown table.

## Checking a change

Prepare the issue (see [newsletter-sending.md](newsletter-sending.md)), then
screenshot the private `preview.html` at desktop and at 375px. Headless Chrome
has a minimum window width, so for mobile load the preview inside a 375px
iframe. Look at the masthead, the headline wrap, any bar chart, list
alignment and the footer links. A real inbox test (Gmail web, iOS Mail) is the
final check and needs a separately approved test send.
