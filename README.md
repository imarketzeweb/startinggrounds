# Charles Brewer Real Estate – Operating System

A complete, automation-first business system for a Keller Williams agent built on Gary Keller's **The Millionaire Real Estate Agent** (MREA), run by Charles plus one Virtual Assistant, with **KW Command** as the system of record, **Zapier** as the glue, and **six ChatGPT custom GPTs** doing every first draft.

> The rule that keeps it white glove: **ChatGPT drafts, a human approves, Command sends.**

## Read in this order

1. `00-START-HERE/conventions.md` – the shared vocabulary (tags, stages, plan names, GPT names, tools). Everything else uses it.
2. `00-START-HERE/operating-system-overview.md` – the whole business on one page.
3. `00-START-HERE/90-day-implementation-plan.md` – what to build, in what order, with owners.
4. `00-START-HERE/assumptions-and-decisions.md` – confirm or change the assumptions before building.

## Map

| Folder | What it is | Primary user |
|---|---|---|
| `01-MREA-MODELS` | Economic, Lead Generation, Budget, Organizational models and Time Blocking, filled in for this business | Charles |
| `02-COMMAND-CRM` | Database architecture (tags, fields, filters), the three Opportunity pipelines, one-time setup checklist | VA |
| `03-CHATGPT` | Setup guide, the six GPT instruction sets (copy-paste), and a 40+ prompt library | Charles + VA |
| `04-AUTOMATIONS` | Automation map, 14 Zapier specs (Z-01..Z-14), and step-by-step copy for all 11 Command SmartPlans (8x8, 33 Touch, 12 Direct, and the rest) | VA |
| `05-SELLER-SYSTEM` | Seller white-glove journey, pre-listing SOP and intake form, **Listing Launch Playbook (Maximum Exposure Standard)**, listing marketing kit template, social templates for the 5 listing stages, open house system, Monday seller report | Charles + VA |
| `06-BUYER-SYSTEM` | Buyer journey, consultation script and needs analysis, itineraries, recaps, offer strategy | Charles + VA |
| `07-INVESTOR-SYSTEM` | Investor journey, buy box, deal alerts, underwriting template | Charles |
| `08-WEBSITE-FUNNEL` | charlesbrewer.guru funnel architecture, landing page copy, lead magnets, UTM and link-in-bio scheme | VA |
| `09-VA-PLAYBOOK` | VA role charter, daily/weekly/monthly checklists, 10 SOPs | VA |
| `10-SCORECARD` | KPI scorecard definition, CSV template for the Google Sheet, and the interactive `economic-model-calculator.html` | Charles + VA |
| `11-YOUTUBE-LATER` | Parked YouTube roadmap and what to capture now | Charles |

## The stack

KW Command (CRM, SmartPlans, Opportunities, Designs) · ChatGPT (six custom GPTs) · Zapier · charlesbrewer.guru · Canva/Command Designs · CapCut · Matterport or Zillow 3D Home · Calendly · Google Workspace · Slack or WhatsApp · Loom

## How ChatGPT fits

Create one ChatGPT Project ("Charles Brewer Real Estate OS"), upload the files this repo names in `03-CHATGPT/setup-guide.md` as knowledge, and create the six GPTs from `03-CHATGPT/gpts/`. The VA uses them daily; Charles approves outputs in two 20-minute windows a day.

| GPT | Job |
|---|---|
| CB Lead Responder | Qualifies every new lead (A/B/C, Buyer/Seller/Investor) and drafts the text, email, and call opener |
| CB Listing Marketer | Turns the Seller Intake Form into the full marketing kit: MLS remarks, video scripts, 5-stage social captions, emails, property page copy |
| CB Seller Concierge | Pre-listing prep, pricing talk tracks, the Monday seller report narrative, milestone messages |
| CB Buyer Concierge | Consult prep, showing itineraries, evening recaps, offer strategy memos |
| CB Investor Analyst | Underwrites deals, produces the Deal Snapshot, writes the biweekly deal alert |
| CB Ops Manager | Writes SOPs, the Friday scorecard summary, time blocks, job descriptions |

## Getting started this week

1. Open `10-SCORECARD/economic-model-calculator.html` in a browser and enter your real numbers.
2. Hand `02-COMMAND-CRM/command-setup-checklist.md` to your VA.
3. Follow `03-CHATGPT/setup-guide.md` to create the Project and GPTs.
4. Start the daily lead generation block from `01-MREA-MODELS/time-blocking.md` tomorrow morning.
