# Opportunities Pipelines in Command

One Opportunity per deal. The stage is the truth about where the deal is. Stage changes drive SmartPlans, Zaps, social posts, and the scorecard, so **move the stage the same day it happens**.

## 1. Seller pipeline

| Stage | What must be true to enter | Owner moves it | What it triggers |
|---|---|---|---|
| `Cultivate` | Seller intent stated, no appointment yet | Zap or VA | `SP-Seller Nurture`; tag `Seller-Nurture` |
| `Appointment Set` | Listing consultation booked on calendar | VA | Pre-listing packet sent within 24h (`05-SELLER-SYSTEM/pre-listing-process.md`); CMA prep task |
| `Appointment Met` | Consultation happened | Charles | Same-day thank-you + follow-up task Day 2, Day 7 |
| `Listing Signed` | Listing agreement executed | Charles | Z-06: listing folder + intake form + `CB Listing Marketer`; vendor booking tasks; 14-day pre-launch timeline |
| `Coming Soon` | Photos done, MLS Coming Soon status (per MLS rules) | VA | Z-07: Coming Soon social sequence; 10 neighbor calls task; `SP-Seller Listing Launch` starts |
| `Active` | Live on MLS, syndication verified | VA | Z-07: Just Listed sequence, database email blast, agent-to-agent email, open house planning; Monday report task recurs (Z-08) |
| `Under Contract` | Executed contract | Charles | `SP-Seller Under Contract`; Z-07 Under Contract post; milestone tracker created (`SOP-07`) |
| `Closed` | Funded and recorded | VA | Z-09: `Past Client` tag, `SP-Past Client Program`, Just Sold sequence, review request Day 7, gift task; scorecard updated |

Lost at any stage → Status tag `Dead` or `Nurture`, Opportunity archived with a reason (Price / Chose another agent / Not selling / Timing). Reasons feed the quarterly review.

## 2. Buyer pipeline

| Stage | What must be true | Owner | Triggers |
|---|---|---|---|
| `Cultivate` | Buyer intent, no consult yet | Zap or VA | `SP-Buyer Nurture` |
| `Consult Set` | Buyer consultation booked | VA | Pre-consult packet (buyer guide, lender intro, process map) within 24h |
| `Consult Met` | Consultation happened | Charles | Needs Analysis entered in notes; `CB Buyer Concierge` prep summary saved |
| `Buyer Agreement Signed` | Buyer representation agreement executed; pre-approval on file | Charles | Search alerts set; showing itinerary process begins |
| `Showing` | Actively touring | VA | Night-before itinerary + same-evening recap tasks (`06-BUYER-SYSTEM/buyer-consultation.md`) |
| `Offer Written` | Offer submitted | Charles | Offer strategy memo saved; 24h follow-up task |
| `Under Contract` | Executed contract | Charles | `SP-Buyer Under Contract`; milestone tracker (`SOP-07`) |
| `Closed` | Funded and recorded | VA | Z-09: past client program, gift, review, anniversary date set |

## 3. Investor (Capital Partner) pipeline

One Opportunity per partner per deal. Deals themselves are tracked on the Deal Board sheet until a partner commits (`07-INVESTOR-SYSTEM/deal-sourcing-engine.md`).

| Stage | What must be true | Owner | Triggers |
|---|---|---|---|
| `Cultivate` | Capital partner intent, no criteria call yet | Zap or VA | `SP-Speed to Lead` with the sample Deal Memo attached; `Tier-3` |
| `Criteria Call` | Call booked | VA | `CB Investor Analyst` prep from any known info |
| `Partner Onboarded` | Capital Partner Profile complete, onboarding packet sent | VA | Tag `Capital-Partner`; tier tag set by Charles; `SP-Capital Partner Program`; docs request (proof of funds, buyer rep agreement) |
| `Deal Presented` | A Deal Memo was sent to this partner | Z-12 / VA | 48-hour window tasks: Charles call, 24h reminder text |
| `Deal Committed` | Partner replied "I'm in" in writing and Charles confirmed | Charles | Attorney and title engaged; EMD instructions; Deal Board row → `Funded` |
| `Acquisition Under Contract` | Purchase contract executed | Charles | `SP-Buyer Under Contract` (offsets adjusted); inspection walk with contractor; wire-confirmation call task |
| `Rehab` | Closed on the purchase | Charles | Project Tracker created; Z-15 Friday Project Update tasks; milestone texts |
| `Listed` | Finished flip live on MLS at the Maximum Exposure Standard | VA | Full seller system: Z-06, Z-07, Z-08 with reports sent to the partner |
| `Sold` | Resale funded | VA | Z-16: distribution statement task (5 business days), distribution call, review request, gift, `SP-Past Client Program` |
| `Repeat` | "Next deal" call held, capital availability date known | Charles | Stays on `SP-Capital Partner Program`; first look on the next matching deal; new Opportunity created at `Deal Presented` when it happens |

Partner passes on a deal → Opportunity back to `Partner Onboarded` with a note on why. Three consecutive passes → Charles re-tunes the profile or re-tiers.

## 4. Pipeline hygiene rules

1. Every Opportunity has a **next task with a due date**. No task = the VA creates a "Charles: decide next step" task.
2. Stage age limits: `Appointment Set`/`Consult Set` > 14 days without a met appointment → VA flags in huddle. `Active` listing at Day 14 and Day 30 → price/marketing review meeting (see `05-SELLER-SYSTEM/listing-launch-playbook.md`). `Deal Presented` > 48 hours without a reply → VA moves to Tier-2 alert per the journey. `Rehab` with no Friday update sent → escalate in Monday huddle.
3. Weekly pipeline review (Friday): count by stage, conversion between stages, expected GCI in `Under Contract`. These are scorecard lines.
4. Commission and expected close date are filled in at `Under Contract` so the scorecard's "pending GCI" is real.
