# murph-data

Cron-written data for the Murph site, served by GitHub Pages at
https://murph-hq.github.io/murph-data/. The site's code lives in a separate
repo; data commits here never build or deploy the site.

| Directory | Written by | Cadence |
|---|---|---|
| `feeds/` | `scripts/snapshot-feeds.mjs` | hourly, plus the kickoff clusters |
| `line-history/` | `scripts/snapshot-lines.mjs` | slate-aware clusters |
| `forward-test/` | `scripts/snapshot-projections.mjs` | slate-aware clusters |
| `availability/` | `scripts/snapshot-availability.mjs` | slate-aware clusters |

Every file in `feeds/` is `{ "capturedAt": <ms>, "data": ... }`. The site
shows `capturedAt` and warns when a feed is more than three hourly runs old.

**Do not rewrite history in `line-history/` or `forward-test/`.** Commit
times here are the record that each projection was frozen before kickoff.
Rows frozen before this repo existed are in the site repo's history, up to
the commit that moved them.
