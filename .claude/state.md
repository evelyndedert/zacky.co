# zacky-website State

## Last session: 2026-06-13 (session 6)

### What we did (session 6)
- Rebuilt the "Who we are" bio section into **"Meet the Zacky Team"** — two side-by-side cards (Kara left, Evelyn right)
- Each card: circular avatar photo (140px), name (first name only), role subtitle, indented bio paragraph
- Added Evelyn's photo (`images/evelyn.jpg`) with face-centered crop (`object-position: center 18%`)
- Added Kara's photo (`images/kara.png`) with face-centered crop (`object-position: center 20%`)
- Added Zacky favicon (`images/favicon-32.png`, `images/icon-192.png`) to `<head>`
- Removed all `.tag` section labels ("Who we are", "What we build", "Client outcomes", "How it works")
- Updated "Client outcomes" heading to **"The results speak for themselves."**
- Fixed hero SVG animation: orange left-bar now stays on node after activation (was flashing off)
- Reworked animation sequence: dot arrives → orange bar on → hesitation → dot departs + checkmark simultaneously
- Pushed to `evelyndedert/zacky.co` main (commit 225aa74) — **ready for Kara to deploy**

### What's decided
- Bio section uses first names only (no last names)
- Kara's subtitle: "Systems & Automation Design"
- Evelyn's subtitle: "Design & Implementation"
- Section tags removed site-wide — headings stand alone
- No divider between the app hero and the Meet the Team section (background contrast is sufficient)

### What's next
- **Kara: deploy zacky.co from Netlify** (pushed and ready)
- Kara's bio is live and final

### Blockers
- Deploy is Kara's action — nothing blocking on Evelyn's side

---

## Previous session: 2026-06-11 (session 5)

### What we did (session 5)
- Rebrand: all outward "Zacky OS" / "Zacky Operating System" mentions → **"Zacky Command Center"** in `index.html` and `demo.html`
- Pushed to `evelyndedert/zacky.co` main (commit 7d74d1f)

### Learned (session 5)
- **Netlify does NOT auto-deploy from the repo** — verified live: zacky.co still served old branding after push. Kara must deploy manually from her side.

---

## Previous session: 2026-06-11 (session 4)

### What we did (session 4)
- Full rebuild of `demo.html`: replaced 3-tab basic demo with a high-fidelity 5-tab OS replica
- Pushed to `evelyndedert/zacky.co` main (commit 9221844)

### What's decided
- Public repo so Kara's Netlify free tier can connect to it
- `demo.html` is the live OS demo — generic business data, no industry specificity
- Kara deploys to zacky.co from her side (she owns the Netlify/domain)
