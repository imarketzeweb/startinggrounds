# 03 ChatGPT Layer: Map

Read `/00-START-HERE/conventions.md` first. Every GPT name, tag, pipeline stage, and SmartPlan name in this folder comes from that file.

## What this layer does

ChatGPT is the thinking and writing engine of the business. It does not touch a client, a contact record, or a send button. Its job is to take raw inputs (a lead payload, an intake form, a set of weekly numbers, a deal's financials, a Loom transcript) and hand back a finished first draft in Charles's voice, fast enough that the human step is a two-minute review instead of a thirty-minute writing session.

The rule that governs everything in this folder:

**ChatGPT drafts, a human approves, Command sends.**

Nothing produced by any GPT goes to a client, a lead, a vendor, or the public without Charles or the VA reading it first. Every GPT is instructed to close its output with a "DRAFT for human review" footer so that nobody can mistake a draft for a finished piece.

## The six GPTs

| # | GPT | What it does | Primary user |
|---|---|---|---|
| 1 | `CB Lead Responder` | Reads a raw lead payload, assigns type (Buyer / Seller / Investor / Sphere) and temperature (A / B / C), suggests Command tags and SmartPlan, and drafts the first SMS, email, and call opener | VA (first pass), Charles (A leads) |
| 2 | `CB Listing Marketer` | Turns a completed Seller Intake Form into the full Listing Marketing Kit: MLS remarks, video scripts, 5-stage social captions, emails, GBP and Nextdoor posts, neighbor scripts, single-property page copy | VA |
| 3 | `CB Seller Concierge` | Listing consultation prep from CMA numbers, pricing talk track, objection handling, Monday seller report narrative, feedback interpretation, Day 14 / Day 30 price-review memo, under-contract milestone explanations, post-closing notes | VA (reports), Charles (pricing and objections) |
| 4 | `CB Buyer Concierge` | Buyer consult prep from the Buyer Needs Analysis, showing itinerary builder, same-evening recap drafter, offer strategy memo, milestone explainer texts, buyer objection handling | VA (itineraries, recaps), Charles (offer strategy) |
| 5 | `CB Investor Analyst` | Underwrites fix and flip deals (ARV comps, rehab, 70% rule MAO, holding and selling costs, profit, ROI, sensitivity), rental hold analysis as backup exit, the Deal Memo package for capital partners, the Friday Project Update, the 48-hour Deal Alert email, and partner matching from Capital Partner Profiles | Charles (underwriting, memos, matching), VA (Project Update and Deal Alert assembly) |
| 6 | `CB Ops Manager` | VA SOPs in a fixed format, Loom transcript to SOP, weekly scorecard summary, MREA time-block calendars, job descriptions for next hires, Friday review | VA (SOPs, scorecard), Charles (hiring, time blocks, Friday review) |

## Input, output, and where it goes

| GPT | Input | Output | Used by | Feeds into |
|---|---|---|---|---|
| `CB Lead Responder` | Raw lead payload from Zapier or Slack `#leads` (name, email, phone, source, page, message, property, timeline) | JSON block (type, temperature, suggested_tags, suggested_smartplan, summary) + SMS + email + call opener + 3 qualifying questions | VA, Charles | Command: tags, `SP-Speed to Lead`, Opportunity in Cultivate. Slack `#leads` thread. |
| `CB Listing Marketer` | Completed Seller Intake Form (from `05-SELLER-SYSTEM/pre-listing-process.md`) | Full Listing Marketing Kit in fixed order (see `05-SELLER-SYSTEM/listing-marketing-kit-template.md`) | VA | Drive `04-Marketing-Kit`, MLS, Command Designs, Canva, CapCut, social scheduler, Command email Campaign, single-property page on charlesbrewer.guru |
| `CB Seller Concierge` | CMA numbers, Zillow/competing agent context, weekly showing and traffic data, showing feedback verbatim, contract milestones | Talk tracks, Monday report narrative, price-review memo, milestone texts, anniversary notes | VA, Charles | Command: Monday email to seller, Opportunity notes, `SP-Seller Under Contract` messages, `SP-Past Client Program` |
| `CB Buyer Concierge` | Buyer Needs Analysis, list of addresses and times, showing notes, comps and competition data | Consult agenda, itinerary, evening recap, offer strategy memo, milestone texts | VA, Charles | Command: itinerary email night before, recap same evening, `SP-Buyer Under Contract`, Opportunity notes |
| `CB Investor Analyst` | Deal Analysis inputs (from `07-INVESTOR-SYSTEM/deal-analysis-template.md`), weekly project numbers, Capital Partner Profiles | Deal Snapshot, Deal Memo package, Friday Project Update, 48-hour Deal Alert email, partner match table | Charles, VA | Command: `SP-Investor Deal Alerts` email, Investor pipeline (Deal Presented, Deal Committed, Rehab, Listed), partner Opportunity notes |
| `CB Ops Manager` | Loom transcript or task description, weekly KPI numbers (from `10-SCORECARD/kpi-scorecard.md`), hiring need, calendar constraints | SOP, scorecard summary, time-block calendar, job description, Friday review | VA, Charles | Command Tasks, Slack `#ops`, Drive SOP folder, Friday review doc |

## Who uses what, day to day

**Charles** uses ChatGPT for judgment-heavy work he still owns: pricing conversations, offer strategy, deal analysis, hiring, time blocking, the Friday review. He also reviews and approves every client-facing draft.

**The VA** uses ChatGPT for volume work: qualifying and drafting the first reply to every lead, running the marketing kit on every listing, turning Monday numbers into the seller report narrative, building showing itineraries and recaps, assembling the deal alert email, and writing SOPs from Loom recordings. The VA sends nothing without approval unless the SOP for that task explicitly says the VA approves it.

## Files in this folder

| File | Use it when |
|---|---|
| `setup-guide.md` | You are setting up the Project, the six GPTs, sharing with the VA, scheduled Tasks, the brand voice sheet, privacy rules, and the monthly review |
| `gpts/cb-lead-responder.md` | Copy-paste instructions for `CB Lead Responder` |
| `gpts/cb-listing-marketer.md` | Copy-paste instructions for `CB Listing Marketer` |
| `gpts/cb-seller-concierge.md` | Copy-paste instructions for `CB Seller Concierge` |
| `gpts/cb-buyer-concierge.md` | Copy-paste instructions for `CB Buyer Concierge` |
| `gpts/cb-investor-analyst.md` | Copy-paste instructions for `CB Investor Analyst` |
| `gpts/cb-ops-manager.md` | Copy-paste instructions for `CB Ops Manager` |
| `prompt-library.md` | 40+ ready prompts grouped by lead gen, seller, buyer, investor, social, ops, and Command |

## The human-approval rule, in practice

1. Every GPT output ends with `DRAFT for human review. Not sent.`
2. The VA pastes the draft into Command (email, text, SmartPlan step, Opportunity note) or the social scheduler as a draft, never as a send.
3. Charles approves in Slack (`#leads`, `#listings`, `#ops`) with a thumbs-up or edits, or the SOP grants the VA approval authority for that specific task type (example: showing itineraries, standard milestone texts).
4. Only after approval does the VA click send or schedule.
5. Anything involving price, negotiation, legal terms, or bad news goes to Charles every time. No exceptions.

## Investor model note

Charles sources fix and flip deals; capital partners fund them. Charles brings the deal, the partner brings the capital, Charles runs the project white glove and lists the finished flip under the Maximum Exposure Standard. `CB Investor Analyst` is built around that. The investor pipeline used in `07-INVESTOR-SYSTEM` and by that GPT is `Cultivate → Criteria Call → Partner Onboarded → Deal Presented → Deal Committed → Acquisition Under Contract → Rehab → Listed → Sold → Repeat`. Every investor output ends with the estimates disclaimer and "structure and terms subject to attorney-drafted agreement."

## What the GPTs never do

- Fabricate a fact about a property, a market, a rate, or a client. If the input does not contain it, the GPT asks or flags it.
- Write anything that describes people rather than property (Fair Housing). See the rules in each GPT file.
- Give legal, tax, or lending advice. They point to the attorney, CPA, or lender.
- Send, post, schedule, or update a record. That is Command, Zapier, and a human.
