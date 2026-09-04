# Buyer Journey: White Glove, Touch by Touch

Read `/00-START-HERE/conventions.md` first. Stages, SmartPlans, tags, and GPT names below are exact.

The standard: every buyer knows what happens next, before they have to ask. This document lists every touch from first lead to the home anniversary, who sends it, and where it lives in Command.

## How to read this document

- "Owner" is who is responsible for the touch going out. `Command` means a SmartPlan sends it automatically. `Charles` or `VA` means a human sends it (usually from a `CB Buyer Concierge` draft).
- "Stage" is the Buyer pipeline stage in Command Opportunities.
- Every human touch gets logged in the Command contact timeline the same day. If it is not in Command, it did not happen.
- Rule: ChatGPT drafts, a human approves, Command sends.

## Phase 1: Lead to Consult (stage: Cultivate, then Consult Set)

Trigger: a new contact enters Command with tag `Buyer` + a `Src-*` tag + `New-Lead`. Zapier (`Z-01 Website Form → Command Contact + Speed to Lead`) or the VA adds `SP-Speed to Lead` and posts to Slack `#leads`.

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 1 | 0 min | Instant acknowledgment: "Got it, Charles or [VA NAME] will reach out in the next few minutes." | Text + email | Command (`SP-Speed to Lead`) | Automation only acknowledges. |
| 2 | Under 5 min (8am to 8pm) | Human reply. Call first, then text if no answer. Draft via `CB Lead Responder`, which also assigns `A`/`B`/`C`. | Call, then text | Charles; VA if Charles is unavailable | Outside 8pm to 8am: first thing next morning. Log the attempt in Command. |
| 3 | Same day | Consult booking link with two suggested times. | Text + email | Charles or VA | `[CALENDLY LINK]`. Offer video or in-office at `[BROKERAGE OFFICE]`. |
| 4 | Day 1 | Value email: "3 things every [MARKET] buyer should know right now" + buyer guide link. | Email | Command (`SP-Speed to Lead`) | |
| 5 | Day 2 | Second call attempt if no consult booked. | Call | Charles or VA | Voicemail script in `CB Lead Responder`. |
| 6 | Day 3 | Text: short market note plus one question ("Are you looking in the next 30 days or a bit later?"). | Text | Command task, VA sends | Answer sets `A`/`B`/`C`. |
| 7 | Day 5 | Email: "How the white glove buyer process works" (process map graphic). | Email | Command (`SP-Speed to Lead`) | |
| 8 | Day 7 | Third call attempt. | Call | Charles | |
| 9 | Day 10 | Break-up text: "I will stop reaching out for now. When you are ready, I am one text away." | Text | Command (`SP-Speed to Lead`) | Plan ends. If no consult set, VA changes status to `Nurture` and starts `SP-Buyer Nurture`. |

Exit rule from `SP-Speed to Lead`: the moment a consult is booked, the VA moves the Opportunity to `Consult Set`, stops `SP-Speed to Lead`, sets status `Hot`, and does not start `SP-Buyer Nurture`.

### `SP-Buyer Nurture` (for `B` and `C` buyers with no consult set)

Adds tag `Buyer-Nurture`. Runs until a consult is set or the contact goes `Dead`.

| Cadence | Touch | Owner |
|---|---|---|
| Every 2 weeks | Email: new-listings roundup for their stated area, or a short "what changed in [MARKET] this month" note | Command |
| Monthly | Personal text from Charles with one real question (rates, timeline, neighborhood) | Command task, Charles sends |
| Quarterly | Call from Charles | Command task |
| Ongoing | Every reply from the buyer resets the clock: VA reviews, Charles calls within 24 hours | VA + Charles |

## Phase 2: Consult Set to Consult Met

Trigger: Calendly booking. Zapier (`Z-02 Calendly Consult Booked → Command Stage + Slack`) moves the Opportunity to `Consult Set` and alerts `#leads`.

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 10 | Within 1 hour of booking | Confirmation text from Charles: "Looking forward to it. [VA NAME] is sending a short packet so we can make the most of our time." | Text | Charles | |
| 11 | Within 4 hours of booking | Pre-consult packet email | Email | VA | Contents below. |
| 12 | 24 hours before | Reminder text + ask to complete the short online Buyer Needs Analysis pre-form (5 questions) | Text | Command task, VA sends | Pre-form answers go to the VA, who runs `CB Buyer Concierge` for a consult prep brief. |
| 13 | 2 hours before | Charles reads the consult prep brief: lead source, temperature, pre-form answers, suggested questions, likely objections | Internal | VA drafts, Charles reads | |
| 14 | Consult | Buyer consultation (agenda below, script in buyer-consultation.md) | In person or video | Charles | |

