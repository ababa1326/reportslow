# Project: Credit Utilization Tracker — Web App

## What this is
A free web tool that tells users how much to pay **before their statement closing date** — not their due date — so their credit card reports a low balance to the credit bureaus. The timing insight is the entire product: the statement closing date is when the balance gets photographed and reported, not the due date. **Do not lose this concept.**

## Starting point
There is a working MVP in this folder: `credit-utilization-tracker.html`

- Single self-contained HTML file, vanilla JavaScript, **zero dependencies**.
- Renders and calculates correctly; verified in a real browser.
- **Read this file first.** The core logic, the math, and the explanatory copy are correct and should be preserved.

## Free tier (already built — keep as-is)
- Single card, instant calculation
- Inputs: credit limit, current balance, statement closing date
- Target utilization toggle: 30% / 10% / <10%
- Output: exact dollar amount to pay down before closing + resulting reported balance
- Utilization bar with target marker
- Timeline graphic (cycle start → closing date → due date)
- Explanatory SEO content below the tool (what utilization is, statement vs. due date, what to aim for, does paying early help)

**Do not gate the core single-card tool. It stays free and standalone — it's the SEO engine and the funnel.**

## What to build next
1. Restructure into a proper project. React or keep vanilla — your call — but the free tier must remain deployable as a **static site**.
2. Add a premium tier:
   - Multi-card tracking with **total/aggregate utilization** across all cards (this is the headline premium feature)
   - Saved cards (requires auth + a database)
   - Statement-date reminders (email or calendar invite)
   - Stripe for payments
3. Premium **wraps around** the free tier — nothing from the free version gets thrown away.

## Constraints
- Free tier must stay client-side and free to host (Netlify / Vercel / GitHub Pages).
- This is an **educational tool, not financial advice** — keep the disclaimer in the footer.
- **Do not** connect to users' real bank or credit accounts. All data is manual entry, nothing leaves the browser on the free tier.

## Build order (important)
1. Get the existing free tier deployed and live first.
2. Confirm it works hosted and is findable.
3. **Only then** add the premium / auth / Stripe / database layer.

The premium infrastructure (Stripe + auth + database + email) is the first thing that turns this from a zero-maintenance tool into an ongoing burden. Delay it until there's evidence the free tool has real traffic. Don't build the paid layer for a tool nobody has found yet.

## SEO notes
- Target search terms already baked into the copy: "statement date," "when does my balance report," "credit utilization."
- The tool draws people in; the explanatory prose below it is what Google indexes and ranks. Keep both.
- Page title and meta description matter — keep them aligned with what people actually search.

## Naming
"UtilizationCheck" in the current file is a **placeholder**. Pick a real name and check domain availability before launch.
