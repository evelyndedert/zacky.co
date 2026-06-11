# zacky-website Learnings

## Netlify + GitHub
- Netlify free tier requires a **public** GitHub repo to connect. Private repos need a paid plan.
- Root-level `index.html` is auto-served — no build command or publish directory needed.
- SSH remote (`git@github.com:...`) required for git push from this machine (HTTPS not configured).

## Netlify Forms
- Add `data-netlify="true"` and `name="contact"` to the `<form>` tag.
- Add a hidden `<input type="hidden" name="form-name" value="contact">` inside the form.
- All inputs need `name` attributes or Netlify won't capture them.
- Submit via `fetch('/', { method: 'POST', body: new URLSearchParams(new FormData(form)) })` to keep custom success UI.
- Email notifications configured in Netlify dashboard: Site → Forms → [form name] → Add notification.

## Handoff pattern
- For a single-file HTML site: copy to new repo as `index.html`, push, Kara links repo in Netlify dashboard. Done.

## OS Demo pattern
- Demo as a separate `demo.html` opened via `target="_blank"` — keeps it immersive without leaving the site.
- Use fictional company names/data (not client or Zacky data) so it reads obviously as a demo.
- #f0f0f0 background reads as neutral/app-like vs the beige which felt branded.

## CSS Theming — specificity trap
- `:root` and `[data-theme="zacky"]` have identical specificity (0,1,0). If `:root` is declared later, it wins and the theme never applies.
- Fix: use `html[data-theme="zacky"]` (specificity 0,1,1) — always beats `:root`. Apply this pattern for any attribute-based theme that must override root defaults.

## CSS layout — banner-aware viewport
- When a fixed bottom banner consumes height, use `calc(100vh - var(--banner-h))` on `body`, `.sidebar`, and `.main` — NOT `height: 100%` on body (that gives full viewport and content hides under the banner).
- `overflow: hidden` on both `html` and `body` prevents scroll bleed when using fixed positioning.

## iMessage-style chat layout
- Outer row: `flex-direction: row-reverse` moves avatar to the right.
- Message body inside: `display: flex; flex-direction: column; align-items: flex-end` right-aligns the bubble within its column.
- Meta row (timestamp/name): also `flex-direction: row-reverse` to right-align.
- Bubble `border-radius`: `var(--r) 0 var(--r) var(--r)` gives the "tail on the right" shape.

## Hardcoded colors break themes
- Any hardcoded hex in `style=""` attributes or non-token CSS rules won't update when CSS variables change.
- Audit: grep for `#6366F1`, `#2563EB`, etc. across the file whenever adding a new theme — replace with `var(--zacky)` or the appropriate token.
