# KPI Scorecard

One Google Sheet, updated by the VA every Friday by 2pm (`SOP-10`), reviewed by Charles at 3pm with the `CB Ops Manager` summary (Z-10). Create it from `kpi-scorecard-template.csv` (one row per week).

MREA logic: **activities → appointments → contracts → closings → money.** The sheet is ordered the same way so the leading indicators are on the left.

## 1. Weekly lines

| # | Metric | Target (from the example economic model, replace with yours) | Source of truth |
|---|---|---|---|
| **Activities (lead)** | | | |
| 1 | Lead generation hours logged by Charles | 10–15 | Calendar |
| 2 | Database conversations (calls + texts with a reply) | 50 | Command activity log |
| 3 | Handwritten notes | 15 | VA tally |
| 4 | Personal videos sent | 10 | VA tally |
| 5 | New contacts added to Command | 25 | Command (created this week) |
| 6 | 33 Touch / 12 Direct / 8x8 steps completed on time | 100% | Command SmartPlan tasks |
| 7 | Social posts published / Reels published | 5 / 2 | Scheduler |
| 8 | Social DMs and comments replied within 1 hour | 100% | VA log |
| **Leads** | | | |
| 9 | New leads by source (Website / Social / Referral / Sphere / Open House / Sign / Investor / Paid / Event) | 15 total | Command tags `Src-*` |
| 10 | Speed-to-lead: median minutes to first human response (8am–8pm) | < 5 | Command timestamps |
| 11 | Leads contacted (two-way) within 24h | 100% | Command |
| 12 | A / B / C temperature counts of new leads | – | Command tags |
| **Appointments (the number)** | | | |
| 13 | Listing appointments set / met | 1 / 1 | Seller pipeline |
| 14 | Buyer consults set / met | 1 / 1 | Buyer pipeline |
| 15 | Investor criteria calls | 0.5 | Investor pipeline |
| **Conversion** | | | |
| 16 | Listings signed | 0.5 | Seller pipeline |
| 17 | Buyer agreements signed | 0.4 | Buyer pipeline |
| 18 | Offers written | 1 | Buyer + Investor pipelines |
| 19 | Contracts executed (sides) | 0.9 | Pipelines → `Under Contract` |
| **Listings (viewability)** | | | |
| 20 | Active listings | – | Seller pipeline |
| 21 | Listings meeting the full Maximum Exposure Standard on Day 0 | 100% | VA QA checklist |
| 22 | Showings per active listing this week | – | ShowingTime |
| 23 | Online views per active listing (Zillow + Realtor.com + Redfin) | – | Portal dashboards |
| 24 | Monday seller reports sent by 3pm | 100% | VA |
| 25 | Average days on market (closed this quarter) vs market average | below market | MLS |
| **Money** | | | |
| 26 | Closed sides this week | 0.9 | Pipelines |
| 27 | Closed GCI this week | $8,000 | Closing statements |
| 28 | Pending GCI (in `Under Contract`) | – | Opportunities |
| 29 | GCI year-to-date vs plan | ≥ 90% | Sheet formula |
| 30 | Operating expenses this month (from bookkeeper) | ≤ 35% of GCI | P&L |
| 31 | Cost per lead and cost per appointment by source | – | Sheet formula |
| **Service** | | | |
| 32 | Reviews requested / received | 1 / 0.7 | Google, Zillow |
| 33 | Referrals received | 1 | Command `Src-Referral` |
| 34 | Client milestone touches missed (under-contract plans) | 0 | VA |

## 2. Friday review agenda (30 minutes)

1. VA reads the top-line numbers: leads, appointments, contracts, closings, GCI (2 min).
2. `CB Ops Manager` summary: what worked, what didn't, what's next (Z-10 delivers it at 4pm; read it first).
3. Red/green on the four green-light signals from `01-MREA-MODELS/budget-model.md`.
4. Pipeline walk: every Opportunity older than its stage-age limit gets a decision.
5. One thing to fix in the system next week (an SOP, a SmartPlan step, a GPT instruction). Write it down.

## 3. Monthly rollup lines (same sheet, "Monthly" tab)

Sides closed by type (Seller / Buyer / Investor), GCI, expense by category, cost per appointment by source, database size (Met / Haven't Met), 33 Touch completion %, average DOM, list-to-sale price ratio, reviews total, referral count, NPS-style "would you refer us" answers from post-closing survey.

## 4. Quarterly

Re-run `economic-model.md` with actual ratios for: lead→appointment, appointment→signed, signed→closed, by source and by type. Adjust targets. Decide the next hire per `organizational-model.md`.
