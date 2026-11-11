# Contributing to aapl-expiration-tracker

This repository tracks weekly Apple (AAPL) options expiration data for the risk desk.
All market figures must come from **live data** (Yahoo Finance option chains and stock
info endpoints) — never hard-coded from memory or a stale slide deck.

## Adding this week's data

1. Pull fresh data: `yahoo_finance_get_stock_info(AAPL)` for the company snapshot
   (address, city, sector, industry, current price) and
   `yahoo_finance_get_option_expiration_dates(AAPL)` for the expiration map.
2. For the three soonest upcoming expirations, fetch both chains
   (`yahoo_finance_get_option_chain` with `option_type: calls` and `puts`).
3. Compute per expiry:
   - ATM strike = strike closest to the current share price.
   - Highest-open-interest call strike (report the OI value exactly as returned).
   - Highest-open-interest put strike (report the OI value exactly as returned).
4. Create one tracking issue per expiration in date order, titled `Expiry YYYY-MM-DD`,
   with the ATM strike, top call OI strike, top put OI strike, and the share price used.
5. Add `expirations.md` on a feature branch and open a PR into `main`.
6. Add a minimal manually-triggerable workflow to `main` (one job that echoes a line),
   trigger it once, wait for completion, note the billable duration, then delete the
   run's logs to keep the repo tidy.
7. Check discussion categories; report findings.

## PR checklist

- [ ] Issues #1, #2, #3 exist for the three expirations in date order.
- [ ] `expirations.md` includes the company snapshot, full expiration list, and a
      per-expiration stats table.
- [ ] Numbers match live pulls; anything odd is reported verbatim from the source.
- [ ] CONTRIBUTING.md and the manual workflow are present on `main`.

## Workflow

A minimal `workflows/update-expirations.yml` is included on `main`. It is
`on: worklow_dispatch` (manual trigger) with a single job that echoes a line.
Use `gh api repos/{owner}/{repo}/actions/workflows/{workflow_id}/dispatches` or the
`gh workflow run` command to trigger it.
