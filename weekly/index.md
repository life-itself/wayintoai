---
title: Way Into AI Weekly
description: Every issue of the weekly email. What mattered in AI this week, and what to do about it.
syntaxMode: mdx
showToc: false
showEditLink: false
---

<div className="wai wai--embed" id="subscribe">
<p className="wai__label">Get it every Tuesday · free</p>
<form className="wai__form" action="https://mailer.lifeitself.org/newsletter/v1" method="post">
<label className="wai__sr" htmlFor="wai-weekly-email">Email address</label>
<input id="wai-weekly-email" type="email" name="email" placeholder="you@example.com" autoComplete="email" required />
<input type="hidden" name="target" value="way-into-ai" />
<button type="submit">Subscribe</button>
</form>
<p className="wai__small">Once a week. Free. Unsubscribe any time. <a href="https://lifeitself.org/privacy-policy">Privacy policy</a></p>
</div>

<List
  dir="/weekly"
  slots={{
    headline: "subject",
    summary: "description",
    eyebrow: "date"
  }}
/>
