# zacky-website State

## Last session: 2026-06-11 (session 4)

### What we did (session 4)
- Full rebuild of `demo.html`: replaced 3-tab basic demo with a high-fidelity 5-tab OS replica
- 5 views: Overview (KPIs + What's Next + In-Flight projects), Chat (iMessage-style, 4 conversations), Projects (3 cards + clickable detail drawers), Invoices, Team
- Mock company: "Business" (generic, no industry) — sidebar shows "B" brand mark
- Dual theme toggle in sidebar: Zacky (parchment/terracotta, default) + Blue (indigo, secondary)
- CSS specificity fix: `html[data-theme="zacky"]` beats `:root` — prevents blue theme from bleeding through
- Phase progress bars in solid blue (5 blocks, done/active/empty states)
- Chat self-messages right-aligned (iMessage style, flex row-reverse + column-reverse on body)
- All "Workflow" language replaced with "Automations" / "Projects Managed" etc.
- Bold gradient banner at bottom with strong box-shadow to stand out
- Pushed to `evelyndedert/zacky.co` main (commit 9221844)

### What's decided
- Public repo so Kara's Netlify free tier can connect to it
- `demo.html` is the live OS demo — generic business data, no industry specificity
- Zacky theme is the default; Blue is secondary toggle in sidebar
- All "Workflow" references removed from demo — replaced with "Automations" language
- Kara deploys to zacky.co from her side (she owns the Netlify/domain)

### What's next
- Kara: pull evelyndedert/zacky.co and deploy to zacky.co
- Kara: set up Netlify email notification for contact form if not done yet
- Future: Bank and Lawn Care demo variants (deferred — generic "Business" covers initial launch)
- Future: company switcher if multiple demo variants built

### Blockers
- Deploy is Kara's action — nothing blocking on Evelyn's side
