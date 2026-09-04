# 90-Day Implementation Plan

Build in the order that produces appointments soonest. Each week has an owner and a "done when". Do not skip ahead: week 1 and 2 are the foundation everything else writes into.

## Phase 1 – Foundation (Weeks 1–2): Command, database, ChatGPT

| Week | Task | Owner | Done when | Reference |
|---|---|---|---|---|
| 1 | Confirm `00-START-HERE/assumptions-and-decisions.md`; fill in `[MARKET]`, phone, email, booking link across docs | Charles | Decisions list signed off | `assumptions-and-decisions.md` |
| 1 | Run the economic model calculator with real numbers; print it | Charles | Whiteboard numbers posted | `10-SCORECARD/economic-model-calculator.html` |
| 1 | Command one-time setup (tags, fields, pipelines, filters) | VA | Checklist items 1–4 done | `02-COMMAND-CRM/command-setup-checklist.md` |
| 1 | Create the ChatGPT Project and the six GPTs; upload knowledge files; fill in the brand voice sheet | Charles (voice sheet), VA (setup) | All six GPTs answer a test prompt correctly | `03-CHATGPT/setup-guide.md` |
| 1 | Import and tag the database; Charles marks Met / Haven't Met | Charles + VA | Count verified, zero "missing facts" | `02-COMMAND-CRM/database-architecture.md` §6 |
| 2 | Build the 11 SmartPlans (VA drafts from the files, Charles approves copy) | VA + Charles | All plans live, test contact ran through each | `04-AUTOMATIONS/command-smartplans/` |
| 2 | Enroll everyone: 8x8 / 33 Touch / 12 Direct | VA | Enrollment counts match database | same |
| 2 | Send the reconnect text to the Met list; start the daily lead-gen block | Charles | 50 conversations logged in week 2 | `SP-33-Touch-Met.md`, `01-MREA-MODELS/time-blocking.md` |
| 2 | Scorecard sheet created; first Friday review held | VA + Charles | Week 2 row filled | `10-SCORECARD/kpi-scorecard.md` |

## Phase 2 – Capture (Weeks 3–4): website funnel and speed to lead

| Week | Task | Owner | Done when | Reference |
|---|---|---|---|---|
| 3 | Sell / Buy / Invest landing pages live on charlesbrewer.guru with forms posting to Zapier | VA (+ web help if needed) | Test submission reaches Command with correct tags in < 1 minute | `08-WEBSITE-FUNNEL/` |
| 3 | Build Z-01, Z-02, Z-14 (form → Command → alert → draft → escalation) | VA | 5-minute human response verified on 3 test leads | `04-AUTOMATIONS/zaps/` |
| 3 | Lead magnets drafted with the GPTs and designed in Canva (Seller Guide, Buyer Guide, Investor Deal Alerts signup) | VA | PDFs attached to thank-you emails | `08-WEBSITE-FUNNEL/lead-magnets.md` |
| 4 | Booking link limited to appointment blocks; pre-listing and pre-consult packets ready | VA | Packets send from Command in one click | `05-SELLER-SYSTEM/pre-listing-process.md`, `06-BUYER-SYSTEM/` |
| 4 | Social: link-in-bio, UTM scheme, Canva/Command Designs templates for the 5 listing stages and the weekly content calendar | VA | Two weeks of non-listing posts scheduled | `05-SELLER-SYSTEM/social-media-listing-templates.md` |
| 4 | Google Business Profile complete; first review requests sent to 10 past clients | VA + Charles | 3 new reviews | `08-WEBSITE-FUNNEL/charlesbrewer-guru-funnel.md` |

## Phase 3 – Listings (Weeks 5–8): the seller machine

| Week | Task | Owner | Done when | Reference |
|---|---|---|---|---|
| 5 | Vendor bench set: photographer w/ drone, 3D tour, floor plan, stager, cleaner, handyman, sign company, printer/mailing house | VA | Standing orders and prices in a sheet | `05-SELLER-SYSTEM/pre-listing-process.md` |
| 5 | Listing intake form (Google Form/Typeform) live; Z-06 built (intake → folder → Opportunity → `CB Listing Marketer` kit → approval) | VA | Test listing produces a full kit in a Google Doc | `04-AUTOMATIONS/zaps/Z-06-*.md` |
| 6 | Z-07 (stage → social + SmartPlan), Z-08 (Monday seller reports), Z-09 (closed → past client) | VA | Test opportunity moved through all stages triggers everything | `04-AUTOMATIONS/zaps/` |
| 6 | Open house system: sign-in app, neighbor mailer template, Z-04 | VA | First mega open house run on a listing (or a colleague's) | `05-SELLER-SYSTEM/open-house-system.md` |
| 7 | First listing launched at the full Maximum Exposure Standard; VA runs the QA checklist | Charles + VA | Day 0 checklist 100%, syndication verified in 24h, 5-stage social scheduled | `05-SELLER-SYSTEM/listing-launch-playbook.md` |
| 8 | First Monday seller report cycle; Day 14 review meeting held | VA + Charles | Report sent by 3pm with GPT-drafted narrative | `05-SELLER-SYSTEM/weekly-seller-report-template.md` |
| 8 | 12 Direct farm selected and first mailer sent | Charles + VA | 400 addresses in Command with `Haven't Met` + `12-Direct` | `01-MREA-MODELS/lead-generation-model.md` §4 |

## Phase 4 – Buyers, investors, and rhythm (Weeks 9–12)

| Week | Task | Owner | Done when | Reference |
|---|---|---|---|---|
| 9 | Buyer consult script and Needs Analysis in use; itinerary + recap templates; Z-03 (social leads) | Charles + VA | First buyer runs through the full journey | `06-BUYER-SYSTEM/` |
| 10 | Capital Partner Profile fields in Command, Deal Board sheet live, `CB Investor Analyst` tested on 3 real properties, attorney meeting held (`structures-and-compliance.md`), first Deal Memo produced and sent to Tier-1 partners (Z-12) | Charles + VA | One Deal Memo approved and sent; 3+ partners onboarded | `07-INVESTOR-SYSTEM/` |
| 11 | Z-10 (Friday scorecard summary), Z-11 (reviews), Z-13 (missed calls); VA SOPs 01–10 recorded as Looms | VA | Every SOP has a Loom and a Done-when | `09-VA-PLAYBOOK/sops/` |
| 12 | Quarterly review: re-run the economic model with 90 days of actuals; decide next hire; pick 3 priorities for next quarter; YouTube go/no-go check | Charles | Updated calculator, written priorities | `01-MREA-MODELS/`, `11-YOUTUBE-LATER/` |

## Definition of "the system is running"

All true for 4 consecutive weeks:
1. Every lead in Command within 5 minutes, human reply within 5 minutes (8am–8pm).
2. 2 appointments per week.
3. Every listing launched at the Maximum Exposure Standard on Day 0.
4. Monday seller reports out by 3pm.
5. 33 Touch / 12 Direct / 8x8 steps 100% on time.
6. Friday scorecard reviewed with the GPT summary.
