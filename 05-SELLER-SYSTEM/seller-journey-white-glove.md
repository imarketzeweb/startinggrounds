# Seller Journey: White Glove, Touch by Touch

This is the full seller experience from first contact to home anniversary. Every touch has an owner. If a touch has no owner it does not happen.

Owner key:
- **Charles**: personal call, meeting, or personally written message
- **VA**: [VA NAME] does it by hand
- **SmartPlan**: Command sends it or creates the task automatically (SmartPlan named in the row)
- **Zap**: Zapier moves data or posts an alert (Zap named in the row)
- **GPT**: drafted by the named GPT, approved by a human, sent from Command

Script references point to files in this folder or to `03-CHATGPT` GPT prompts. Template names in Command Designs follow `[Address]-[Stage]-[Platform]`.

## Stage map

| Journey phase | Seller pipeline stage | Listing stage | SmartPlan | Status tag |
|---|---|---|---|---|
| Lead to appointment | Cultivate → Appointment Set | none | `SP-Speed to Lead` then `SP-Seller Nurture` | `New-Lead` → `Nurture` or `Hot` |
| Consultation | Appointment Met | none | `SP-Seller Nurture` paused | `Hot` |
| Signed to launch | Listing Signed → Coming Soon | Coming Soon | `SP-Seller Listing Launch` | `Active` |
| On market | Active | Just Listed, Open House | `SP-Seller Listing Launch` | `Active` |
| Contract to close | Under Contract | Under Contract | `SP-Seller Under Contract` | `Under-Contract` |
| Closed and beyond | Closed | Just Sold | `SP-Past Client Program`, `SP-33 Touch (Met)` | `Closed`, type flips to `Past Client` |

## Phase 1: Lead to appointment (pipeline: Cultivate → Appointment Set)

Standard: human response within 5 minutes, 8am to 8pm. Automation acknowledges, a human replies.

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Minute 0 | Lead arrives (site form, social DM, sign call, referral, open house). Contact created with `Seller`, `New-Lead`, one `Src-` tag, `Haven't Met` or `Met` | Command | Zap `Z-01 Website Form → Command Contact + Speed to Lead` (or VA by hand for DM/phone leads) | n/a |
| Minute 0 | Instant acknowledgment text: "Got your note about [ADDRESS]. Charles will call you within the hour." | SMS | SmartPlan `SP-Speed to Lead` | Speed to Lead text 1 |
| Minute 0 | Alert to `#leads` with name, source, address, message | Slack | Zap `Z-02 New Seller Lead → #leads` | n/a |
| Minute 0 to 5 | Read the lead, run `CB Lead Responder` for an A/B/C grade and a suggested reply, call the lead | Phone | Charles (VA if Charles is in an appointment, VA says "Charles asked me to reach you") | `CB Lead Responder` prompt; intake call script in pre-listing-process.md |
| Minute 5 | If no answer: personal text + voicemail | SMS + voicemail | Charles | "Hi [Name], Charles Brewer. Saw your note about [ADDRESS]. I'll try again at [time], or grab a slot here: [CALENDLY LINK]" |
| Day 0 | Temperature tag set (`A`, `B`, or `C`), stage stays Cultivate | Command | VA | n/a |
| Day 0 | Email: "What happens when we work together" (3 paragraphs, link to charlesbrewer.guru seller page) | Email | SmartPlan `SP-Speed to Lead` | Speed to Lead email 1 |
| Day 1 | Second call attempt if no contact | Phone | Charles | Same as above |
| Day 2 | Text: home value question, low pressure | SMS | SmartPlan `SP-Speed to Lead` | Speed to Lead text 2 |
| Day 3 | Email: "3 things every [MARKET] seller should know before listing" | Email | SmartPlan `SP-Speed to Lead` | Speed to Lead email 2 |
| Day 5 | Call attempt 3, leave voicemail with the Calendly link | Phone | Charles | n/a |
| Day 7 | Email: recent [NEIGHBORHOOD] sales snapshot | Email | SmartPlan `SP-Speed to Lead` | Speed to Lead email 3 |
| Day 10 | Speed to Lead ends. `A` or `B` with no appointment moves to `SP-Seller Nurture`, tag `Seller-Nurture`. `C` moves to `SP-Seller Nurture` plus `SP-12 Direct (Haven't Met)` or `SP-33 Touch (Met)` | Command | SmartPlan `SP-Speed to Lead` (last step creates VA task to confirm) | n/a |
| Appointment booked | Stage → Appointment Set. Confirmation text and email with date, time, what to expect, what to have ready | SMS + Email | SmartPlan `SP-Seller Nurture` (appointment step) triggered by VA moving the stage | Appointment confirmation template |
| Appointment booked | Intake call scheduled 2 to 3 days before the consultation | Phone | VA books, Charles calls | Intake call script, pre-listing-process.md |
| Appointment booked | Alert to `#listings`: "Appointment set, [ADDRESS], [date]" | Slack | Zap `Z-03 Opportunity Stage Change → #listings` | n/a |