### Pre-consult packet (email, sent by VA)

1. `[MARKET] Home Buyer's Guide` (PDF, see 08-WEBSITE-FUNNEL/lead-magnets.md).
2. Lender introduction: name, phone, email, and one line on why we work with them. Two lenders if the buyer prefers a choice. Note that the buyer may use any lender.
3. Buyer process map: one-page graphic from consult to keys (Command Designs or Canva).
4. What to bring or have handy: rough budget range, any pre-approval letter, list of must-haves, questions.
5. Link to the 5-question pre-form.
6. Charles bio and reviews link.

### Buyer consultation agenda (MREA consultative style, 60 to 75 minutes)

| Minutes | Block | Purpose |
|---|---|---|
| 0 to 5 | Welcome and agenda | Set the frame: "My job today is to understand what you want, show you how the process works, and decide together whether we are a fit." |
| 5 to 25 | Needs analysis | Timeline, motivation, must-haves, nice-to-haves, deal breakers, areas, payment comfort, decision makers, past experience. Fill the Buyer Needs Analysis form. |
| 25 to 35 | Agency and buyer agreement | Explain representation, how Charles is compensated, what the buyer agreement covers, term and exclusivity. Sign via DocuSign in Command Opportunities. |
| 35 to 45 | Financing | Where they stand, lender handoff, pre-approval versus pre-qualification, cash to close, payment comfort versus approval amount. |
| 45 to 55 | Process | The process map, timelines in `[MARKET]`, what happens at each stage, how Charles communicates (itinerary night before, recap same evening, milestone touches). |
| 55 to 65 | Showing plan | Search setup in Command, first showing block on the calendar, how to react to a listing they see online. |
| 65 to 75 | Next steps and questions | Recap in writing within 2 hours. |

After the consult the VA moves the Opportunity to `Consult Met`, changes `Haven't Met` to `Met`, and enters the Buyer Needs Analysis into the Command contact notes.

## Phase 3: Consult Met to Buyer Agreement Signed

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 15 | Within 2 hours | Written recap: what we heard, the plan, next 3 steps, buyer agreement for signature if not signed in the room | Email | VA drafts via `CB Buyer Concierge`, Charles approves | |
| 16 | Same day | Lender pre-approval handoff: warm email intro to lender copying the buyer, with the buyer's stated timeline and price range | Email | Charles | Lender commits to a 24-hour response. VA tracks in Command task "Pre-approval received?". |
| 17 | Same day | Search set up in Command with the buyer's criteria; buyer receives the first listing alert email | Command | VA | Criteria from the Buyer Needs Analysis. |
| 18 | Day 2 | Text: "Did you hear from [lender]?" | Text | VA | Escalate to Charles if no lender contact by day 2. |
| 19 | Day 3 | If agreement unsigned: call from Charles to answer questions | Call | Charles | |
| 20 | Pre-approval received | Text from Charles: congratulations and "we are cleared to tour, here is my showing link" | Text | Charles | VA moves Opportunity to `Buyer Agreement Signed`, status `Active`, once signed. |

## Phase 4: Showing (stage: Showing)

Standard: itinerary the night before, recap the same evening. Every showing day.

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 21 | Day showings are requested | Confirm showing block; VA books appointments in ShowingTime or per listing instructions | Text | VA | |
| 22 | Night before, by 7pm | Showing itinerary: order, addresses, times, price, key notes per home, meeting point, parking, what to bring | Email + text link | VA drafts via `CB Buyer Concierge`, Charles approves | Template in buyer-consultation.md. |
| 23 | Morning of | Text: "See you at [time] at [first address]. Coffee is on me." | Text | Charles | |
| 24 | During | Charles captures buyer reactions per home (voice note or the itinerary scoring column) | Internal | Charles | |
| 25 | Same evening, by 8pm | Showing recap: each home with their rating, pros and cons in their words, what we learned about their criteria, next step | Email | VA drafts via `CB Buyer Concierge`, Charles approves | Template in buyer-consultation.md. |
| 26 | Next day | Refine search criteria in Command based on recap | Command | VA | |
| 27 | Weekly (Friday) | Weekend availability and any new listings worth a look | Text | VA | |
| 28 | Every 14 days with no offer | Charles call: recalibrate criteria, price, or areas; check on lender and rate lock | Call | Charles | Command task. |

