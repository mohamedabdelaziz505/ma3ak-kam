# GitHub market prices setup
The workflow `.github/workflows/update-market-prices.yml` refreshes `data/market_prices.json` every 10 minutes and can also be started manually.
Before enabling it, add the GoldTimo key to the repository without putting it in the source code:
1. Open the repository on GitHub.
2. Go to **Settings → Secrets and variables → Actions**.
3. Select **New repository secret**.
4. Set the name to `GOLDTIMO_API_KEY` and paste the key as the value.
5. Open **Actions → Update Egyptian market prices → Run workflow** once.
The workflow uses the free GoldTimo endpoints for gold gram prices in EGP for 18K, 21K, and 24K, plus the currency rates endpoint. It commits only when `data/market_prices.json` changes.
The key must remain a GitHub Actions secret. Do not add it to this repository, the Flutter APK, or the public JSON file.
