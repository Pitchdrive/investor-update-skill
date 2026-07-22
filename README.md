<img src=".github/social-preview.png" alt="Investor Update Skill — write updates your investors actually read" width="100%">

# 📬 Investor Update Skill

Write investor updates your investors actually read — with Claude Code (or any agent
that supports skills).

Some of the best founder updates we receive at [Pitchdrive](https://pitchdrive.com)
share the same DNA: real numbers, honest follow-through on last month's promises, and
specific asks. This skill packages that DNA so any founder can produce the same quality
in an afternoon — ideally with the numbers pulled straight from your tools.

## What it does

- **Pulls your KPIs** from connected tools when available — billing (Stripe, Paddle,
  Mollie…), CRM (HubSpot, Salesforce, Attio…), accounting (QuickBooks, Xero, Exact,
  Yuki, Silverfin…), banking (Mercury, Qonto…), plus Linear/GitHub and analytics — and asks you for exactly the missing numbers,
  in one message, when not.
- **Tracks your promises.** Every commitment and ask is logged; next month's update
  opens by revisiting them. That follow-through is what builds investor trust.
- **Writes in your voice**, following an 8-section structure refined from updates VCs
  rate highly: CEO letter → financials → product → velocity → team → culture →
  strategy → forecast & asks.
- **Renders a shareable page in YOUR brand**: it fetches your website, picks up your
  logo, colors and font (you confirm before it's used), and produces a clean
  single-file HTML page with anchor navigation and metric callouts, ready for any
  static host — or just send the markdown.
- **Publishes it too** — to your own hosting (Vercel, Netlify, GitHub Pages) when
  connected, or to [here.now](https://here.now) with **no account needed**, including
  password-protected or invite-only links for confidential updates.
- **Never invents a number.** Missing data is stated as missing. Fabricated metrics
  end founder-investor relationships; this skill refuses to produce them.

## Install

**Claude Code** — copy the skill into your project (or user) skills folder:

```bash
mkdir -p .claude/skills/investor-update
curl -o .claude/skills/investor-update/SKILL.md \
  https://raw.githubusercontent.com/Pitchdrive/investor-update-skill/main/SKILL.md
```

Then in Claude Code, just ask:

> draft my July investor update

Other agents: any runtime that reads `SKILL.md`-style instructions works — or paste the
skill body into your agent's custom instructions.

## Connect your data (optional but recommended)

The skill checks what's already connected and offers manual entry for the rest.
To get automatic numbers, connect MCP servers for the tools you use — e.g. Stripe,
HubSpot, Salesforce, QuickBooks, Xero, Exact Online, Mercury, Linear, GitHub. See your platform's connector/MCP documentation; in
Claude Code these are configured with `claude mcp add`.

No connectors? Fine — the skill asks for a compact list of numbers and does the rest.

## What's in this repo

| File | Purpose |
|---|---|
| `SKILL.md` | The skill — this is the only file you need |
| `templates/update-structure.md` | The 8-section skeleton, for humans who want to write by hand |
| `examples/example-update.md` | A fictional company's update showing the target quality |

## The philosophy

An investor update is not a press release. The updates that get replies (and follow-on
checks) are the ones where the founder states the bad month in the first sentence,
shows the promise they missed next to the one they kept, and ends with an ask specific
enough to answer from a phone. This skill optimizes for that — not for making things
look good.

---

Made with ♥ by [Pitchdrive](https://pitchdrive.com) — we back founders from idea to
Series A. PRs welcome.