## Phase 5: Offer Written (stage: Offer Written)

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 29 | Buyer says "this one" | Offer strategy call, same day. Worksheet in buyer-consultation.md: list price, DOM, comps, competition, terms levers. | Call or video | Charles | VA pulls comps and listing data into the worksheet first; `CB Buyer Concierge` drafts strategy notes. |
| 30 | Before writing | Lender call: confirm approval on this address, closing timeline, appraisal gap capacity | Call | Charles | |
| 31 | Offer drafted | Offer summary email in plain English: price, EMD, inspection period, appraisal terms, closing date, concessions, what each means | Email | VA drafts, Charles approves | Then DocuSign via Command Opportunities. |
| 32 | Offer submitted | Text: "Submitted at [time]. Seller has until [deadline]. I will text you the moment I hear anything." | Text | Charles | VA moves Opportunity to `Offer Written`. |
| 33 | Waiting | Every 12 hours with no news: a one-line status text | Text | Charles | Silence is the enemy of white glove. |
| 34 | Counter received | Call within 15 minutes of receipt; written summary of counter terms after the call | Call + email | Charles | |
| 35 | Offer rejected or lost | Call from Charles same day; recap what we learned; back to Showing | Call | Charles | VA moves Opportunity back to `Showing`. |

## Phase 6: Under Contract (stage: Under Contract, `SP-Buyer Under Contract`)

Trigger: accepted offer. VA moves Opportunity to `Under Contract`, status `Under-Contract`, starts `SP-Buyer Under Contract`, creates the Drive folder, and fills the milestone tracker with real dates from the contract.

