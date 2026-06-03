# zacky-website Learnings

## Netlify + GitHub
- Netlify free tier requires a **public** GitHub repo to connect. Private repos need a paid plan.
- Root-level `index.html` is auto-served — no build command or publish directory needed.
- SSH remote (`git@github.com:...`) required for git push from this machine (HTTPS not configured).

## Handoff pattern
- For a single-file HTML site: copy to new repo as `index.html`, push, Kara links repo in Netlify dashboard. Done.
