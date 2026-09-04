# SmartPlan: `SP-Buyer Under Contract`

## Purpose
Offer accepted to keys in hand for a buyer. Every milestone (earnest money, inspection, appraisal, insurance, loan commitment, utilities, walk-through, closing) is explained before it happens. Bad news is a Charles phone call first, every time.

## Entry trigger
- Opportunity stage `Under Contract` on the Buyer pipeline (Zapier Z-07 pattern or VA in SOP-07). Day 0 = acceptance date.

## Exit conditions
- Opportunity moves to `Closed`: Z-09 removes this plan and starts `SP-Past Client Program`.
- Contract terminates: VA removes the plan, moves Opportunity back to `Showing`.

## Milestone note
Day offsets assume a 30-day close: EMD Day 1 to 3, inspection Day 5 to 10, appraisal ordered Day 7 and back by Day 18, insurance bound by Day 20, loan commitment Day 21 to 25, walk-through Day 29, closing Day 30. Command SmartPlans are day-offset based, so on any other timeline the VA edits the step dates the day the plan starts (SOP-07) to match the contract deadlines in the milestone tracker.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 (after Charles's call) | Email | Subject: Offer accepted on [ADDRESS]. Here's the road to keys | Hi [First Name], congratulations, your offer on [ADDRESS] is accepted at [PRICE]. The road to closing on [date]: earnest money due [date], inspection by [date], appraisal ordered this week, insurance bound by [date], loan commitment by [date], walk-through [date], closing [date]. I'll write before each step, and [VA NAME] will handle scheduling and reminders. Two rules from today: don't open new credit or move money around without telling your lender, and call the title company by phone to verify any wiring instructions. [PHONE] anytime. Charles Brewer, Keller Williams | Charles approves, VA sends after his call |
| 2 | Day 0 | Task | Milestone tracker | Task for VA: create the tracker row with every contract date, adjust this plan's step dates, confirm lender, title, and insurance contacts. SOP-07. | VA |
| 3 | Day 1 | Text | Earnest money reminder | Hi [First Name], [VA NAME] here. Earnest money of [amount] is due to [title company] by [date]. They'll send instructions directly; call them at their published number to confirm before wiring. Let me know once sent and I'll confirm receipt. | VA (VA approves) |
| 4 | Day 4 | Email | Subject: Inspection [date]: what it is and what happens after | Hi [First Name], your inspection is [date] at [time] with [inspector]. Plan for about 3 hours; come for the last 45 minutes so the inspector can walk you through findings. Every home has a list. After the report, Charles will call to sort the items into three buckets: safety and structural, worth negotiating, and normal wear. Then you decide together what to request. Charles and [VA NAME] | Charles approves, VA sends |
| 5 | Day 8 | Call task | Post-inspection strategy call | Task for Charles: call the buyer within 24 hours of the report. Go through the buckets, recommend the request, set expectations on seller response. Only after this does step 6 go. | Charles |
| 6 | Day 11 | Email | Subject: Inspection response: where we landed | Hi [First Name], after our call, here is what we requested and what the seller agreed to: [summary]. Any repairs must be complete by [date] with receipts, and we'll verify at the walk-through. Next: the appraisal, which the lender ordered on [date]. Charles | Charles writes summary, VA sends |
| 7 | Day 13 | Email | Subject: Appraisal and insurance: two things happening this week | Hi [First Name], two items. The appraisal: the lender's appraiser visits [date]; you don't need to be there, and I'll send the result the day we hear. Insurance: please get a homeowner's policy quote now and have it bound by [date]; your lender needs proof before commitment. If you'd like names of agents my clients have used, reply "insurance". Charles | VA, Charles approves |
| 8 | Day 18 | Call task | Appraisal result call | Task for Charles: call with the result the day it arrives. If low, options on the phone first. | Charles |
| 9 | Day 21 | Email | Subject: Loan commitment and the final checklist | Hi [First Name], the lender expects to issue the loan commitment by [date]. Before closing you'll need: insurance binder to the lender, utilities scheduled to start [closing date] (list attached: electric, gas, water, internet), a cashier's check or wire for closing funds (amount from the title company's Closing Disclosure, which you must receive at least 3 business days before closing), and your ID. [VA NAME] will check each off with you. Charles | Charles approves, VA sends |
| 10 | Day 24 | Text | Utilities and movers | Hi [First Name], [VA NAME]. Reminder to set up utilities to start [closing date] and book movers. The Closing Disclosure should arrive by [date]; send it to Charles when you get it so he can review it with you. | VA (VA approves) |
| 11 | Day 27 | Email | Subject: Walk-through and closing day | Hi [First Name], walk-through is [date] at [time]: we check that repairs are done, the home is in the agreed condition, and everything that should be there is there. Closing is [date] at [time] at [title company address]. Bring your ID and closing funds as instructed by phone from the title company. After signing and recording, keys are yours. I'll be with you for both. Charles | Charles approves, VA sends |
| 12 | Day 29 | Text | Night before | Hi [First Name], Charles. Walk-through done, [notes]. Tomorrow at [time] you get keys. Proud of how you handled this. See you there. | Charles |
| 13 | Day 30 | Task | Closing day | Task for VA: confirm recording and key delivery, move Opportunity to `Closed` (triggers Z-09), update Active Buyers sheet, confirm closing gift. | VA |

## Notes
- Steps 3 and 10 are logistics the VA may send alone. Everything else waits for Charles's call or approval.
- The wire fraud line stays in steps 1 and 3 in every version.
- Lender questions go to the lender; the plan never explains rates or loan terms.