| # | When | Milestone touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 36 | Acceptance, within 1 hour | Call from Charles: congratulations plus the three things that happen next | Call | Charles | |
| 37 | Acceptance, same day | "You are under contract" email: full milestone calendar with dates, who does what, and contact list (lender, title, inspector, insurance) | Email | Command (`SP-Buyer Under Contract`), VA fills dates | |
| 38 | Day 1 | EMD: where, how, deadline, wire fraud warning ("we will never change wiring instructions by email; call to verify") | Text + email | VA | Confirm receipt to buyer once title confirms. |
| 39 | Day 1 | Inspection: options for inspectors, what an inspection covers, how to book, encourage attending the last 30 minutes | Email | VA | Book within 48 hours. |
| 40 | Day 2 | Lender: confirm application is complete, rate lock decision, list of documents outstanding | Text | VA checks with lender, Charles texts buyer | |
| 41 | Inspection day | Text before: "Inspector arrives at [time]." Text after: "Report expected by [time tomorrow]." | Text | VA | |
| 42 | Report received | Call from Charles to walk the report; then written inspection response strategy (ask, credit, or accept) | Call + email | Charles | `CB Buyer Concierge` drafts the summary of findings in plain English. Charles decides strategy. |
| 43 | Inspection resolved | Email: what was agreed, next milestone (appraisal) | Email | VA | |
| 44 | Appraisal ordered | Text: "Appraisal ordered, typically back in [X] days. Nothing needed from you." | Text | VA | |
| 45 | Appraisal received | Call from Charles with the result and what it means; email confirming | Call + email | Charles | Low appraisal: strategy call same day. |
| 46 | Day 10 to 14 | Insurance: reminder to bind homeowners insurance, two agent referrals, deadline the lender needs it by | Email | Command (`SP-Buyer Under Contract`) | |
| 47 | Day 14 | Halfway check-in call from Charles | Call | Charles | Command task. |
| 48 | 10 days before closing | Utilities: transfer list with phone numbers and the date to set service (electric, gas, water, trash, internet) | Email | Command (`SP-Buyer Under Contract`) | VA updates the list per `[MARKET]`. |
| 49 | 7 days before closing | Clear to close status from lender; closing logistics email: date, time, location, what to bring (ID, cashier's check or wire confirmation), moving tips | Email | VA | |
| 50 | 5 days before closing | Closing disclosure reminder: review it with lender, questions to Charles | Text | VA | |
| 51 | 1 to 2 days before closing | Final walk-through: scheduled with buyer, checklist sent the night before (systems, repairs completed, personal property removed, condition) | Email + in person | VA schedules, Charles attends | |
| 52 | Day before closing | Text: "Tomorrow at [time]. Wire is confirmed. Bring your ID. Keys after funding." | Text | Charles | |
| 53 | Closing day | Charles at the closing table or on call; keys delivered in person with the closing gift | In person | Charles | Photo for social with written permission. |

`SP-Buyer Under Contract` sends touches 37, 46, 48 automatically and creates Command tasks for every other row with the date pulled from the tracker. The VA confirms dates on the tracker every Monday.

## Phase 7: Closed and Beyond (stage: Closed, `SP-Past Client Program` then 33 Touch)

Non-negotiable: every closed client enters `SP-Past Client Program` the day of closing. The VA changes type tag from `Buyer` to `Past Client`, status to `Closed`, confirms `Met`, and starts the plan.

| # | When | Touch | Channel | Owner | Notes |
|---|---|---|---|---|---|
| 54 | Closing day | Closing gift delivered with keys | In person | Charles | Gift standard below. |
| 55 | Closing day | Handwritten note mailed | Mail | Charles writes, VA mails | |
| 56 | Day 3 | Review request: text with the Google Business Profile review link, then email with the same link | Text + email | Command (`SP-Past Client Program`) | Only after Charles confirms the buyer is happy. |
| 57 | Day 7 | Call from Charles: "How is the first week? Anything not working, any surprises?" | Call | Charles | Vendor referrals as needed. |
| 58 | Day 30 | Email: home maintenance starter checklist, where documents live, how to reach vendors | Email | Command (`SP-Past Client Program`) | |
| 59 | Day 30 | Ask for referral: "Who else do you know thinking about buying or selling this year?" | Call or text | Charles | Log any names as `Sphere` + `Src-Referral`. |
| 60 | Day 90 | Call from Charles: settle-in check, property tax and homestead exemption reminder where applicable | Call | Charles | |
| 61 | Day 90 | Handoff: contact is added to `SP-33 Touch (Met)`; `SP-Past Client Program` continues in parallel for the anniversary touches | Command | VA | Tag `33-Touch` added. |
| 62 | Annual (closing anniversary) | Home anniversary card plus an annual equity update ("your home, one year later") | Mail + email | Command task, VA prepares, Charles signs | Use Command's home valuation or the tool chosen in 08-WEBSITE-FUNNEL/lead-magnets.md. |
| 63 | Ongoing | 33 Touch: monthly market note, quarterly call, holiday touches, client events | Mixed | Command (`SP-33 Touch (Met)`) | See 04 database docs for the 33 Touch calendar. |

### Closing gift standard

- Budget: a fixed amount per closing, set in the annual budget. Consistent for every buyer.
- Choice: something for the home that lasts and carries no logo (cutting board with the address, framed photo of the front door, local artisan piece). A gift card is a fallback, not the standard.
- Card: handwritten by Charles.
- Logged: VA records the gift and date in the Command contact notes.

## Handoffs at a glance

| From | To | Trigger | VA actions in Command |
|---|---|---|---|
| Cultivate | Consult Set | Calendly booking | Stop `SP-Speed to Lead`, status `Hot`, stage change, `#leads` post |
| Consult Set | Consult Met | Consult happened | Stage change, `Haven't Met` to `Met`, needs analysis in notes |
| Consult Met | Buyer Agreement Signed | DocuSign completed | Stage change, status `Active`, search set up |
| Buyer Agreement Signed | Showing | First showing booked | Stage change, itinerary/recap tasks created |
| Showing | Offer Written | Offer submitted | Stage change, offer summary filed in Drive |
| Offer Written | Under Contract | Acceptance | Stage change, status `Under-Contract`, start `SP-Buyer Under Contract`, tracker filled, Drive folder |
| Under Contract | Closed | Funding and keys | Stage change, type `Past Client`, status `Closed`, start `SP-Past Client Program`, gift and note logged |
| Closed | 33 Touch | Day 90 | Add `SP-33 Touch (Met)`, tag `33-Touch` |

## Quality checks

- Weekly, the VA audits every `Active` buyer: last touch date, next scheduled touch, pre-approval letter date, agreement expiration.
- Weekly, Charles spot-checks two itineraries and two recaps for tone and accuracy.
- Any buyer who has to ask "what happens next?" is logged in `#ops` as a system miss with the fix.
