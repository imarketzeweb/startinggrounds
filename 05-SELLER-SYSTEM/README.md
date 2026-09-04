# 05 Seller System: Map

Read `/00-START-HERE/conventions.md` first. Every tag, stage, SmartPlan, and GPT name in this folder comes from that file.

## The promise

White glove: every seller knows what happens next, before they have to ask. In practice that means three things on every listing:

1. Maximum exposure. Every listing launches with pro photos, drone, video walkthrough, 3D tour, floor plan, single-property page, the 5-stage social sequence, and an email blast to the database. No exceptions, no "this one is too small."
2. A written update every Monday. Traffic, feedback, showings, market movement, next step. Sent whether the news is good or bad.
3. Showing feedback relayed within 24 hours. Verbatim plus what it means.

If a listing is not getting those three things, the system is broken and the fix goes to the top of the list.

## The five listing stages

`Coming Soon → Just Listed → Open House → Under Contract → Just Sold`

These stages drive the social sequence, the seller SmartPlans, and the marketing kit. They sit inside the Seller pipeline in Command:

`Cultivate → Appointment Set → Appointment Met → Listing Signed → Coming Soon → Active → Under Contract → Closed`

| Pipeline stage | Listing stage | SmartPlan running | Main doc |
|---|---|---|---|
| Cultivate | none | `SP-Speed to Lead` then `SP-Seller Nurture` | seller-journey-white-glove.md |
| Appointment Set / Met | none | `SP-Seller Nurture` (paused on Appointment Met) | pre-listing-process.md |
| Listing Signed | none | `SP-Seller Listing Launch` starts | pre-listing-process.md |
| Coming Soon | Coming Soon | `SP-Seller Listing Launch` | listing-launch-playbook.md |
| Active | Just Listed, Open House | `SP-Seller Listing Launch` | listing-launch-playbook.md, open-house-system.md |
| Under Contract | Under Contract | `SP-Seller Under Contract` | seller-journey-white-glove.md |
| Closed | Just Sold | `SP-Past Client Program` | seller-journey-white-glove.md |

## Who does what

| Role | Owns | Never does |
|---|---|---|
| Charles | Lead conversations, listing consultation, pricing, negotiation, offer presentation, every seller phone call that carries news, final approval of anything client-facing | Data entry, scheduling vendors, building posts, pulling report numbers |
| VA ([VA NAME]) | Intake form completion, vendor scheduling, Command data (tags, stages, Opportunities), running GPTs, QA before go-live, Monday report data pull, social scheduling, open house sign-in processing | Pricing advice, negotiation, sending anything Charles has not approved |
| Command SmartPlans | Timed emails and texts, task reminders to Charles and VA, tag changes, drips | Anything requiring judgment |
| Zapier | Moving form data into Command, posting alerts to Slack `#listings` and `#leads`, creating Drive folders, creating tasks | Client communication |
| ChatGPT (`CB Listing Marketer`, `CB Seller Concierge`) | First drafts: marketing kit, pricing talk track prep, Monday update narrative, feedback interpretation | Sending anything. Rule: ChatGPT drafts, a human approves, Command sends. |

## Files in this folder

| File | Use it when |
|---|---|
| `seller-journey-white-glove.md` | You want the whole seller experience, touch by touch, lead to home anniversary. Start here to understand the flow. |
| `pre-listing-process.md` | A seller lead has said "come look at the house." Intake call, Seller Intake Form, packet, CMA prep, consultation agenda, vendor prep, 14-day pre-launch. |
| `listing-launch-playbook.md` | The listing is signed. Maximum Exposure Standard, Day -14 to Day +14 timeline, QA checklist, Day 14 and Day 30 no-offer reviews. |
| `listing-marketing-kit-template.md` | You are running `CB Listing Marketer`. Defines every asset the GPT must return, in fixed order, with Fair Housing checklist. |
| `social-media-listing-templates.md` | The VA is building posts. Platform-by-platform templates for the 5 stages plus the weekly non-listing calendar. |
| `open-house-system.md` | A mega open house is on the calendar. 7-day promo, neighbor invites, sign-in, day-of, follow-up, how sign-ins become contacts. |
| `weekly-seller-report-template.md` | It is Monday. Data pull checklist, the report template, and the `CB Seller Concierge` prompt. |

