---
name: weekly-roundup
description: Draft the Way Into AI weekly email ("Way Into AI Weekly") as canonical issue markdown in weekly/, from the week's newsletter-flagged items, logs, posts and refs, then stop for human approval. Use when asked to draft, prepare or dry-run the weekly issue/roundup/newsletter. Never sends email.
---

# Way Into AI weekly roundup

Produces one issue file, `weekly/YYYY-wWW.md`, for human review. It does **not** send, schedule, or touch the CRM; sending is a separate step (bead wayintoai-94n.2, run from `~/src/life-itself/crm`) that starts only from an approved file.

Read before drafting: `docs/brand.md` (voice, promise, issue structure) and "Featuring and newsletter selection" in the repo `SKILL.md` (the flags this skill reads).

## Conventions

| What | Rule |
| --- | --- |
| Send day | Tuesday. Draft ready for review on Monday. |
| Week number | ISO 8601 week of the **send date**: `date -j -f %F 2026-09-29 +%G-W%V` → `2026-W40`. |
| File | `weekly/<ISO year>-w<week>.md`, e.g. `weekly/2026-w40.md`. Site URL `https://wayintoai.com/weekly/2026-w40`. |
| Subject | The hook only: the lead item as a short, true claim, e.g. `Opus 5.5: top-tier AI for 40% less`. ≤ 50 characters, no emoji or glyphs, no brand, no issue number. This follows common newsletter practice: the sender name (`Way Into AI`) carries the brand, the subject earns the open. Don't reuse a hook shape from recent issues (`rg -n '^subject:' weekly`). |
| Preheader | Starts `Week <N>.` then names the other items (`Also: …`). Not a copy of the subject or description. |
| Site title | `What mattered · week <N>`. |
| Issue number | `issue:` = number of `status: sent` issues in `weekly/` + 1. |
| Window | Day after the last **sent** issue's `window_end` through the day before drafting. Scheduled Monday run: previous Tuesday → Sunday. First issue: last 7 days, extended back to the oldest unsent flagged item if it is under 4 weeks old. |
| Status | `status: draft` with `publish: false` → `approved` (human; delete `publish: false` in the same edit) → `sent` (after the send only). |
| Visibility | Drafts carry `publish: false` so Flowershow does not publish them. Approved and sent issues are public at `/weekly/<yyyy>-w<ww>` and listed on `/weekly`. |

### One markdown file, two outputs

The same file is the site page and the email body, so the body must be plain CommonMark that renders the same in both:

- **Frontmatter is metadata only.** The site uses `title`/`description`/`date`; the send step strips frontmatter and uses `subject`, `preheader` and the canonical URL.
- **No H1.** Flowershow renders `title`; the email template renders the subject.
- **Absolute links only**: `https://wayintoai.com/ref/<slug>`, `https://wayintoai.com/posts/<slug>` (no `.md`), or the external URL. No `[[wiki links]]`, no relative paths, no MDX/HTML.
- **Images and graphs:** one or two per issue in total, where a picture says more than a sentence. A graph counts as one and is often the better choice when an item has numbers: a percentage table becomes a bar chart in the email by itself (see Paragraphs and numbers below); any other chart goes in as a PNG. Otherwise use a video's thumbnail, or a one-glance diagram for One thing to try. Save each in `assets/` (JPG/PNG, at most about 1200px wide; `sips -Z 960 in.jpg --out assets/<slug>.jpg`) and also embed it on the item's canonical ref. In the issue use the absolute `https://wayintoai.com/assets/<file>` URL with descriptive alt text, on its own line directly above the item's bold headline. No SVG (Gmail drops it). Images must be pushed before the send. Email clients may block images, so the text must stand without them.
  - YouTube thumbnail: `curl -sfL -o /tmp/t.jpg https://img.youtube.com/vi/<id>/maxresdefault.jpg` (fall back to `hqdefault.jpg`).
  - An image the reviewer pastes into the chat is not saved to disk. Read it from the clipboard: `osascript -e 'set d to the clipboard as «class PNGf»' -e 'set f to open for access POSIX file "/tmp/clip.png" with write permission' -e 'write d to f' -e 'close access f'`. Then look at it before using it.
