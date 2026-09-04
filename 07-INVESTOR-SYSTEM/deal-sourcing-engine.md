# Deal Sourcing Engine

The capital partner program is only as good as the deal flow. This is the MREA lead generation model pointed at properties instead of people: **prospecting + marketing, aimed at a database of deal sources and distressed properties, systematically.**

Target: **20 candidate properties screened per week, 3 underwritten, 1 offer, 1 deal presented per month** in year one. Adjust with the scorecard.

## 1. Where flip deals come from (build all of these, in this order)

| # | Source | How | Owner | Weekly rhythm |
|---|---|---|---|---|
| 1 | **MLS: aged, as-is, estate, price-reduced, back-on-market** | Saved MLS searches: DOM > 45, keywords "as-is", "estate", "investor", "handyman", "TLC", "cash only", "sold as is", price reductions > 5%, expired and withdrawn in the last 90 days | VA pulls Mon/Thu, Charles screens | 10 candidates/week |
| 2 | **Wholesalers and other agents** | Build a `Deal-Source` list in Command: every wholesaler, investor-friendly agent, and REIA regular. Monthly call, immediate response when they send a deal, close fast on the first one to become their first call | Charles | 5 calls/week |
| 3 | **Direct-to-seller: absentee and distressed owner mail** (the investor version of 12 Direct) | List: absentee owners 10+ years, high equity, code violations, pre-foreclosure, probate, tax delinquent, tired landlords in target areas. 500–1,000 addresses, monthly letter or postcard, phone number and Sell page link with `?src=investor-mail` | VA (list + mail), Charles (calls) | 1 mailing/month, 5 seller calls/week |
| 4 | **Driving for dollars** | Charles's showing routes: photograph distressed properties, VA skip-traces and adds to the mail list and to Command with `Src-Investor-List` | Charles + VA | 10 addresses/week |
| 5 | **Attorneys, CPAs, lenders, property managers** | Probate and estate attorneys, divorce attorneys, hard-money lenders (they see defaults), property managers (tired landlords). Quarterly coffee, monthly email, referral fee only where legal and disclosed | Charles | 2 meetings/month |
| 6 | **Seller leads that do not fit a retail listing** | Every seller lead through the funnel that says "as-is", "fast", "inherited", "tenant", or "behind" gets a cash-offer option alongside the listing option | Charles | Ongoing |
| 7 | **Auctions and REO** | County tax sale and trustee sale lists, REO agents' lists, HUD | VA monitors | Monthly |
| 8 | **Contractors** | Contractors see distress first. Every contractor on the vendor bench knows Charles pays a finder's fee where allowed | Charles | Ongoing |

The seller funnel and the deal engine are the same funnel with two exits: **list it** (retail) or **buy it** (partner-funded). Every seller conversation offers both, which is itself a white-glove touch for sellers who need speed or cannot make repairs.

## 2. The Deal Board (Google Sheet, one row per candidate)

Columns, in order. Z-12 watches this sheet.

| Column | Filled by | Notes |
|---|---|---|
| Deal ID | auto | `[YYYY]-[###]` |
| Date added | auto | |
| Address | VA | |
| Source | VA | MLS / Wholesaler name / Mail / D4D / Attorney / Seller lead / Auction / Contractor |
| Source contact (Command link) | VA | |
| Asking / wholesaler price | VA | |
| Beds / baths / sqft / year / lot | VA | |
| Condition notes | Charles | after walkthrough or photos |
| ARV estimate | Charles | from `deal-analysis-template.md` |
| Rehab estimate | Charles | line-item scope + 15% |
| MAO (70% rule) | formula | `ARV × 0.70 − Rehab` |
| Gap (asking − MAO) | formula | negative = works at asking |
| Est. profit / ROI | formula | from underwriting |
| Status | Charles | `Lead → Underwriting → Offer → Under Contract → Funded → Rehab → Listed → Sold → Passed` |
| Pass reason | Charles | Price / Rehab too heavy / ARV not supported / Area / Structural / Title / Timing |
| Memo approved | Charles | checkbox; flips Z-12 to send the Deal Alert |
| Partner (Command link) | VA | once committed |
| Deal folder link | Z-12 | Drive: `Deals/[YYYY-###] [Address]/` with `01-Photos`, `02-Comps`, `03-Scope-Bids`, `04-Deal-Memo`, `05-Contracts`, `06-Project-Tracker`, `07-Resale` |
| Notes | anyone | |

Pass reasons are reported monthly to partners ("deals we passed on and why") and reviewed quarterly to tune sourcing.

## 3. Weekly sourcing rhythm

| Day | Activity | Owner | Time |
|---|---|---|---|
| Mon | VA pulls MLS saved searches, auction lists, and inbound wholesaler emails into the Deal Board as `Lead` | VA | 60 min |
| Mon | Charles screens the board: 30-second pass/underwrite decision per row, using photos, price, and area | Charles | 30 min (inside lead gen block) |
| Tue | VA gathers comps, tax, permits, flood, HOA for `Underwriting` rows; `CB Investor Analyst` first-pass numbers | VA | 90 min |
| Wed | Charles walks the 2–3 best with the lead contractor; scope and ARV confirmed; MAO set; offers written | Charles | Afternoon block |
| Thu | Deal source calls (5) and absentee-owner seller calls (5) | Charles | Inside lead gen block |
| Thu | VA pulls second MLS run; updates pass reasons | VA | 30 min |
| Fri | Deal Board review in the scorecard meeting: candidates, underwritten, offers, presented, funded | Charles + VA | 10 min |

## 4. The 30-second screen (Charles, Monday)

Pass immediately if any of these: ARV band the partners do not buy; obvious structural or foundation issue with no price to match; flood zone A/AE without a plan; HOA that bans flips or short holds; title red flags (probate not opened, liens exceeding value); asking price more than 20% above a rough MAO with a seller who "will not negotiate."

Underwrite if: asking within 20% of rough MAO, cosmetic-to-moderate rehab, resale comps visibly present, motivated seller signal (estate, vacant, tenant issue, price cuts).

## 5. Deal Source network (Command)

Tag `Deal-Source` plus `Met`. They are on `SP-33 Touch (Met)` with these substitutions: the items of value are "what I am buying right now" one-pagers (buy box), and 4 of the 8 calls are "what do you have?" calls. Every deal they send gets a same-day response even if it is a pass, with the reason. Every closed deal they sourced gets a handwritten note and, where legal and disclosed, the agreed fee within 5 days of closing. Speed and reliability are the entire relationship.

## 6. Sourcing scorecard lines (add to `10-SCORECARD`)

| Metric | Target |
|---|---|
| Candidates added to Deal Board | 20/week |
| Underwritten | 3/week |
| Offers written | 1/week |
| Deals presented to partners | 1/month |
| Deals funded | 1 per 1–2 months in year one |
| Deal source conversations | 5/week |
| Absentee/distressed seller conversations | 5/week |
| Average days: Lead → Presented | < 10 |
| Average days: Presented → Committed | < 3 |
