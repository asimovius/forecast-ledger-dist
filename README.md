# ForecastLedger

Public, versioned releases of the data products behind the ForecastLedger
graded BTC market-forecast registry.

## What this is

A **read-only data distribution point**. Nothing here is produced or hosted
from this machine — every artifact attached to a release was built on a
separate build host, then committed to this repository and tagged. Code
lives in the [source repository](https://github.com/asimovius/forecast-ledger);
the artifact feeds live here:

- **`/ledger`** — date-stamped snapshots of the public calibration ledger
  (markdown, e.g. `ledger/2026-10-08.md`): per-horizon record over the last
  30 graded calls, rolling hit-rate and Brier score, and the
  `un-armed`-below-minimum-n gate, stated plainly.
- **`/scorecards`** — one file per horizon (`24h`, `3d`, `7d`, `4w`):
  full history of every graded call, the calibration summary, and the
  scoring rules (Brier scored against the published naive baseline of 0.25)
  so anyone can recompute the numbers from raw records.
- **`/mcp`** — release manifests describing how to connect an MCP client
  to the registry server (stdio JSON-RPC 2.0), plus protocol notes.

## What it is not

- Not investment advice, a solicitation, or a management service.
- Not a signal feed. The dataset provides critical decision-making data
  points — graded market-forecast records and their calibration stats.
- Never contains perp funding, open interest, or any other
  exchange-internals-derived data. Those are internal analysis inputs and
  are not part of the dataset.
- Contains no credentials, keys, or private infrastructure details.