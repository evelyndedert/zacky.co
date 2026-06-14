# zacky-website Learnings

## Netlify + GitHub
- Netlify free tier requires a **public** GitHub repo to connect. Private repos need a paid plan.
- Root-level `index.html` is auto-served — no build command or publish directory needed.
- SSH remote (`git@github.com:...`) required for git push from this machine (HTTPS not configured).
- Netlify does NOT auto-deploy on push — Kara must trigger manually from the Netlify dashboard.

## Netlify Forms
- Add `data-netlify="true"` and `name="contact"` to the `<form>` tag.
- Add a hidden `<input type="hidden" name="form-name" value="contact">` inside the form.
- All inputs need `name` attributes or Netlify won't capture them.
- Submit via `fetch('/', { method: 'POST', body: new URLSearchParams(new FormData(form)) })` to keep custom success UI.
- Email notifications configured in Netlify dashboard: Site → Forms → [form name] → Add notification.

## SVG animation timing — left-edge orange bar
- The orange bar (`na` rect) was set to `opacity: 0` inside `completeNode()` — causing a flash.
- Fix: remove the `op(g(id+'a'), 0)` call from `completeNode`. The `reset()` function already clears it at the start of each loop. Bar now persists until the animation restarts.
- Correct sequence: dot arrives → `activateNode` (bar on) → `await wait` (hesitation) → `flowDot` out + `completeNode` simultaneously (bar stays, checkmark appears).

## Images in circular avatars
- Use `object-fit: cover` + `object-position: center X%` on `<img>` inside a fixed `width/height` circle.
- Lower % (e.g. `18%`) pulls the image up — good for portraits where the face is in the upper half.
- `border-radius: 50%` on the container clips to circle; the img fills it.

## Section tags (`.tag` class)
- The `.tag` elements ("Who we are", "How it works", etc.) are purely decorative labels above headings.
- They can be removed site-wide without affecting layout — headings stand alone fine.

## Favicon
- Favicon files live in `images/` — copied from `zacky/command-center/icons/`.
- Chrome may cache the old favicon; hard refresh (Cmd+Shift+R) clears it.
- Add both 32px and 192px variants in `<head>` for browser + PWA coverage.

## Handoff pattern
- For a single-file HTML site: copy to new repo as `index.html`, push, Kara links repo in Netlify dashboard. Done.

## OS Demo pattern
- Demo as a separate `demo.html` opened via `target="_blank"` — keeps it immersive without leaving the site.

## CSS Theming — specificity trap
- `:root` and `[data-theme="zacky"]` have identical specificity (0,1,0). Fix: use `html[data-theme="zacky"]` (specificity 0,1,1).

## CSS layout — banner-aware viewport
- When a fixed bottom banner consumes height, use `calc(100vh - var(--banner-h))` on `body`, `.sidebar`, and `.main`.

## iMessage-style chat layout
- Outer row: `flex-direction: row-reverse`. Message body: `display: flex; flex-direction: column; align-items: flex-end`.