## Phase 2: Pre-listing and consultation (pipeline: Appointment Set → Appointment Met)

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Consult minus 3 | Intake call, 20 minutes. Fill the Seller Intake Form live | Phone | Charles | Intake call script, pre-listing-process.md |
| Consult minus 3 | Seller Intake Form saved to `Listings/[YYYY-MM] [Street Address]/04-Marketing-Kit`. Drive folder created | Drive | VA (or Zap `Z-04 Stage = Appointment Set → Create Drive Folder`) | Seller Intake Form, pre-listing-process.md |
| Consult minus 2 | Pre-listing packet delivered by email (PDF) and, when local, dropped at the door | Email + physical | VA assembles, Charles approves, VA sends | Pre-listing packet contents, pre-listing-process.md |
| Consult minus 2 | Text: "Packet is in your inbox. Skim pages 2 and 3 before we meet, that's where the pricing conversation starts." | SMS | Charles | n/a |
| Consult minus 1 | CMA prepared, pricing range set, `CB Seller Concierge` used to prepare the pricing talk track | Internal | Charles with VA data pull | CMA prep checklist, pre-listing-process.md |
| Consult minus 1 | Reminder text with address confirmation and Charles's ETA | SMS | SmartPlan `SP-Seller Nurture` (appointment step) | Reminder template |
| Consult day | Listing consultation, 60 to 90 minutes. Walk the home, needs, pricing, marketing plan, agreement | In person | Charles | Consultation agenda, pre-listing-process.md |
| Consult day | Stage → Appointment Met | Command | VA (from Charles's post-meeting Slack note) | n/a |
| Consult day, evening | Thank-you text with the one thing the seller cared about most | SMS | Charles | "Thanks for your time today. I heard you on [their priority]. Here is how we handle it: [one line]." |
| Consult plus 1 | Follow-up email: recap, pricing recommendation in writing, next step, listing agreement via DocuSign if not signed on site | Email + DocuSign | Charles drafts with `CB Seller Concierge`, VA sends from Command Opportunity | Consultation recap template |
| Consult plus 3 | If not signed: call | Phone | Charles | "Any questions on the plan or the number?" |
| Consult plus 7 | If not signed: back to `SP-Seller Nurture` with a monthly market update, stage stays Appointment Met, tag `Nurture` | Email | SmartPlan `SP-Seller Nurture` | n/a |

## Phase 3: Listing Signed to launch (pipeline: Listing Signed → Coming Soon)

Full detail is in listing-launch-playbook.md. This table is the seller-facing view only.

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Day -14 (signed) | Stage → Listing Signed. Status tag `Active`. `SP-Seller Listing Launch` starts. Opportunity created with DocuSign room | Command | VA | n/a |
| Day -14 | Welcome call: "Here is exactly what the next 14 days look like." Confirm launch date, photo date, vendor access | Phone | Charles | Launch roadmap talk track, pre-listing-process.md |
| Day -14 | Welcome email with the 14-day pre-launch timeline, prep checklist, and vendor schedule | Email | SmartPlan `SP-Seller Listing Launch` day 1 | Seller launch welcome email |
| Day -14 | Alert to `#listings`: "Listing signed, [ADDRESS], launch [date]" | Slack | Zap `Z-03 Opportunity Stage Change → #listings` | n/a |
| Day -13 | Vendor bookings confirmed and texted to seller (stager, cleaner, handyman, photographer) | SMS | VA | Vendor confirmation text |
| Day -12 | Seller prep checklist call (10 min): declutter, repairs, pets, what to remove from walls | Phone | Charles | Prep checklist, pre-listing-process.md |
| Day -10 | Stager walk, handyman punch list | In person | VA schedules, vendors execute | Vendor-prep checklist |
| Day -7 | Photo day confirmation text: "Photographer arrives [time]. Lights on, blinds open, cars out of the driveway." | SMS | SmartPlan `SP-Seller Listing Launch` day 7 | Photo day prep text |
| Day -6 | Photo, drone, video, 3D, floor plan shoot | In person | VA coordinates, Charles present if possible | Vendor-prep checklist |
| Day -5 | Marketing kit generated via `CB Listing Marketer`, reviewed by Charles | Internal | VA runs GPT, Charles approves | listing-marketing-kit-template.md |
| Day -4 | Seller reviews and approves the MLS remarks and hero photo (send 3 photo options) | Email | VA sends, Charles handles pushback | "Seller approval" email template |
| Day -3 | Stage → Coming Soon. Coming Soon in MLS if permitted (verify local MLS rules). Coming Soon social posts begin | MLS + social | VA | listing-launch-playbook.md |
| Day -3 | Seller receives the seller-facing marketing summary (from the kit) | Email | VA | Seller-facing marketing summary, listing-marketing-kit-template.md |
| Day -2 | Sign and lockbox installed, showing instructions set up in ShowingTime (or equivalent) | Physical | VA schedules | n/a |
| Day -1 | "Tomorrow we go live" text with the exact time and what to expect in the first 72 hours | SMS | Charles | Go-live text |

## Phase 4: On market (pipeline: Active)

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Day 0 | Listing goes Active in MLS at the agreed time. Stage → Active | MLS + Command | VA | Listing QA checklist, listing-launch-playbook.md |
| Day 0 | Just Listed social sequence starts, database email blast goes out, agent-to-agent email goes out | Social + email | VA schedules, SmartPlan `SP-Seller Listing Launch` sends the database blast | listing-marketing-kit-template.md |
| Day 0 | 10 neighbor calls, "just listed" | Phone | Charles | 10 neighbor call script, listing-marketing-kit-template.md |
| Day 0 | Text to seller: "We are live. Links: [MLS], [property page], [Zillow]. Watch your ShowingTime notifications." | SMS | Charles | Live text |
| Day 1 | Syndication check: Zillow, Realtor.com, Redfin, Homes.com. Screenshot proof to seller | Email | VA | Syndication check, listing-launch-playbook.md |
| Day 1 | Alert to `#listings` with syndication status | Slack | VA | n/a |
| Day 2 to 3 | Broker open (if scheduled) | In person | Charles hosts, VA promotes | open-house-system.md |
| Days 0 to 7 | Every showing: feedback requested automatically within 2 hours, relayed to the seller within 24 hours with interpretation | SMS or email to seller | ShowingTime requests it, VA logs it, Charles relays it | Feedback relay template below |
| Day 5 to 7 | Mega open house, first weekend | In person | Charles hosts, VA runs promo and sign-in | open-house-system.md |
| Day 7 (first Monday) | Weekly seller update, written | Email | VA pulls data, `CB Seller Concierge` drafts, Charles approves and sends | weekly-seller-report-template.md |
| Every Monday | Weekly seller update, written, by 12pm | Email | Same as above | weekly-seller-report-template.md |
| Every Tuesday (listings over 14 days) | Voice call to the seller following the Monday email | Phone | Charles | "Did you read the update? Here's what I'd do this week." |
| Day 14, no offers | Price and marketing review meeting | Phone or in person | Charles | Day 14 agenda, listing-launch-playbook.md |
| Day 30, no offers | Formal price review with new CMA | In person | Charles | Day 30 agenda, listing-launch-playbook.md |
| Any day, offer arrives | Offer logged in the Opportunity, alert to `#listings` | Command + Slack | VA | n/a |
| Any day, offer arrives | Offer presentation call within 4 hours of receipt: net sheet, terms grid, recommendation | Phone or in person | Charles, VA prepares net sheet and terms grid | Offer presentation template below |
| Multiple offers | Offer comparison grid sent before the call, deadline set and communicated to all agents | Email | VA prepares, Charles sends | Multiple offer grid |
| Offer accepted | Stage → Under Contract, `SP-Seller Listing Launch` stops, `SP-Seller Under Contract` starts. MLS status updated per rules | Command + MLS | VA | n/a |

### Showing feedback relay template (Charles, within 24h)

```
[Name], feedback from today's [time] showing:

Agent said: "[verbatim]"

What that tells us: [one or two sentences. Is it price, condition, layout, or nothing actionable?]

What I'm doing about it: [nothing yet / adjusting the description / discussing at Monday's update / suggest we talk]

Next showing is [date/time or "none booked yet, [X] scheduled for the week"].
```

### Offer presentation template (Charles, phone or in person)

1. The headline: price, close date, financing, contingencies, in one sentence.
2. The net sheet (VA prepares from the title company's estimate).
3. The terms grid: price, earnest money, financing type and lender strength, appraisal gap, inspection period, closing date, possession, concessions, contingencies, anything unusual.
4. Buyer strength read: pre-approval letter reviewed, lender called, agent reputation.
5. Recommendation: accept, counter (with the exact counter), or reject, and why.
6. Decision deadline and what happens next in Command.

## Phase 5: Under contract (pipeline: Under Contract)

SmartPlan `SP-Seller Under Contract` creates the tasks and sends the milestone emails. Charles makes every call that carries news.

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Contract day | Call: "Congratulations, here is the road to closing." Walk the timeline | Phone | Charles | Under contract roadmap talk track |
| Contract day | Email: full contract-to-close timeline with every date and who does what | Email | SmartPlan `SP-Seller Under Contract` day 1 | Contract-to-close timeline email |
| Contract day | Under Contract social post, MLS status change | Social + MLS | VA | social-media-listing-templates.md |
| Contract day | Earnest money confirmation text once received | SMS | VA | "Earnest money of $[X] received by [title company] on [date]." |
| Contract day | Alert to `#listings`: "Under contract, [ADDRESS], close [date]" | Slack | Zap `Z-03 Opportunity Stage Change → #listings` | n/a |
| Contract plus 2 | Text: inspection scheduled for [date/time], what to do (leave, pets out, utilities on, access to attic and panel) | SMS | VA | Inspection prep text |
| Inspection day | Text morning of: "Inspector arrives [time]. We'll have their report within 48 hours." | SMS | SmartPlan `SP-Seller Under Contract` (task to VA to send) | n/a |
| Inspection plus 1 to 3 | Repair request received. Call to walk through it and set a response strategy | Phone | Charles | Repair negotiation talk track |
| Repair agreement | Email: signed amendment, repair list, who does what by when | Email + DocuSign | VA sends from Command Opportunity | n/a |
| Appraisal ordered | Text: "Appraisal ordered. Appraiser visit is [date]. I'm sending the appraiser our comps and the upgrade list." | SMS | Charles | Appraisal prep text |
| Appraisal day | Appraiser packet delivered: comps, upgrades with dates and cost, offer summary if multiple offers | Email / at door | VA prepares, Charles delivers | Appraiser packet checklist |
| Appraisal result | Call the same day: came in at value, or the plan if it did not | Phone | Charles | n/a |
| Contingencies cleared | Email: "Inspection and appraisal contingencies cleared. Remaining: financing, title, walkthrough." | Email | SmartPlan `SP-Seller Under Contract` (task) | Milestone email |
| Close minus 10 | Moving checklist email: utilities, mail forwarding, keys, garage openers, manuals, what to leave | Email | SmartPlan `SP-Seller Under Contract` | Seller moving checklist |
| Close minus 7 | Call: confirm signing appointment, wire instructions (verbally confirm, warn about wire fraud), possession plan | Phone | Charles | Closing prep talk track |
| Clear to close | Text and Slack: "Clear to close. Signing is [date/time] at [title company]." | SMS + Slack | VA (Slack), Charles (text) | n/a |
| Close minus 2 | Final walkthrough scheduled, seller told what the buyer will check | SMS | VA | Walkthrough prep text |
| Close minus 1 | Text: "Tomorrow: bring ID, keys, openers. I'll be there at [time]." | SMS | Charles | n/a |

## Phase 6: Closing day and post-closing (pipeline: Closed)

| Day / trigger | Touch | Channel | Owner | Script or template |
|---|---|---|---|---|
| Closing day | Attend signing or call immediately after. Confirm funding and recording | In person / phone | Charles | n/a |
| Closing day | Closing gift delivered (local, personal, tied to something from the intake form's "seller's favorite things") | Physical | VA orders on contract day, Charles hands it over | Closing gift SOP below |
| Closing day | Stage → Closed. Type tag `Seller` → `Past Client`. Status `Closed`. Relationship `Met`. `SP-Seller Under Contract` stops. `SP-Past Client Program` starts, tag `Past-Client-Program` | Command | VA, same day (service standard 5) | n/a |
| Closing day | Just Sold social post (with seller permission, no sale price unless permitted and MLS-compliant) | Social | VA | social-media-listing-templates.md |
| Closing day | Alert to `#listings`: "Closed, [ADDRESS]" | Slack | Zap `Z-03 Opportunity Stage Change → #listings` | n/a |
| Day +1 | Handwritten thank-you note mailed | Mail | Charles writes, VA mails | n/a |
| Day +7 | Check-in call: "Settled? Anything from the move you need a name for?" Ask for a review if the moment is right | Phone | Charles | Review ask script below |
| Day +7 | Review request link email (Google Business Profile first, Zillow second) | Email | SmartPlan `SP-Past Client Program` day 7 | Review request email |
| Day +30 | Text: "One month. How's the new place?" plus a copy of the final closing statement reminder for taxes | SMS | SmartPlan `SP-Past Client Program` day 30 (task to Charles to personalize) | n/a |
| Day +90 | Email: "Three things I've learned about [MARKET] since we closed" and a referral ask | Email | SmartPlan `SP-Past Client Program` day 90 | Referral ask email |
| Day +90 | Move the contact into `SP-33 Touch (Met)`, tag `33-Touch`. `SP-Past Client Program` continues in parallel for anniversaries | Command | SmartPlan `SP-Past Client Program` day 90 (task to VA) | n/a |
| Annual, closing anniversary | Home anniversary card or small gift plus annual home value email | Mail + email | SmartPlan `SP-Past Client Program` (annual step, task to VA and Charles) | Home anniversary template |
| Annual, January | Closing statement copy and "homeowner tax reminder" email | Email | SmartPlan `SP-Past Client Program` | n/a |
| Ongoing | 33 Touch continues: monthly market email, quarterly call, birthday, holiday, two events a year | Mixed | SmartPlan `SP-33 Touch (Met)` with Charles doing the calls | 33 Touch calendar (see 02-DATABASE) |

### Closing gift SOP (VA)

1. On contract day, reread "seller's favorite things" from the Seller Intake Form.
2. Choose a gift tied to it (local restaurant, their hobby, something for the new home). Budget: [set amount].
3. Order by close minus 7. Deliver to Charles by close minus 1.
4. Log the gift in the Opportunity notes so it is never repeated.

### Review ask script (Charles, Day +7 call)

"Before I let you go, one favor. Reviews are how people like you find me. If you'd be willing to write two sentences about how this went, [VA NAME] will send you a link that takes about a minute. Would that be okay?"

If yes, VA sends the review link within the hour.

## Definition of done per phase

| Phase | Done when |
|---|---|
| Lead to appointment | Appointment on the calendar, intake call scheduled, stage Appointment Set |
| Consultation | Listing agreement signed in DocuSign, stage Listing Signed, `SP-Seller Listing Launch` running |
| Signed to launch | QA checklist passed, listing Active in MLS, seller has live links |
| On market | Executed contract, stage Under Contract, `SP-Seller Under Contract` running |
| Under contract | Funded and recorded, stage Closed, `SP-Past Client Program` running same day |
| Post-closing | Review received, contact in `SP-33 Touch (Met)`, anniversary task scheduled |
