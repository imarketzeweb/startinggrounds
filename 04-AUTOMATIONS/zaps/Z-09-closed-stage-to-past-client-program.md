# Z-09  Closed Stage → Past Client Program

## Name
`Z-09 Closed Stage → Past Client Program`

## Purpose
Service standard 5: every closed client enters `SP-Past Client Program` the day of closing. This Zap retags the contact, starts the program, creates the closing-gift task, schedules the Day 7 review request, and sets the yearly anniversary reminder. Past clients and their referrals are the core of the MREA database, so nothing here is optional.

## Trigger
- Preferred: **KW Command: Opportunity Stage Changed** to `Closed` on any pipeline (verify trigger).
- Fallback: **Google Sheets: Updated Spreadsheet Row** on `Active Listings` (sellers) or `Active Buyers` sheet, column `Stage` = Closed, which the VA sets during SOP-08.

## Steps

1. **Filter:** new stage = Closed.
2. **Google Sheets: Lookup Row** for the client: contact link, address, closing date, client type (Buyer / Seller / Investor), co-buyer names, gift preference notes (from the intake or buyer needs analysis).
3. **KW Command: Update Contact** tags (verify action; fallback: VA in SOP-08).

   | Action | Tags |
   |---|---|
   | Add | `Past Client`, `Closed`, `Met`, `Past-Client-Program` |
   | Remove | `Buyer` or `Seller` (type becomes `Past Client`; keep `Investor` if the client is an investor who will repeat), `Active`, `Under-Contract`, `Hot`, `New-Lead`, `Nurture`, `A`, `B`, `C`, `Buyer-Nurture`, `Seller-Nurture`, `8x8-Active` |
   | Keep | `Src-*` (never changed), `33-Touch` if present |

4. **KW Command: Remove from SmartPlan** `SP-Seller Under Contract` or `SP-Buyer Under Contract`. **Add to SmartPlan** `SP-Past Client Program`. After the program's 12 months, the SmartPlan itself adds `33-Touch` and `SP-33 Touch (Met)` (see the SmartPlan file).
5. **KW Command: Update Contact** custom field `Home Anniversary` = closing date (verify field; fallback: note "Closed {date} at {address}").
6. **KW Command: Create Task** for VA, due today: "Order closing gift for {name}: {gift_notes}. Budget per SOP-08. Ship to {address}."
7. **KW Command: Create Task** for Charles, due closing day +1: "Personal thank-you call to {name}."
8. **Delay by Zapier: Delay Until** closing date + 7 days, then **Slack** to `#ops`: `Day 7 review request due for {name}. VA: send review request per SOP-08 (Google review link + Command email step).` Also **KW Command: Create Task** VA due Day 7: "Send review request." (The `SP-Past Client Program` Day 7 email carries the review link; the task is the human check that it went.)
9. **Google Calendar: Create Detailed Event** yearly recurring on the closing date: "Home anniversary: {name}, {address}. Charles calls; VA sends card." Invite Charles and VA. (Command SmartPlans do not run yearly forever, so the calendar is the long-term reminder; `SP-Past Client Program` covers year one.)
10. **Google Sheets: Update Row** `Active Listings` / `Active Buyers`: move to `Closed` tab with closing date, price, and source. This is the scorecard's closed-units feed.
11. **Slack: Send Channel Message** to `#ops` (template below).

## Filters / Paths

| Client type | Extra step |
|---|---|
| Seller | Z-07 has already queued the Just Sold post. Add task: "Send Just Sold email to neighbors via Command Campaign (approved copy in kit)." |
| Buyer | Task: "Utilities and mail forwarding reminder sent? Confirm in milestone tracker." |
| Investor / capital partner | This Zap covers the flip's listing (Seller pipeline). Partner-side closing (distribution, review, next deal, `Repeat`) is Z-16. Keep `Capital-Partner` tag and `SP-Capital Partner Program` running. |

## ChatGPT step
None. The closing-day note and anniversary notes are written by `CB Seller Concierge` / `CB Buyer Concierge` in the SmartPlan steps (pre-written copy) and personalized by Charles.

## Alert message template (Slack `#ops`)
```
:tada: CLOSED  |  {name}  |  {address}  |  {client_type}
Tags updated: Past Client added, active tags removed (verify in Command: {contact_link})
SP-Past Client Program: {started or "VA to add"}
Tasks: closing gift (VA, today), thank-you call (Charles, tomorrow), review request (VA, Day 7)
Anniversary event created for {closing_date} yearly.
Scorecard: closed unit logged, source {Src tag}.
```

## Error handling / fallback
- Tag update action not available: VA runs the tag checklist in SOP-08 within one hour of the Closed stage move. The Slack alert lists exactly which tags to add and remove.
- Delay step limits (Zapier delays max 30 days on some plans): Day 7 is within limits. If not, create the review task with a Day 7 due date instead.
- Client closed both a sale and a purchase: run once per Opportunity; the second run finds tags already correct. Two anniversary events are fine.
- Contact missing email: review request goes by text from Command; VA adjusts.

## Test checklist
- [ ] Move a test Opportunity to Closed; contact shows `Past Client`, no `Active`/`Under-Contract`/`Buyer`/`Seller`.
- [ ] `SP-Past Client Program` started; under-contract plan removed.
- [ ] Three tasks created with correct owners and due dates.
- [ ] Yearly calendar event exists with both invitees.
- [ ] Closed tab row with price and source.
- [ ] Capital partner test keeps `Capital-Partner` and `SP-Capital Partner Program`.

## Build time estimate
2.5 hours.
