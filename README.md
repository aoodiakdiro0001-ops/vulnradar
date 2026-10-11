# 📡 VulnRadar — Threat-Intel Dashboard (MIT)

Free niche aggregator for defenders: **live CVE tracker + bug bounty
board + exploit/advisory search + alerts**. UI in 6 languages
(EN default, TR/AR/FR/DE/ES); CVE data stays in source English.

## Data sources (all public)

- **CVE live feed:** `https://cve.circl.lu/api/last` (+ `/api/cve/<ID>`,
  vendor/product filter), auto-polled every 5 min in-page.
- **Detail links:** NVD (`nvd.nist.gov/vuln/detail/<ID>`),
  MITRE, Exploit-DB search.
- **Bounty board:** curated famous programs; links go to the **official
  public directories** (HackerOne/Bugcrowd verified, rest homepages).
  Reward tiers are broad bands ($–$$$$), not quotes — verify scope and
  rewards on the platform.

## Alerts

- **Free (works now):** watchlist (CVE-ID/keyword) + browser Notification
  API + JSON/CSV export. Keep the tab open; polling runs client-side.
- **Pro ($8/mo, needs backend):** Telegram instant + email digest +
  priority API. `Pro` interest is saved locally; wire a cron worker +
  Telegram Bot API + mailer before charging (see Minay backend notes).

## Ads

`CONFIG.ads` — paste AdSense (`client`+`slot`) or Carbon IDs; otherwise a
tasteful placeholder shows.

## Run / Deploy

```bash
cd vulnradar
python3 -m http.server 8080
```
Static single file (+README). GitHub Pages-ready from repo root.

## Honest limits

- No backend: no server-side scraping/scheduling; bounty "updates" =
  curated links + filters (add a scraper worker for live program diffs).
- CIRCL rate-limits; errors show a retry note, never fake data.
- Exploit-DB has no public API — integrated via search links.

## License

MIT.
