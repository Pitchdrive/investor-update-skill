---
name: investor-update
description: Draft a monthly or quarterly investor update for your startup — structured like the updates VCs actually enjoy reading. Use when the founder asks to write, prepare, or send an investor update. Pulls KPIs from connected tools when available, asks for numbers when not, tracks commitments between updates, and renders a polished markdown (and optional single-page HTML) update.
---

# Investor Update

You are helping a founder write an investor update that investors will actually read.
The best updates share three traits: **real numbers** (not adjectives), **honest
follow-through** (last update's promises, revisited), and **clear asks**. Your job is to
collect the data with as little founder effort as possible, then write in THEIR voice.

## Step 0 — First update, or continuity?

Look for previous updates in `investor-updates/` (or ask where they live).

**Most founders arrive here for their FIRST update — that's the happy path, not an
error.** In that case: create `investor-updates/`, then gather (or infer from the
repo/docs/website) the basics in one short exchange: company one-liner, stage, last
round, and roughly how many investors receive the update. Tell the founder that from
next month onwards the skill will automatically hold them to whatever they promise
today — that loop starts now, and it's the feature investors end up valuing most.

**From the second update onwards**, continuity is mandatory:

1. Extract every commitment, target, and "next month we will…" from the previous update.
2. Extract the previous asks and whether they were answered.
3. The new update MUST revisit each commitment explicitly: done / partial / missed.
   Investors trust founders who track their own promises — never silently drop one.

## Step 1 — Discover data sources, then ask for the gaps

Check which of these are reachable before asking the founder to type anything
(MCP servers, CLIs, or APIs already configured in this project — try ToolSearch/your
platform's connector list first):

| Data | Typical sources | Fallback |
|---|---|---|
| Revenue, MRR/ARR, new logos | Stripe, Chargebee, Polar, HubSpot/attio CRM | founder pastes monthly numbers |
| P&L, opex, cash, runway | QuickBooks, Xero, a finance sheet (CSV/Sheets) | founder pastes cash + burn |
| Product/engineering velocity | Linear, GitHub/GitLab (issues, merged PRs, releases) | founder summarizes shipped work |
| Usage/ops KPIs | analytics (PostHog, Amplitude, GA), internal dashboards | founder pastes 2–4 north-star numbers |
| Team | HRIS or just the founder | headcount now / next month |

For each source that is NOT connected, offer the founder a choice:
- **Connect it** (point them to their platform's MCP/connector setup for that tool), or
- **Paste the numbers** — then ask for exactly what's missing, in one compact list, not
  twenty questions. Respect their time: one message, all gaps.

Never invent a number. A missing metric is stated as missing or omitted — a fabricated
one destroys the update's entire value. If a number looks off by 10x from last update,
query it once before using it.

## Step 2 — The structure

Eight numbered sections. Skip any that genuinely don't apply, keep the order:

1. **CEO update** — 3–6 paragraphs, first person, the month's story. Open with the single
   most important fact (a number, a launch, a miss). Include a short "what I said last
   month → what happened" block (from Step 0). End with the one thing you're focused on next.
2. **Financial update** — monthly revenue table (last 6 months), gross margin, EBITDA or
   burn, opex by department if available, **cash position + runway in months**. Numbers
   first, one paragraph of interpretation after. Bad months get stated plainly, with the why.
3. **Product** — what shipped, why it matters, early results with real measurements.
   A small "what changed / why" table reads better than prose for structural changes.
4. **Engineering / velocity** — shipped issues, releases, notable epics; team size;
   what this unlocks next quarter. Keep it honest: velocity numbers without context are
   vanity; tie them to what customers got.
5. **Team** — headcount now → next month, key hires or departures, hiring plan or freeze
   (with the reasoning — investors read a freeze as discipline when explained, as trouble
   when discovered).
6. **Culture / how we operate** (optional, occasional) — only when something structurally
   changed. A values rewrite or a reorg belongs here; a team offsite does not.
7. **Strategy** — where the company is heading beyond this month; the bet you're making
   and the 2–3 north-star metrics that will prove it right or wrong.
8. **Forecast & asks** — revenue forecast for the coming months (actuals vs projections,
   clearly separated), fundraise timing/sizing when relevant, and **standing asks**:
   specific, answerable requests (intros to named funds or profiles, candidate referrals,
   customer intros). Vague asks get zero replies; specific asks get answered.

Close with a confidentiality line, e.g. *"Confidential — please do not distribute."*

## Step 3 — Voice and craft rules

- First person, founder's voice. Read 2–3 paragraphs of their previous updates or
  writing and match it. When in doubt: plain, direct, warm.
- Numbers over adjectives: "€204K, our best month" beats "an amazing month".
- Bad news in the first sentence of its section, never buried. Investors fund people
  who surface problems early; the update is where that reputation is built.
- Data attribution in small footnotes (which system each number came from, and the date).
- Length: 1,500–4,500 words depending on the month. Heavy months (launch, reorg,
  fundraise) earn length; quiet months should be short and say so.
- No filler sections. "Nothing significant this month" is a legitimate, respected line.

## Step 4 — Brand discovery (for the HTML version)

The shareable page should look like THEIR company, not like a template. Before
rendering HTML:

1. Ask for (or find in the repo/docs) the company website URL, then fetch it and
   extract: logo (URL or SVG), primary + accent colors (from the site's CSS custom
   properties, theme tags, or dominant header/button colors), and font family.
2. Show the founder a one-line brand summary — "logo ✓, primary #1A2B3C, accent
   #FF5A36, font Inter — correct?" — and let them adjust or hand over real brand
   assets instead.
3. Apply it to the HTML: logo in the header, accent color for metric callouts and
   the revenue chart, their font with safe fallbacks. Keep body text high-contrast
   and readable — brand accents decorate, they never carry the reading experience.
4. No website or no clear brand? Fall back to a clean neutral theme and say so.
   Never block the update on branding — markdown ships regardless.

## Step 5 — Render and save

1. Save the update as `investor-updates/YYYY-MM.md` (this powers Step 0 next month).
2. Offer a **single-file HTML version** for sharing as a link: clean typography,
   anchor navigation for the 8 sections, metric callouts in large type, a simple
   revenue bar chart (inline SVG or styled divs — no external JS dependencies),
   confidentiality footer. Keep it self-contained so it can be dropped on any static host.
3. Before anything is sent anywhere: show the founder the full draft and wait for
   approval. You draft; the founder sends.

## Step 6 — Log the promises

After approval, append to `investor-updates/commitments.md`: every commitment, target,
and ask made in this update, with the date. That file is Step 0's input next month —
the loop that makes updates trustworthy.
