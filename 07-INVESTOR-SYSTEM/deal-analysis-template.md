# Fix & Flip Underwriting Template

This is the math behind every Deal Memo. `CB Investor Analyst` fills it (code interpreter on) from the inputs below; Charles confirms ARV and rehab in person before anything is presented. Rental math is included as the backup exit.

**Every output ends with:** *"All figures are estimates based on the assumptions listed. The partner is responsible for verifying them. Returns are not guaranteed. Structure and terms are set by an attorney-drafted agreement."*

## 1. Inputs (all required; the GPT asks for missing ones in one batch)

```
DEAL INPUTS
Deal ID / Address:
Source:
Purchase price (offer or asking):
Closing costs on purchase ($ or %; default 2%):
ARV comps (3 to 6): address, sale date, price, sqft, beds/baths, condition, distance, adjustment
ARV (Charles-confirmed):
Rehab scope (line items) and contractor bids:
Rehab contingency (default 15%):
Timeline: rehab months, marketing months (default: rehab per scope, marketing 2 months)
Holding costs monthly: taxes, insurance (vacant/builder's risk), utilities, HOA, lawn/security
Financing: cash, or loan amount, rate, points, term, interest-only? (Structure C: partner is the lender)
Selling costs: listing + buyer agent commission (%), seller closing costs (%), concessions (default 1%), staging ($)
Backup exit: market rent, PM fee %, vacancy %, maintenance %, refinance LTV and rate
Partner structure (A / B / C) and terms, if known
```

## 2. The formulas (show every one in the memo)

```
Total rehab            = sum(line items) × (1 + contingency)
Purchase costs         = purchase price × closing cost %
Holding months         = rehab months + marketing months + 1 (buffer)
Holding costs          = monthly holding × holding months
Financing costs        = points + (loan × rate ÷ 12 × holding months)          [0 if all cash]
Selling costs          = ARV × (commission % + closing %) + concessions + staging
Total project cost     = purchase + purchase costs + rehab + holding + financing + selling
Gross profit           = ARV − total project cost
Total cash in          = purchase + purchase costs + rehab + holding + financing − loan proceeds
ROI                    = gross profit ÷ total cash in
Annualized ROI         = ROI × (12 ÷ holding months)
MAO (70% rule)         = ARV × 0.70 − total rehab
Price vs MAO           = purchase price − MAO        (negative is good)
Profit margin on ARV   = gross profit ÷ ARV          (target ≥ 10–12%)
Break-even ARV         = total project cost          (ARV at which profit = 0)
Cushion                = (ARV − break-even ARV) ÷ ARV
```

## 3. Sensitivity table (required in every memo)

| Scenario | ARV | Rehab | Holding months | Gross profit | ROI |
|---|---|---|---|---|---|
| Base | as underwritten | as underwritten | as underwritten | | |
| ARV −5% | | | | | |
| Rehab +15% (beyond contingency) | | | | | |
| Hold +30 days | | | | | |
| All three at once (stress case) | | | | | |

A deal is presented only if the **stress case still clears $0** and the base case clears the minimum profit standard in `capital-partner-program.md` §6.

## 4. Worked example (numbers are illustrative)

| Line | Value |
|---|---|
| Purchase price | $220,000 |
| Purchase costs (2%) | $4,400 |
| Rehab line items | $48,000 |
| Contingency 15% | $7,200 → total rehab **$55,200** |
| ARV (3 comps: $342k, $349k, $355k, adjusted) | **$345,000** |
| MAO = 345,000 × 0.70 − 55,200 | **$186,300** (purchase is $33,700 above MAO; flagged) |
| Holding: 4 rehab + 2 market + 1 buffer = 7 months × $1,100 | $7,700 |
| Financing: all cash | $0 |
| Selling: 5% commission + 1.5% closing + 1% concessions + $2,500 staging | $28,375 |
| Total project cost | $315,675 |
| Gross profit | **$29,325** |
| Total cash in | $287,300 |
| ROI / annualized | **10.2% / 17.5%** |
| Margin on ARV | 8.5% (below the 10% target; flagged) |
| Stress case (ARV −5%, rehab +15%, +30 days) | $345,000×0.95 = $327,750 − ($315,675 + $8,280 + $1,100 + selling on lower ARV −$1,380) = **$4,075** (barely clears) |

Verdict for the memo: **Offer at $195,000 or pass.** At $195,000 the base profit is ~$54,000 (16% ROI, margin 15.7%) and the stress case clears ~$29,000. The memo shows both the asking-price case and the offer-price case.

## 5. Backup exit: rent and refinance

```
Gross rent (monthly, from 3+ rental comps)
− Vacancy (default 5–8%)
− Property management (default 8–10%)
− Maintenance/capex reserve (default 8–10%)
− Taxes, insurance, HOA
= NOI (monthly × 12 = annual NOI)
Cap rate                = annual NOI ÷ total project cost (before selling costs)
Refinance loan          = appraised value × LTV (default 70–75%)
Cash left in deal       = total cash in − refinance loan
Debt service            = payment on refinance loan
Cash flow               = NOI − debt service
Cash-on-cash            = annual cash flow ÷ cash left in deal
DSCR                    = NOI ÷ debt service   (lenders usually want ≥ 1.2)
1% rule check           = monthly rent ÷ total project cost ≥ 1%?
```

If the backup exit does not at least break even on cash flow, say so in the memo. The partner should know the floor.

## 6. Red-flag checklist (every item answered Yes/No/Unknown in the memo)

- Flood zone (FEMA map) and insurance cost confirmed
- Foundation, roof age, sewer line (scope a camera inspection on pre-1980 homes), electrical panel type, plumbing material, HVAC age
- Permits: open permits, unpermitted additions, what the rehab will require and the typical timeline in [MARKET]
- Title: liens, judgments, probate status, HOA dues owed, code violations, easements
- HOA rules on rentals, flips, exterior changes
- Occupancy: tenants, leases, eviction timeline, personal property
- Environmental: asbestos, lead paint (pre-1978), oil tank, mold
- Comps: are they truly renovated-condition sales, within 6 months, within 0.5 mile? Any new construction skewing ARV?
- Resale market: months of inventory in the price band, average DOM for renovated homes
- Insurance: can it be insured vacant during rehab, at what cost
- Neighbor and lot: drainage, encroachments, driveway, parking

## 7. Assumptions register (appended to every memo)

| Assumption | Value used | Source | Confidence |
|---|---|---|---|
| ARV | | comps listed | H/M/L |
| Rehab | | bids / Charles walkthrough | |
| Holding months | | scope + [MARKET] DOM | |
| Selling costs | | | |
| Rent (backup) | | | |
