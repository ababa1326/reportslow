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
`reportslow.com` was available as of 2026-06-10 — register it before launch.
All canonical/OG URLs are already hard-coded to `https://reportslow.com/`. If you pick a
different domain, search-and-replace that string in `index.html`, `robots.txt`, `sitemap.xml`.

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
