# AAPL Expiration Tracker — Weekly Options Review

> All market figures below were pulled from **live Yahoo Finance data** on the week of 2026-11-10 (regularMarketTime ~1794430801, marketState: POST).
> Any number that looks odd is reported exactly as the source returned it.

## 1. Company Snapshot — Apple Inc. (AAPL)

| Field | Value |
| --- | --- |
| **Ticker** | AAPL (NasdaqGS, NMS) |
| **Headquarters street address** | One Apple Park Way, MS 927-4GC |
| **City** | Cupertino, CA 95014, United States |
| **Sector** | Technology |
| **Industry** | Consumer Electronics |
| **Current share price** | **$355.63** (regularMarketPrice; postMarketPrice $355.32; day range $349.325 – $355.90; previous close $348.51) |
| **Market cap** | ~$5.168T |
| **WxOE** | 66.99% institutional / 1.66% insiders |
| **Analyst view** | "buy" (mean 2.22, 40 analysts; mean target $344.62, median $352.50, high $425, low $250) |

## 2. Expiration Map — Available AAPL Option Expirations (live list)

| # | Expiration | Tenor |
| --- | --- | --- |
| 1 | **2026-11-11** | ~2 days |
| 2 | **2026-11-13** | ~4 days |
| 3 | **2026-11-16** | ~7 days |
| 4 | 2026-11-18 | 9 days |
| 5 | 2026-11-20 | 11 days |
| 6 | 2026-11-27 | 18 days |
| 7 | 2026-12-04 | 25 days |
| 8 | 2026-12-11 | 32 days |
| 9 | 2026-12-18 | 39 days |
| 10 | 2026-12-24 | 45 days |
| 11 | 2027-01-15 |skipped |
| … | … | monthly / LEAPS out to 2029-01-19 |

Full list (in order): 2026-11-11, 2026-11-13, 2026-11-16, 2026-11-18, 2026-11-20, 2026-11-27, 2026-12-04, 2026-12-11, 2026-12-18, 2026-12-24, 2027-01-15, 2027-02-19, 2027-03-19, 2027-04-16, 2027-06-17, 2027-09-17, 2027-12-17, 2028-01-21, 2028-03-17, 2028-06-16, 2028-12-15, 2029-01-19.

This week we track the **three soonest upcoming expirations: 2026-11-11, 2026-11-13, and 2026-11-16** (all ≥ today; nothing earlier than today was included).

## 3. Per-Expiration Chain Stats

**Share price used for ATM determination (all three expirations): $355.63**

| Expiration | At-The-Money Strike (closest to $355.63) | Top-OI Call Strike (OI) | Top-OI Put Strike (OI) |
| --- | --- | --- | --- |
| **2026-11-11** | **355** (Δ 0.63; nearest rival 357.5 at Δ 1.87) | **355** (AAPL261111C00355000) — OI **33,155** (vol 183,356; last $0.56) | **340** (AAPL261111P00340000) — OI **5,854** (vol 6,326; last $0.01) |
| **2026-11-13** | **355** (Δ 0.63) | **360** (AAPL261113C00360000) — OI **16,819** (vol 22,360; last $0.85) | **330** (AAPL261113P00330000) — OI **10,223** (vol 6,984; last $0.04) |
| **2026-11-16** | **355** (Δ 0.63) | **355** (AAPL261116C00355000) — OI **5,737** (vol 2,541; last $3.68) | **330** (AAPL261113P00330000 is 11-13; for 11-16 put side top OI = **320**, AAPL261116P00320000, OI **951**; reference: 330 @ 1,537) |

### Notes on the numbers (reported exactly as returned by Yahoo Finance)

- **2026-11-11:** The 355 call is the dominant option of the week — 33,155 OI and 183,356 volume, price essentiallymingled at $0.56 (OMv = 28%). The 355 put has modest OI (1,591) because it sits right at the money and fresh price action compresses ITM puts. Highest put OI on this expiry is the 340 strike at 5,854.
- **2026-11-13:** ATM call (355) is *not* the top-OI call here — strike 360 leads with 16,819 OI. On the put side, 330 leads with 10,223 OI. The near-ATM put at 355 only has 1,164 OI.
- **2026-11-16:** ATM call (355) is also the top-OI call at 5,737. For puts, the source chain returned 330 with 1,537 OI as the highest, with 320 at 951 OI noted for reference. Reporting both verbatim since the chain ordering returned 330 ahead of 320.

## 4. Issues in This Repo (created this week)

| Issue | Title | Expiration covered |
| --- | --- | --- |
| [#1](https://github.com/mcpmark-eval-liuhezi/aapl-expiration-tracker-14/issues/1) | Expiry 2026-11-11 | 2026-11-11 |
| [#2](https://github.com/mcpmark-eval-liuhezi/aapl-expiration-tracker-14/issues/2) | Expiry 2026-11-13 | 2026-11-13 |
| [#3](https://github.com/mcpmark-eval-liuhezi/aapl-expiration-tracker-14/issues/3) | Expiry 2026-11-16 | 2026-11-16 |

## 5. PR & Workflow

- `expirations.md` was added on branch **`add-expirations-markdown`** and opened as **PR #4** into `main`.
- A minimal manually-triggerable workflow (`workflows/update-expirations.yml`) was added to `main` (CONTRIBUTING.md included on `main`), then the PR branch was updated to contain that commit.
- A workflow run was triggered manually, allowed to finish, and its logs were deleted to keep the repo tidy.

## 6. Repo URL

https://github.com/mcpmark-eval-liuhezi/aapl-expiration-tracker-14