## The minimum weekly rhythm for the seller side

| Day | Charles | VA |
|---|---|---|
| Monday | Approve and send every seller update by 12pm | Pull all report data by 10am, draft narrative via `CB Seller Concierge`, send to Charles for approval |
| Tuesday | Call every seller with a listing over 14 days old | Schedule next week's social for all active listings |
| Wednesday | Review Coming Soon pipeline, confirm launch dates | Vendor confirmations for upcoming launches |
| Thursday | Open house decisions for the weekend | Open house promo push, neighbor invites out |
| Friday | Nothing seller-specific unless a launch is live | Confirm showings, lockboxes, and sign status for weekend |
| Any day | Return showing feedback to the seller within 24h | Log feedback in the Opportunity notes the moment it arrives |

## Slack channels used in this folder

- `#listings`: every listing event (signed, coming soon, live, showing feedback, offer, under contract, milestones, closed). Zaps post here.
- `#leads`: seller leads arriving, Speed to Lead status.
- `#ops`: vendor issues, QA failures, anything blocking a launch.

## Drive folder per listing

`Listings/[YYYY-MM] [Street Address]/` with `01-Photos`, `02-Video`, `03-3D-FloorPlan`, `04-Marketing-Kit`, `05-Docs`. The VA creates it the day the listing is signed (or the Zap does). The Seller Intake Form and every GPT output go in `04-Marketing-Kit`.

## First listing quickstart (read in this order)

If this is the first time running the system on a real listing, do not read everything. Do this.

| Step | Read | Do | Owner |
|---|---|---|---|
| 1 | pre-listing-process.md section 1 and 2 | Run the intake call. Fill the Seller Intake Form completely | Charles, VA |
| 2 | pre-listing-process.md section 3 to 6 | Build the packet, pull the CMA, hold the consultation, sign | VA, Charles |
| 3 | pre-listing-process.md section 7 to 9 | Book every vendor the day it is signed. Set up Command | VA |
| 4 | listing-marketing-kit-template.md | Run `CB Listing Marketer` on Day -5. Fair Housing checklist. Charles approves | VA, Charles |
| 5 | listing-launch-playbook.md section 1 to 4 | Work the Day -14 to Day 0 timeline. Pass the QA checklist | VA |
| 6 | social-media-listing-templates.md section 3 | Schedule the Coming Soon and Just Listed posts | VA |
| 7 | open-house-system.md | Promote and run the first-weekend mega open house | Charles, VA |
| 8 | weekly-seller-report-template.md | First Monday update on Day +7. Every Monday after | VA, Charles |
| 9 | listing-launch-playbook.md section 5 | Day 14 and Day 30 reviews if no offers | Charles |
| 10 | seller-journey-white-glove.md phase 5 and 6 | Under contract milestones, closing, past client handoff | All |

After the first listing, hold a 30-minute retro in `#ops`: what took longer than planned, which vendor was late, which QA item was missed. Fix the doc, not the person.

## How the folder wires into Command

