# Deploying ReportsLow (free tier)

The free tier is a **static site** — no build step, no server, no dependencies.

## Files that ship (the whole site)
- `index.html` — the app + SEO prose (self-contained)
- `favicon.svg`
- `og.png` — social share image (1200×630)
- `og.svg` — source for the share image (optional to deploy)
- `robots.txt`
- `sitemap.xml`

## Files that do NOT ship (dev-only, gitignored)
- `server.js` — local preview server
- `SPEC-*.md`, `HANDOFF.md`, `DEPLOY.md`, `.claude/`

## Domain
Deployed free at https://ababa1326.github.io/reportslow/ via GitHub Pages. The custom domain
(`reportslow.com`) is deliberately deferred until the tool shows traction. If registered later,
swap the URLs back in one pass and 301 from the github.io URL.

## Host options (pick one — all free)
**Netlify / Vercel (drag-and-drop):** drop this folder into the dashboard; it serves `index.html`
at the root. Add the custom domain in the host's settings and point the registrar's DNS at it.

**GitHub Pages:** push to a repo, enable Pages on the default branch root. Add the custom domain
in Settings → Pages (it writes a CNAME).

## After it's live (per the handoff build order)
1. Confirm the page loads and the calculator works on the live URL.
2. Submit `https://reportslow.com/sitemap.xml` in Google Search Console so it gets indexed.
3. Add lightweight analytics (e.g. Plausible/Cloudflare) to see if traffic shows up.
4. **Only once there's real traffic** build the premium layer (multi-card aggregate utilization,
   auth + DB, Stripe, reminders). Don't build the paid infra for a tool nobody has found yet.