- **No unsubscribe or footer text.** The send step's template adds the canonical link and unsubscribe.
- Link every item back to the site page first (the site is the notebook; the email is the edit), external source second if useful.

### Approval and the content hash

The CRM currently binds send approval to a hash of the **whole source file, frontmatter included** (wayintoai-94n.6 tracks narrowing it to body, subject and preheader). So make every pre-send edit first: set `status: approved`, delete `publish: false`, push so the canonical page is live, and only then prepare and draft. Do not touch the file again until the send is confirmed; then set `status: sent` and `sent:`.

### Frontmatter

```yaml
---
title: "What mattered · week 40"
description: <one sentence for site listings and social cards>
date: 2026-09-29            # send date
week: 2026-W40
issue: 1
subject: "Opus 5.5: top-tier AI for 40% less"
preheader: "Week 40. Also: …"
status: draft
publish: false              # keeps the draft off the site; delete on approval
window_start: 2026-09-22
window_end: 2026-09-27
items:                      # every repo file the body links or draws facts from; 94n.2 marks these newsletter_sent
  - ref/claude-opus-5-5.md
try: ref/some-tool.md       # the "One thing to try" item (also listed in items)
---
```

## Procedure

1. **Work out the issue.** Send date = next Tuesday (today if Tuesday). Compute week, file path, issue number and window as above. If the file already exists and is not `status: draft`, stop and ask.

2. **Gather candidates** (read-only):

   ```bash
   python3 .agents/skills/weekly-roundup/gather.py [--today YYYY-MM-DD] [--since YYYY-MM-DD] [--until YYYY-MM-DD]
   ```

   Pass `--today` on scheduled runs (the machine may be in UTC). It lists: flagged items (`newsletter: weekly|standalone`) not yet sent, whatever their date, with `STALE` on those over 4 weeks old; log `newsletter_candidates` in the window; new posts/refs in the window; the window's log headings; past try picks; undated refs. "Sent" means `newsletter_sent` on the item **or** listed in a sent issue's `items:`/`try:`. Then **read every candidate file**; never draft from titles.

3. **Select.** Rank: our own posts (they carry our opinion) > flagged `weekly` > refs with the biggest consequences for someone using AI at work > other refs. Keep one canonical item per story (a post beats its ref), and **one story gets at most one What mattered slot**: fold follow-on angles into that item or into The bigger picture.
   - `newsletter: standalone` → include it in the weekly. A dedicated send is a separate decision the reviewer makes; don't ask about it in the draft.
   - `STALE` flagged items → ask, don't include by default.
   - **What mattered:** 3 developments (4 at most). Fewer, shorter items beat a full list. Thin week (fewer than 3 worth it): run 2 and say so in the opener, or add one archive item clearly labelled as such. Never pad.
   - **One thing to try:** one practical thing for people **using** AI: a tool, skill, workflow, prompt, or a useful guide or reference. Not policy or news. The homepage promises one every issue. Prefer this week's items; if none fits, draw from the archive: `/use` posts, refs with a "User Experience Note", `ref/moc-best-ai-skills.md`, guides and references. Don't repeat a past pick. Prefer something a generalist can start in ten minutes. Don't claim we use it unless the repo says so.
   - **The bigger picture:** one item or theme on work, power, policy or safety, in one or two sentences (about 50 words).
   - **From the log:** up to 3 other worthwhile items, one line each. Leave out bookmarks we haven't tried and anything that is only "interesting". No firehose.

