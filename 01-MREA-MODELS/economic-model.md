# Economic Model

> MREA principle: *"Focus on the numbers you must hit, and let the activities that produce those numbers drive your day."*
> The economic model works backward from the income you want to the appointments you must go on, then to the leads and database size that produce those appointments.

The interactive version of this page is `10-SCORECARD/economic-model-calculator.html`. Open it in a browser, type your numbers, and it recalculates everything below. Print the result and put it where you can see it.

## 1. Start with the end: net income

| Line | Formula | Your number |
|---|---|---|
| A. Net income goal (annual, before tax) | you choose | $________ |
| B. Operating expense ratio | MREA teams typically run 35–50% of GCI in expenses; a solo agent + VA is closer to 30–40% | ____% |
| C. GCI required | A ÷ (1 − B) | $________ |
| D. Brokerage split / cap | KW cap + royalty; once capped, near 100% | $________ |
| E. Gross commission needed before splits | C + D | $________ |

Worked example (placeholder numbers, replace with yours):

| Line | Example |
|---|---|
| A. Net income goal | $250,000 |
| B. Expense ratio | 35% |
| C. GCI required | $250,000 ÷ 0.65 = **$384,615** |
| D. Split/cap paid to brokerage | ~$30,000 (until capped) |
| E. Gross needed | ~$415,000 |

## 2. Convert GCI to closings

| Line | Formula | Your number |
|---|---|---|
| F. Average sale price in [MARKET] | from MLS | $________ |
| G. Average commission side (%) | e.g. 2.5–3% | ____% |
| H. Average GCI per closed side | F × G | $________ |
| I. Closed sides needed | E ÷ H | ________ |
| J. Seller sides (target 50–60% of sides, MREA "lead with listings") | I × 0.55 | ________ |
| K. Buyer sides | I − J | ________ |
| L. Investor sides (subset of J and K, target 15–25%) | I × 0.20 | ________ |

Example: $415,000 ÷ ($400,000 × 2.5% = $10,000) = **42 sides** → ~23 seller sides, ~19 buyer sides, of which ~8 are investors (who often buy and sell repeatedly).

## 3. Convert closings to appointments

MREA's key insight: **appointments are the number you control.** Everything upstream (leads, touches, marketing) exists to create appointments. Everything downstream (contracts, closings) is a conversion ratio you improve with skill.

| Line | Formula | Starting assumption | Your number |
|---|---|---|---|
| M. Listing appointments → listings taken | industry 50–70% for referral/sphere, 25–40% for internet leads | 60% | ____% |
| N. Listings taken → closed | 80–90% | 85% | ____% |
| O. Listing appointments needed per year | J ÷ (M × N) | 23 ÷ 0.51 = **45** | ________ |
| P. Buyer consults → signed buyer agreements | 60–80% | 70% | ____% |
| Q. Signed buyers → closed | 60–75% | 65% | ____% |
| R. Buyer consults needed per year | K ÷ (P × Q) | 19 ÷ 0.455 = **42** | ________ |
| S. Total appointments per year | O + R | **87** | ________ |
| T. Appointments per week (48 working weeks) | S ÷ 48 | **~2 per week** | ________ |

Two appointments a week is the whole job. Every system in this repo exists to put two qualified appointments on the calendar every week and to serve them at a white-glove level so they refer.

## 4. Convert appointments to leads and database

| Line | Formula | Starting assumption | Your number |
|---|---|---|---|
| U. Lead → appointment conversion (blended) | sphere/referral 25–40%, web/social 3–8%, open house 5–10% | 12% blended | ____% |
| V. Leads needed per year | S ÷ U | 87 ÷ 0.12 = **725** | ________ |
| W. Leads per week | V ÷ 48 | **~15 per week** | ________ |

### Database math (MREA's two rules)

MREA gives two rules of thumb for a database that is touched consistently:

- **Met database on 33 Touch:** expect about **2 transactions per 12 contacts per year** (one repeat, one referral).
- **Haven't Met database on 12 Direct:** expect about **1 transaction per 50 contacts per year**.

| Line | Formula | Example | Your number |
|---|---|---|---|
| X. Sides you want from Met database | you choose (aim for 50%+ of I) | 22 | ________ |
| Y. Met contacts needed on 33 Touch | X × 6 | **132** (round up to 150) | ________ |
| Z. Sides you want from Haven't Met | you choose | 8 | ________ |
| AA. Haven't Met contacts needed on 12 Direct | Z × 50 | **400** | ________ |
| AB. Remaining sides from lead sources (web, social, open house, signs, investors) | I − X − Z | 12 | ________ |

So for this example: a **150-person Met list touched 33 times a year**, a **400-person Haven't Met list mailed monthly**, and **~15 new leads a week** from the site, social, open houses, and signs produce the 42 sides.

## 5. The daily numbers (what goes on the whiteboard)

From the example above, the activity that produces the result:

| Daily (5 days) | Weekly | Why |
|---|---|---|
| 10 database conversations (calls/texts) | 50 | 33 Touch phone touches + lead follow-up |
| 5 new contacts added to Command | 25 | database growth (every open house, DM, sign call) |
| 3 handwritten notes | 15 | MREA personal-touch multiplier |
| 1 piece of social content published | 5 | keeps the funnel warm without listings |
| 2 hours lead generation time-blocked | 10–15 | non-negotiable (see `time-blocking.md`) |
| | 2 appointments | the number that matters |

## 6. Quarterly review questions

1. Are we hitting **2 appointments per week**? If not, is it leads (volume) or conversion (skill/speed)?
2. Which source produced the most appointments per dollar and per hour? (see `10-SCORECARD`)
3. Is the Met database growing by 25/week? Is 33 Touch actually executing (check Command SmartPlan step completion)?
4. Are seller sides ≥ 50%? If not, shift lead gen toward seller sources (12 Direct, circle prospecting, home-value funnel).
5. Update the assumptions in the calculator with **actual** ratios from the last 90 days.
