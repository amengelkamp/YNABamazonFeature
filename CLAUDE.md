# YNABamazonFeature

A product mockup and future implementation of an Amazon order enrichment feature for YNAB (You Need A Budget).

## What This Is

YNAB shows Amazon transactions as raw order IDs (e.g. `304-1431326-3637907 AMZ`) with no product name. This project:

1. **Phase 1 (current):** HTML/CSS interactive mockup — used as a PM portfolio piece / product proposal for YNAB
2. **Phase 2 (planned):** Actual implementation — connects user email via OAuth, parses Amazon order confirmation emails, matches to YNAB transactions by amount + date, enriches memo field with product name

## Feature Brief

See `/home/alicia/ynab-amazon-feature-brief.md` for full product brief including problem statement, user research, matching logic, and screen-by-screen flow.

## Tech Stack (Phase 1 — Mockup)

- Plain HTML + CSS, no framework
- Single file: `index.html`
- Open directly in browser — no build step needed

## Tech Stack (Phase 2 — Planned)

- Next.js + TypeScript
- Gmail / Outlook OAuth (read-only, Amazon emails only)
- YNAB API (read + update transactions)
- Matching logic: amount + date window (±3 days), closest-date tiebreaker

## Color Palette

All colors extracted from the real YNAB UI:

| Variable | Value | Usage |
|---|---|---|
| Sidebar | `#1a2340` | Dark navy sidebar background |
| Primary | `#4046ca` | Buttons, icons, links |
| Notif bar | `#eeeef8` | Top notification bar |
| Positive | `#2e7d32` | Green balance amounts |
| Cleared | `#4caf88` | Cleared transaction dot |
| Enriched | `#b85c00` | Amber memo suggestion text |

## Screens (Mockup)

| Screen | Status | Description |
|---|---|---|
| 1. Announcement modal | ✅ Done | "Give your Amazon transactions a name." |
| 2. Email provider selection | ✅ Done | Gmail / Outlook / IMAP picker |
| 3. Enriched transaction list | ✅ Done | Product names in memo column |
| 4. Transaction detail | 🔲 Planned | Confirm/edit suggestion |
| 5. Ambiguous match | 🔲 Planned | User picks between two orders |
| 6. Settings | 🔲 Planned | Manage email connection |

## Development

```bash
# Open mockup in browser
xdg-open index.html
```

No dependencies, no build step.