| Command object | What it drives in this folder |
|---|---|
| Contact tags `Seller`, `Past Client`, `Met`, `Haven't Met` | Who gets which SmartPlan and which 33 Touch or 12 Direct after closing |
| Status tags `New-Lead` → `Hot` → `Active` → `Under-Contract` → `Closed` | The VA flips these at each pipeline stage change |
| Source tags `Src-Website`, `Src-Social`, `Src-OpenHouse`, `Src-Sign` | Set once at creation. Sign QR scans and property page forms are `Src-Website`, open house sign-ins are `Src-OpenHouse`, DM replies are `Src-Social` |
| Seller pipeline Opportunity | One per listing. Holds the DocuSign room, notes (lockbox codes, decision makers, showing restrictions), feedback log, offer log, and related open house contacts |
| `SP-Speed to Lead` | First 10 days for any web or social seller lead |
| `SP-Seller Nurture` | Cultivate through Appointment Met, and anyone who did not sign |
| `SP-Seller Listing Launch` | Listing Signed through Active: seller emails, photo day text, database blast, VA and Charles tasks |
| `SP-Seller Under Contract` | Contract day to closing: milestone emails and tasks |
| `SP-Past Client Program` | Starts the day of closing, never stops. Day 7 review, Day 30, Day 90, annual anniversary |
| `SP-8x8 New Contact` | Every open house sign-in and every new social DM contact |
| Command Designs | Email headers, seller summary, Just Listed email |
| Command Sites | Listing page auto-built from MLS, verified Day +1 |
| Command Tasks | The VA's board. Every timeline row in this folder becomes a task with a due date |

## Zaps referenced in this folder

Verify each trigger and action exists in the Command Zapier integration before building. Names follow `Z-##  Trigger → Outcome`.

| Zap | Trigger | Outcome |
|---|---|---|
| `Z-01 Website Form → Command Contact + Speed to Lead` | charlesbrewer.guru form submit | Contact created with tags, `SP-Speed to Lead` started |
| `Z-02 New Seller Lead → #leads` | New contact with `Seller` and `New-Lead` | Slack alert with name, source, message |
| `Z-03 Opportunity Stage Change → #listings` | Seller pipeline stage change | Slack alert with address, new stage, date |
| `Z-04 Stage = Appointment Set → Create Drive Folder` | Stage moves to Appointment Set | Drive folder `Listings/[YYYY-MM] [Street Address]/` with five subfolders |
| `Z-05 Open House Form → Command Contact + Src-OpenHouse + SP-8x8 New Contact` | Open house sign-in form submit | Contact created, tagged, 8x8 started |

## Glossary

| Term | Meaning here |
|---|---|
| Maximum Exposure Standard | The fixed list of media and channels every listing gets. listing-launch-playbook.md section 1 |
| Seller Intake Form | The single input to `CB Listing Marketer`. pre-listing-process.md section 2 |
| Marketing kit | The fixed-order output of `CB Listing Marketer`. listing-marketing-kit-template.md |
| 5-stage sequence | Coming Soon → Just Listed → Open House → Under Contract → Just Sold, on every platform |
| Mega open house | A promoted, neighbor-invited, sign-in-required open house. open-house-system.md |
| Monday update | The written weekly seller report. weekly-seller-report-template.md |
| Day 14 / Day 30 review | Mandatory price and marketing checkpoints when no offer has arrived |
| 10 neighbor calls | MREA "just listed" calls Charles makes on launch day |
| Circle prospecting | Calls to 25 to 50 more neighbors during launch week |
| Reverse prospecting | MLS tool that shows agents whose buyers' saved searches match the listing |
| Syndication check | Day +1 verification that Zillow, Realtor.com, Redfin, and Homes.com all show the full listing |
| QA checklist | The Day -1 go-live gate the VA runs. Nothing goes Active until it passes |
| 8x8 | Eight touches in eight weeks for a new contact, then handoff to 33 Touch or 12 Direct |
| 33 Touch | The annual touch plan for contacts tagged `Met` |
| 12 Direct | The annual mail or email plan for contacts tagged `Haven't Met` |

## What is not in this folder

- Buyer side: see 06-BUYER-SYSTEM (or the folder named for buyers)
- Database and touch plans (8x8, 33 Touch, 12 Direct calendars): see `04-AUTOMATIONS/command-smartplans/` (database design in `02-COMMAND-CRM/`)
- GPT instructions and system prompts: see 03-CHATGPT
- Zap build specs: see `04-AUTOMATIONS/zaps/`
- YouTube: parked, see 11-YOUTUBE-LATER
