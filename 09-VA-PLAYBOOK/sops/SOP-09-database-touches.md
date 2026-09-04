# SOP-09  Database Touches (33 Touch and 12 Direct)

## Purpose
Execute the MREA database plan every month: 33 Touch for the `Met` database (`SP-33 Touch (Met)`), 12 Direct for the `Haven't Met` database (`SP-12 Direct (Haven't Met)`), and the monthly capital partner note (`SP-Capital Partner Program`). The SmartPlans hold the copy and the schedule; this SOP is how the VA turns each month's steps into sent emails, ordered mail, and prepared calls, on time, with real numbers.

## Trigger
- The 1st of each month (prep for the month), plus the individual SmartPlan tasks as they come due.

## Steps
1. **Day 1 to 3: pull the month.** Open `04-AUTOMATIONS/command-smartplans/SP-33-Touch-Met.md`, `SP-12-Direct-Havent-Met.md`, and `SP-Capital-Partner-Program.md`. List every step due this month with its channel (Email, Text, Call task, Mail task). Put them on the month's touch calendar in `#ops` (pinned) with dates and owners.
2. **Numbers.** Update the monthly market report numbers (median price, days on market, inventory, rates, recent sales by area) in the `Market Numbers` sheet from the MLS and the KW market report. Every email placeholder this month is filled from that sheet, never from memory. Charles approves the numbers once; after that the emails only need a read-through.
3. **Emails (33 Touch).** For each email step: fill placeholders in the Command SmartPlan step (if Command allows editing the step copy per send) or in the Command email template; post the filled version in `#ops` for Charles's approval; schedule the send in Command for the plan date. Emails marked "VA sends" in the SmartPlan go after a read-through. Log replies daily as notes; anything that sounds like a move is a lead (`SOP-01`, `Src-Sphere` or `Src-Referral`).
4. **Texts.** Fill and post for approval as a batch; send from Command on the plan date. Reply to every response within the hour and log.
5. **Call tasks.** Build Charles's call list for the month's call touch: name, phone, last note, a one-line prompt. Deliver as a Command task list and a Google Sheet tab, in batches of 15 per day across the call week. Log the outcomes he reports.
6. **Personal notes.** For handwritten-note steps: prepare the list with a one-line prompt per person from Command notes (job, kids, hobby, last conversation), stamped envelopes, and cards on Charles's desk (or mailed to him) by the 10th. He writes; you mail and log.
7. **Items of value and holiday cards (33 Touch mail).** Export the `33-Touch` list (name, address) from Command by the 3rd; check addresses; order with the mailing house (or print in-house for small counts) to arrive on the plan date. Files: design in Command Designs or Canva per the brand kit. Log the order and cost.
8. **12 Direct postcard.** Export the `12-Direct` list by the 3rd; remove anyone tagged `Dead` or with two returned mailers; confirm the month's card headline, body, and stat with Charles (the stat comes from the `Market Numbers` sheet; Charles signs off). Add the QR code with `utm_source=mail&utm_medium=postcard&utm_campaign=12direct-[YYYY-MM]` and the keyword ("LIST", "VENDOR"). Order by the 5th to arrive by the 15th. Log count and cost. Keyword responses and QR leads are processed via `SOP-01` with the source corrected to the mailer.
9. **Capital partner note.** First Wednesday: pull from the `Deal Board` the deals looked at and passed on this month (address area and the number that killed each) and deals in progress. Run `CB Investor Analyst` with the monthly partner note prompt; post for Charles's approval; send from Command to `Capital-Partner` contacts on the plan date. Never include projected returns.
10. **Birthdays and anniversaries.** Weekly: pull next week's birthdays and home anniversaries from Command; add Charles's call tasks; mail cards a week ahead. Log.
11. **Returns and bounces.** Mark returned mail in Command (note "returned [date]"); after two returns, tag `Dead` with reason "bad address" and remove from `12-Direct`. Email bounces: fix or mark; two hard bounces, remove email and rely on mail.
12. **Report.** Monthly: touches sent by channel, mailer counts and cost, replies received, leads generated from database touches (`Src-Sphere`, `Src-Referral`, mailer QR), into the scorecard and the first-Friday meeting.

## Done-when
- Every touch due this month is sent, mailed, or on Charles's call list on the plan date; numbers came from the `Market Numbers` sheet; mail ordered by the 5th; replies logged; the monthly touch report is on the scorecard.

## Time
- 6 to 8 hours per month plus 15 minutes per day for replies and logging.

## Tools
- KW Command (SmartPlans, Campaigns, tasks, exports), `Market Numbers`, `Deal Board`, `Capital Partners` sheets, Command Designs / Canva, mailing house portal, `CB Investor Analyst`, `CB Ops Manager` (for reworking copy), Slack `#ops`.

## Escalate-if
- A market number looks wrong or the source is unclear: ask before it goes in any email or card.
- A reply raises a price question, a complaint, or a legal matter: Charles.
- The mailing house cannot hit the date: tell Charles; he decides to delay or switch to email for that touch.
- Brokerage advertising rules for a card (logo, office, license number) are unclear: ask before ordering.
