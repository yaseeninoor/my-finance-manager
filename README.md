# My Finance Manager

A mobile-friendly personal finance dashboard built for daily use on iPhone, with AED currency and Tamil/English interface.

## Features
- Overview cards for total balance, income, expenses and net savings.
- Add income and expenses with category, account, date and notes.
- Search and filter transaction history.
- Cash-flow and category charts (Chart.js loads from a CDN when online).
- Accounts with opening balances and live calculated balances.
- Monthly category budgets.
- CSV export and JSON backup/restore.
- Dark mode and Tamil/English toggle.
- Local browser storage; no bank login or server account required.
- Installable/offline shell on browsers that support service workers.

## Run it
1. Open the repository on GitHub.
2. Go to **Settings → Pages**.
3. Under Build and deployment, select **Deploy from a branch**.
4. Choose **main** and **/(root)**, then Save.
5. Wait for GitHub Pages to publish, then open the published site in Safari.
6. On iPhone, use Safari's **Share → Add to Home Screen** to install it.

The app is static; it does not need API keys or a backend. The charts use Chart.js via CDN, so charts may not render while fully offline, but transaction entry and saved records still work.

## Important privacy notes
- Transaction records are stored in this browser's local storage on this device. They are not automatically synced to iCloud or another device.
- Private browsing, clearing website data, or changing browsers can remove local records. Use **Settings & backup → Download backup** regularly.
- GitHub Pages publishes the app source publicly when this repository is public. Never commit your real transaction exports or JSON backups into the repository.
- For stronger privacy, set the repository to **Private**. Note: GitHub Pages access and availability depend on your GitHub plan and repository settings.
- This is a personal budgeting tool, not a bank-connected or audited accounting application.

## Files
- `index.html` — application structure
- `style.css` — responsive interface and themes
- `app.js` — local data, transactions, reports, accounts, budgets and exports
- `manifest.json` — install metadata
- `service-worker.js` — app shell cache

## Backup format
Use the built-in JSON backup button. Restore replaces current local app data, so export a fresh backup before restoring if you want to keep the current version.