4. **Draft** in house voice (`docs/brand.md`): first person plural, specific. This is a **roundup, not new editorial**: report what the sources say, and use only takes already recorded in our posts and refs. Don't add new inferences, predictions or opinions; when in doubt, cut the sentence. Say "we think", "we don't know yet". Concrete numbers and examples over adjectives; no hype, doom, jargon, or digest-speak ("In this week's roundup…", "exciting", "game-changer").
   - **Headlines** state the point as a plain claim. Never the "X, not Y" / "not X but Y" shape, and never the product name alone.
   - **Items:** what happened and why it matters, with our take only where a post or ref already states it. Vary the shape; five identical four-sentence paragraphs read like a digest. Keep claims no broader than the evidence (sample sizes, "vendor figures").
   - **Paragraphs and numbers** follow [docs/numbers-and-charts.md](../../../docs/numbers-and-charts.md): paragraphs of at most about 60 words, broken where the item turns; three or more comparable figures go in a small two-column Markdown table with the subject in **bold** and an italic source caption. A percentage table renders in the email as a bar chart. No images, SVG or HTML for data in the weekly.
   - **One thing to try** ends with the exact first step (a command, a menu, a prompt) and how long it takes.
   - **Opener:** one or two sentences naming the week's thread. Issue 1 (or after a gap) also says what this email is, in one sentence.
   - **Sign-off:** invite replies ("Just reply to this email") and point to the log.
   - Every number, quote, date and take must come from a file in `items:`. Relative dates are from the **send date** ("on 1 September", not "three weeks ago").
   - **Bite-sized: a two-minute read, 300–450 words.** The email is the edit; the site holds the detail. Each What mattered item is one paragraph: the bold headline plus one or two sentences (about 50 words), then one link. If an item needs a second paragraph, cut it or move the detail to the ref. One thing to try is about 60 words, first step included. Drop a story before squeezing four into a long item.

   Body skeleton:

   ```markdown
   <1–2 sentence opener>

   ## What mattered

   **<Headline that makes the point.>** <One or two sentences: what happened, why it matters.> [Read more](https://wayintoai.com/...)

   ![<alt text>](https://wayintoai.com/assets/<image>.jpg)

   **<Item with an image: picture first, then the headline.>** <…> [Watch it](https://wayintoai.com/...)

   ## One thing to try

   **<Name, for <use>.>** <What it is, how we use it.>

   <First step, exactly.> [Read more](...)

   ## The bigger picture

   <One or two sentences.>

   ## From the log

   - [<Title>](https://wayintoai.com/ref/...): <one line>

   <Reply invite.> The rest of what we log is at [wayintoai.com/logs](https://wayintoai.com/logs).
   ```

5. **Check** before handing over:
   - `rg -n '\[\[|\]\(\.\.?/|\.md\)' weekly/<file>` returns nothing (no wiki or relative links).
   - Every `https://wayintoai.com/...` link maps to an existing `ref/` or `posts/` file, and every such file is in `items:`.
   - Every number, quote and "we think" traces to a file in `items:`.
   - No paragraph over about 60 words: `awk -v RS= 'NF>60 && !/^(---|\||- )/{print NR": "NF" words"}' weekly/<file>` prints nothing (or each hit is justified). Runs of three or more comparable figures are a table.
   - Body is 300–450 words: `awk '/^---$/{c++;next} c>=2' weekly/<file> | wc -w`. Each What mattered item is a single paragraph.
   - Every image URL is under `https://wayintoai.com/assets/`, the file exists in `assets/`, and it has alt text.
   - Subject ≤ 55 chars and says nothing the body contradicts.
   - Tell pass: run Humanizer (`/humanizer` on the body) if installed, or check by hand for "X, not Y", rules of three, inflated importance, em-dash runs, filler.
   - Optional: have a sub-agent critique content (accuracy against sources, selection, voice) and fold in what holds up.

6. **Stop for approval.** Do not commit, push, send, or change flags on source items. Report: file path, subject, word count, the selection with one-line reasons, what was left out and why, and review notes (`CONFIRM` items, takes that need the reviewer's view). The reviewer edits the file, sets `status: approved` and deletes `publish: false`; that is the only editorial approval signal. It does not authorize a send: the send gate in `docs/newsletter-sending.md` still needs explicit approval of the rendered message and exact audience.

## Surfacing the Monday draft

Interactive run: the file in the working tree plus the report above. Scheduled run (Monday morning, not yet set up; bead wayintoai-94n.3): commit the draft to branch `weekly/<yyyy>-w<ww>`, open a PR titled `Weekly draft: What mattered · week <N>`, and create a bead `Review weekly issue week <N>` labelled `who:rufus` linking the PR. Merging the approved PR on Monday publishes the site page, so the canonical URL exists before Tuesday's send.
