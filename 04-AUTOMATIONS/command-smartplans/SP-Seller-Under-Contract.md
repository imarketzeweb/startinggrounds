# SmartPlan: `SP-Seller Under Contract`

## Purpose
Contract to closing for a seller. Every milestone is explained before it happens, in writing, so the seller never has to ask. Bad news (low appraisal, inspection demands, buyer financing trouble) is never delivered by this plan; it is a phone call from Charles, and the plan's message is sent only after that call.

## Entry trigger
- Opportunity stage `Under Contract` on the Seller pipeline (Zapier Z-07 adds; fallback: VA in SOP-07). Day 0 = contract acceptance date.

## Exit conditions
- Opportunity moves to `Closed`: Z-09 removes this plan and starts `SP-Past Client Program`.
- Contract terminates: VA removes the plan, moves Opportunity back to `Active`, and re-adds `SP-Seller Listing Launch` from the appropriate step.

## Milestone note
Command SmartPlans are day-offset based. The offsets below assume a typical 30-day close: inspection by Day 7 to 10, appraisal by Day 14 to 18, loan commitment by Day 21 to 25, walk-through Day 28 to 29, closing Day 30. On a 21-day or 45-day contract the VA edits the step dates in Command the day the plan starts (SOP-07 step 2) using the actual contract deadlines from the milestone tracker.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 (after Charles's call) | Email | Subject: Under contract on [ADDRESS]: your road map to closing | Hi [First Name], congratulations, we're under contract at [PRICE]. Here is the road to closing on [closing date]: inspection by [date], appraisal around [date], buyer's loan commitment by [date], final walk-through [date], and closing [date] at [title company]. I'll write to you before each one. [VA NAME] will coordinate access for the inspector and appraiser. Nothing is final until the keys change hands, so keep the home in the same condition and don't cancel utilities yet. Questions anytime: [PHONE]. Charles Brewer, Keller Williams | Charles approves, VA sends after his call |
| 2 | Day 0 | Task | Milestone tracker | Task for VA: create the milestone tracker row for this contract with every contract deadline; adjust this plan's step dates to match; confirm title company and attorney (if applicable) contacts. SOP-07. | VA |
| 3 | Day 2 | Text | Earnest money confirmation | Hi [First Name], [VA NAME] here. The buyer's earnest money of [amount] was received by [title company] today, so the contract is fully in force. Next up: inspection on [date]. I'll confirm the time tomorrow. | VA (VA approves) |
| 4 | Day 5 | Email | Subject: Inspection [date]: what to expect | Hi [First Name], the buyer's inspection is [date] from [time]. Please be away with pets for about 3 hours; leave utilities on and access to attic, electrical panel, and water heater clear. Afterward the buyer may ask for repairs or credits. That's normal. Charles will call you with anything they request and walk you through options before you decide anything. Charles Brewer and [VA NAME] | Charles approves, VA sends |
| 5 | Day 8 | Call task | Post-inspection call | Task for Charles: call the seller the day the inspection response arrives (or Day 10 if nothing). Explain requests, options, and recommendation. Only after this call does step 6 go. | Charles |
| 6 | Day 10 | Email | Subject: Inspection resolved: here's what we agreed | Hi [First Name], following our call, here is what was agreed on the inspection: [summary of repairs or credits, or "no repairs requested"]. Any repairs need to be done by [date] with receipts; [VA NAME] can schedule vendors if you'd like. Next milestone: the appraisal, likely around [date]. Charles | Charles writes summary, VA sends |
| 7 | Day 12 | Email | Subject: Appraisal: how it works and how we prepare | Hi [First Name], the buyer's lender will send an appraiser around [date]. I'll meet them with a package of the comparable sales and the improvements you've made, which is the best way to support our price. You don't need to do anything but keep the home tidy. I'll let you know the result the day we hear. Charles | VA, Charles approves |
| 8 | Day 18 | Call task | Appraisal result call | Task for Charles: call the seller with the appraisal result the day it arrives. If low, discuss options on the phone before anything in writing. | Charles |
| 9 | Day 22 | Email | Subject: Loan commitment and the final stretch | Hi [First Name], the buyer's lender has [issued / is finalizing] the loan commitment, due by [date]. From here: [VA NAME] will confirm your closing appointment with [title company], remind you about utility transfers (schedule for the day after closing), and coordinate the final walk-through on [date]. Start packing in earnest; you're almost there. Charles | Charles approves, VA sends |
| 10 | Day 25 | Text | Moving logistics | Hi [First Name], [VA NAME]. Two reminders: schedule utility transfers for [day after closing], and the buyer's final walk-through is [date] at [time], so the home should be empty and broom-clean by then. Need a mover or cleaner? I have names. | VA (VA approves) |
| 11 | Day 28 | Email | Subject: Closing day: what to bring, what happens | Hi [First Name], closing is [date] at [time] at [title company address]. Bring a government ID, all keys, garage remotes, and any codes. Your proceeds are wired per the instructions the title company sends directly (call them to verify wiring instructions by phone; never trust an email with wiring changes). Leave the home as agreed. I'll be there, and I'll call the moment we're recorded. Charles | Charles approves, VA sends |
| 12 | Day 29 | Text | Night before | Hi [First Name], Charles. Tomorrow's the day. Walk-through went [well / notes]. See you at [time]. Thank you for trusting me with this one. | Charles |
| 13 | Day 30 | Task | Closing day | Task for VA: confirm recording, move Opportunity to `Closed` (this triggers Z-09), update Active Listings sheet, confirm closing gift ordered. | VA |

## Notes
- Steps 3 and 10 are logistics the VA may send alone. Every other message follows a Charles call or approval.
- Wire fraud line in step 11 stays in every version. Never remove it.
- The `Under Contract` social post is triggered by Z-07 and needs seller permission noted in the Opportunity before it is scheduled.
