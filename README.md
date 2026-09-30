# feeds

Scheduled snapshots of public NFL data — schedules, rosters, injuries,
player usage and market lines — written by automated jobs and served as
static JSON from GitHub Pages.

| Directory | Contents | Cadence |
|---|---|---|
| `feeds/` | the latest copy of each upstream feed | hourly, more often around kickoffs |
| `line-history/` | market lines captured over the week | several times a day on game weeks |
| `forward-test/` | projections frozen before kickoff | several times a day on game weeks |
| `availability/` | injury and inactive status over the week | several times a day on game weeks |

Every file in `feeds/` is `{ "capturedAt": <ms>, "data": ... }`, where
`capturedAt` is when the snapshot was taken.

Commits are made by the jobs, not by hand. **History in `line-history/` and
`forward-test/` is never rewritten:** the commit times are the record that
each row was captured before kickoff.
