# Personal Budget Site

A clean, minimal personal budgeting dashboard. Deploys for free on GitHub Pages and syncs to Excel via Power Query.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The full website (single file, no dependencies except CDN) |
| `data.json` | Your exported budget data — this is what Excel reads |

---

## Deploy to GitHub Pages

1. Create a **public** GitHub repository (e.g. `budget`)
2. Upload both `index.html` and `data.json` to the root
3. Go to **Settings → Pages → Source → Deploy from branch → main / (root)**
4. Wait ~1 minute — your site is live at:
   `https://YOUR_USERNAME.github.io/budget/`

Your Power Query data URL will be:
`https://YOUR_USERNAME.github.io/budget/data.json`

---

## Connect Excel via Power Query

### One-time setup

1. Open Excel → **Data** tab → **Get Data** → **From Other Sources** → **From Web**
2. Paste your `data.json` URL → OK
3. In Power Query Editor:
   - Click the `transactions` field → **Convert to Table**
   - Click the expand icon on the `Column1` field → select all columns → OK
   - Rename columns as needed
   - Click **Close & Load**

### Set auto-refresh

1. **Data** tab → **Queries & Connections**
2. Right-click your query → **Properties**
3. Check **"Refresh every X minutes"** (e.g. 60)
4. Check **"Refresh data when opening the file"**
5. Click OK

Now every time you click "Download data.json" in the **Excel Sync** tab of your site and re-upload it to GitHub, Excel will pull the latest data automatically on your refresh schedule.

---

## Keeping data.json updated

When you add transactions on the site, your data is saved in the browser. To push it to Excel:

1. Go to **Excel Sync** tab on your budget site
2. Click **Download data.json**
3. Upload the new `data.json` to your GitHub repo (drag & drop onto the file in GitHub, click Commit)
4. Excel refreshes automatically at its next interval (or click **Refresh All**)

### Tip: use GitHub's web editor
You can drag and drop the new `data.json` directly onto the file in GitHub's web UI — no git knowledge needed.

---

## CSV Format (for importing transactions)

If you want to import from your existing Excel spreadsheet, export it as CSV with these columns:

```
date, description, amount, category, type
2026-05-01, Salary, 4200, Income, income
2026-05-02, Rent, 1200, Rent, expense
```

Then use **Add Transaction → Choose CSV file** to import.

---

## Categories

Groceries · Rent · Transport · Utilities · Dining · Entertainment · Health · Clothing · Savings · Income · Other
