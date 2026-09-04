# SOP-07  Under Contract Coordination

## Purpose
From accepted offer to closing, the client hears from us before every milestone, every deadline is tracked, every vendor is scheduled, and Charles makes every call that carries news. Works with `SP-Seller Under Contract`, `SP-Buyer Under Contract`, and Z-07. Command SmartPlans are day-offset based; this SOP is where the offsets get matched to the real contract.

## Trigger
- Charles posts "Under contract: [ADDRESS], [client name], closing [date]" in `#listings` (sellers) or `#ops` (buyers), or the Opportunity moves to `Under Contract`.

## Steps
1. **Within 1 hour: tracker.** Create the milestone tracker row (the `Milestone Tracker` sheet or Command Opportunity checklist): acceptance date, earnest money due, inspection deadline, inspection response deadline, appraisal expected, financing/loan commitment deadline, title commitment, HOA docs (if any), walk-through, closing date and location, plus contacts for title, lender, the other agent, the other side's coordinator, inspector, and attorney where applicable. Source: the executed contract in Command (DocuSign). You read dates and names only; you do not interpret terms.
2. **Within 1 hour: stage and plan.** Confirm the Opportunity is at `Under Contract` and the sheet (`Active Listings` or `Active Buyers`) shows Under Contract with the closing date (Z-07 trigger fallback). Confirm the right SmartPlan is running (`SP-Seller Under Contract` or `SP-Buyer Under Contract`) and the listing launch or nurture plan is removed. **Adjust every step's date in the SmartPlan to match the tracker** (typical 30-day offsets are the default; edit for 21-day, 45-day, cash, etc.). Set status tag `Under-Contract`.
3. **Day 0: the road map.** Charles calls the client first. After his call (he posts "called" in the thread), send the Day 0 road-map email with the real dates filled in, from Command, after Charles approves the filled version.
4. **Vendors and access.** Schedule and confirm: inspection (buyer side: book with the client's chosen inspector; seller side: confirm access and instructions), appraisal access, repair vendors after the inspection agreement, walk-through, closing appointment. Every appointment on Charles's calendar and in the tracker. Confirm each with the client by text the day before (the VA may send these logistics texts).
5. **Milestone messages.** Each SmartPlan step arrives as a task with copy. Fill placeholders from the tracker, post for approval where the plan says "Charles approves", send from Command after approval, and mark the tracker milestone done with the date. Logistics texts marked "VA approves" go without waiting. Never send the inspection-result, appraisal-result, or loan-commitment emails until Charles has posted "called" for that milestone.
6. **Weekly.** Every Monday (sellers) and Thursday (buyers): check the tracker for anything due in the next 7 days, chase lender status (buyer side) with a polite email copying Charles, chase repair receipts, and confirm the other side's coordinator is aligned on dates. Post a one-line status per contract in the EOD report.
7. **Documents.** Every signed addendum, inspection report, repair receipt, appraisal notice, title commitment, and Closing Disclosure goes in `05-Docs` (sellers) or the buyer's transaction folder, and is attached in the Command Opportunity. The Closing Disclosure goes to Charles the hour it arrives so he can review it with the client.
8. **Wire fraud rule.** Every message that mentions money says: verify wiring instructions by phone with the title company at their published number. If any email arrives with changed wiring instructions, do not forward it; call Charles and the title company.
9. **Closing week.** Confirm the closing appointment, ID and funds instructions, utilities (buyers: start on closing day; sellers: transfer the day after), movers, keys and remotes collected (sellers), final walk-through completed with notes in the tracker. Order the closing gift by Day 25 if Z-09 will not fire until closing (see `SOP-08`).
10. **Closing day.** Confirm recording with title; move the Opportunity to `Closed` and update the sheet (fires Z-09); proceed to `SOP-08`.
11. **If the contract falls apart.** Charles calls the client. Then: remove the under-contract plan, move the Opportunity back to `Active` (seller: re-add `SP-Seller Listing Launch` from the right step and update MLS status with Charles) or `Showing` (buyer), update the sheet, and note the reason in the Opportunity.

## Done-when
- Tracker complete with every deadline and contact; SmartPlan dates adjusted; every milestone message sent on time after the required Charles call; every vendor confirmed; documents filed; closing confirmed and Opportunity moved to Closed.

## Time
- 2 hours setup, then 30 to 60 minutes per contract per week; 2 hours in closing week.

## Tools
- KW Command (Opportunities, DocuSign, SmartPlans, Tasks), `Milestone Tracker` sheet, `Active Listings` / `Active Buyers` sheets, Google Drive, Slack `#listings` / `#ops`, phone, calendar.

## Escalate-if
- Any deadline is within 48 hours and not on track (lender silent, inspection not scheduled, repairs not done): Charles the same hour.
- Inspection report, appraisal, or lender raises anything the client will not like: Charles calls first; you send nothing.
- The other agent, the lender, or the title company asks you a question about terms, credits, extensions, or contingencies: "Charles will get back to you," then tell him.
- The client asks what a contract term means, whether to waive something, or what to do about a repair request: Charles.
- Anything about wiring instructions changing: stop and call Charles and title.
