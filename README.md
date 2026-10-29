# anima-runner

Two actions that check out the private repository `anima` and run its scripts (anima D-0083, D-0088):

- `build`: `scripts/build` (security scans, lint, typecheck, tests, build).
- `deploy`: `scripts/deploy` (arm64 image, scan, deploy to dev on AWS, smoke test, ZAP).
- `scan`: `scripts/scan` on what dev and production run, twice a month and beside each production deploy (anima D-0656).

Every output line goes to Better Stack (source `anima-ci`); the logs here show only step outcomes and are kept one
day.

Run them from the Actions tab, or:

    gh workflow run build  --repo Lemonade4400/anima-runner -f ref=main
    gh workflow run deploy --repo Lemonade4400/anima-runner -f ref=main
