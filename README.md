# Hapoalim Finance

A lightweight, single-page finance tracker for Bank Hapoalim Excel exports. No accounts, no backend — runs entirely in your browser. Hebrew UI, RTL layout.

**Live app → [avitalboas-dev.github.io/hapoalim-finance](https://avitalboas-dev.github.io/hapoalim-finance/)**  
**Architecture → [architecture.html](https://avitalboas-dev.github.io/hapoalim-finance/architecture.html)**

---

## How it works

1. Export a transaction Excel file from Bank Hapoalim (פירוט תנועות)
2. Drop the file onto the upload screen
3. Browse your spending by category, view monthly flow, and search or filter transactions

---

## Features

**סקירה (Overview tab)**
- Spending & income breakdown by category — click any category to filter transactions below
- Sortable transactions table — click any column header to sort by date, description, category, or amount
- Category editor — reassign any transaction's category; changes apply across all matching merchants and sync automatically
- "↗ מגמה" button appears when a category is active, jumping to the Trends tab

**מגמות (Trends tab)**
- Monthly flow chart showing income vs. spending over time
- Category trend chart — month-by-month spending for a selected category

**Shared**
- Period selector — current month (default), last 3 months, last 6 months, all time, or a custom date range
- Transactions remembered between sessions (no re-upload needed)

---

## Data & persistence

| What | Where | Scope |
|------|-------|-------|
| Transactions | Browser `localStorage` | Per device — each person uploads their own Excel file |
| Category mappings | [JSONBin.io](https://jsonbin.io) | Shared — syncs automatically across all devices |

Category edits save to JSONBin instantly on every change and are loaded from there on startup. No manual export or commit needed.

---

## Local development

No build step needed. Just open `index.html` in a browser.

```bash
# Serve locally (avoids fetch restrictions on file:// URLs)
npx serve .
```

---

## Deployment

The app is deployed via GitHub Pages from the `main` branch root. Any push to `main` updates the live site within a minute or two.
