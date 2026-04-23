---
name: Hapoalim Finance project overview
description: Stack, deployment, storage, credentials, and two-user setup for the hapoalim-finance app
type: project
---

Single-page Hebrew RTL finance tracker for Bank Hapoalim Excel exports. No build step — everything in `index.html`.

**Stack:** Vanilla JS, SheetJS (CDN) for Excel parsing, Heebo font, ₪ / he-IL locale  
**Deployment:** GitHub Pages from `main` branch root → avitalboas-dev.github.io/hapoalim-finance/  
**Repo:** https://github.com/avitalboas-dev/hapoalim-finance

**Storage:**
- Transactions: `localStorage` (per device, key `hapoalim_tx_v1`)
- Category mappings: JSONBin.io (shared across devices)
  - Bin ID: `69ea51e036566621a8e4720e`
  - Access Key: `$2a$10$TbGux.P1oGnU9iKotg.vQ.xn0C34/DERAb..0AuacbKfF6S53IP9y`

**Two-user setup:** User and wife each upload their own Excel file. Category edits sync via JSONBin automatically.

**Excel format (Bank Hapoalim פירוט תנועות):**
- Header row detected dynamically by scanning for "תאריך" cell
- Columns: תאריך→date, הפעולה→op, פרטים→details, חובה→debit, זכות→credit, לטובת→for_who, עבור→for_what
- Dates: JS Date objects or DD/MM/YYYY strings
- credit = positive (income), debit = negative (expense)
- Category key format: `op.toLowerCase() + '|' + dir`

**Hebrew categories:** מזון וסופר, אוכל בחוץ, תחבורה, קניות, מנויים, בריאות, ילדים, בית, הכנסה, חיסכון, בידור, נסיעות, אחר  
**activeCat default:** `'הכל'` (not 'All')

**Why:** Identical feature set to family-finance (Revolut) but adapted for Israeli bank Hebrew Excel format.  
**How to apply:** When adding features, port from family-finance first, then adapt for Hebrew/RTL/Excel specifics.
