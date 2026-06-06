# YNAB Amazon Transaction Enrichment

A product concept and interactive mockup for an Amazon order enrichment feature in [YNAB (You Need A Budget)](https://www.ynab.com).

## The Problem

YNAB shows Amazon transactions as raw order IDs — `304-1431326-3637907 AMZ` — with no product name. Users have to manually cross-reference their Amazon order history to remember and categorize what they bought. Amazon provides no official API, so there is no native solution today.

This is a widely discussed pain point in the YNAB community on Reddit and YNAB's own feature request forum.

## The Solution

Connect your email account. YNAB scans Amazon order confirmation emails and automatically enriches matching transactions with the actual product name in the memo field — plus a suggested budget category.

Both are shown as suggestions, not forced overwrites. You stay in control.

## How Matching Works

- Amazon order confirmation emails contain the order total and order date
- YNAB transaction has the charge amount and charge date (typically 1–3 days after order)
- Matching: **amount + date window (±3 days)**
- Ambiguous matches (same amount, same week): auto-select closest date, flag for manual confirmation
- Confidence indicator: high confidence vs. please confirm

## Screens

| # | Screen | Description |
|---|---|---|
| 1 | Announcement modal | "Give your Amazon transactions a name." — triggered on first login after feature launch |
| 2 | Email provider selection | Gmail / Outlook / IMAP — OAuth connection with privacy explanation |
| 3 | Enriched transaction list | Product names appear as italic suggestions in the memo column |
| 4 | Transaction detail | Confirm or edit memo and category suggestion *(planned)* |
| 5 | Ambiguous match | User picks between two possible orders *(planned)* |
| 6 | Settings | Manage email connection *(planned)* |

## Running the Mockup

No build step needed. Open directly in your browser:

```bash
open index.html
# or on Linux:
xdg-open index.html
```

## Tech Stack

**Mockup (current):** Plain HTML + CSS, single file, no dependencies.

**Planned implementation:**
- Next.js + TypeScript
- Gmail / Outlook OAuth (read-only, Amazon emails only)
- YNAB API (read + write transactions)

## Status

This is a **product design mockup** — not a production application. Built as a PM portfolio piece and product proposal.

---

*Made with curiosity by [Alicia Mengelkamp](https://github.com/amengelkamp)*
