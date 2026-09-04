# SOP-05  Weekly Seller Report

## Purpose
Service standard 2: every active seller gets a written update every Monday: traffic, feedback, showings, market movement, next step. Sent whether the news is good or bad. Z-08 creates the tasks; this SOP is the work. Template and GPT prompt live in `05-SELLER-SYSTEM/weekly-seller-report-template.md`.

## Trigger
- Monday 7:00am: Z-08 creates one "Weekly Seller Report" task per Active (and Coming Soon) seller Opportunity. If the tasks are missing at 8:00, create them from `Active Listings`.

## Steps
1. **8:00 to 10:00: pull the numbers** for each listing into the report sheet (one tab per listing):
   - MLS: views, saves/favorites, this week and cumulative.
   - Zillow, Realtor.com, Redfin: views and saves (agent dashboards or the listing page).
   - Showings: count this week and total, from ShowingTime or the showing log; feedback verbatim for every showing (chase any missing feedback by text to the showing agent at 8:30; second chase 9:30).
   - Open house: attendance, sign-in count, any "interested" flags (from the open house sheet, Z-04).
   - Sign QR inquiries and single-property page visits (Lead Log `Src-Sign`, site analytics).
   - Social: reach and saves on this listing's posts this week.
   - Market: new competing listings, price changes, pendings, solds within about a mile and the same price band (MLS search saved per listing).
   - Days on market, price, and any price history.
2. **10:00 to 11:00: draft.** Run `CB Seller Concierge` with the report prompt and the numbers. Read the draft: numbers match the sheet; feedback is verbatim and attributed to "a showing agent" not a name; the "what it means" paragraph never includes a price recommendation; the next step is concrete. Add `[CHARLES: recommendation]` where a decision belongs to him. Paste the draft into the Command email as a draft (do not send) and post the text in `#listings` under the Z-08 thread for that listing: "Report draft for [ADDRESS] ready. Charles: approve by 12pm."
3. **11:00 to 12:00: chase.** Any feedback still missing: note "feedback requested, not yet received" in the report rather than waiting. Any approval not received by 12:00: direct message Charles at 12:00 and 1:30.
4. **12:00 to 3:00: send.** When Charles approves (thumbs-up or edited text), apply his edits, send from Command (email, from Charles), and add the report as an Opportunity note. Log send time in `Seller Report Log`. Sellers who prefer a call: Charles calls with the report open and you still send the written version afterward.
5. **Charles's Tuesday calls.** Post the list of sellers with listings over 14 days old in `#listings` by 9am Tuesday with DOM, showings, and the report's next step.
6. **Coming Soon sellers** get a shorter version: what was done this week, what happens next week, live date.
7. **Under Contract sellers** are not in this SOP; `SP-Seller Under Contract` and `SOP-07` cover them.
8. **Scorecard.** Friday: seller reports sent on time % into the KPI sheet from `Seller Report Log`.

## Done-when
- Every active seller has a written report sent from Command by 3pm Monday, logged with time, with an Opportunity note, and Charles's Tuesday call list is posted.

## Time
- 30 to 45 minutes per listing for the data pull and draft; 10 minutes per listing to send and log.

## Tools
- KW Command, MLS, ShowingTime (or showing log), Zillow/Realtor.com/Redfin agent dashboards, `Active Listings` and report sheets, `CB Seller Concierge`, Slack `#listings`, `Seller Report Log`.

## Escalate-if
- Feedback mentions price, a defect, or something the seller will not want to hear: Charles calls the seller before the written report goes; the report goes after the call.
- Zero showings for the week on a listing under 30 days, or two consecutive zero weeks: flag in the draft and to Charles directly; the Day 14 / Day 30 review may move up.
- A showing agent reports a possible offer coming: tell Charles immediately, not in the report.
- Charles has not approved by 2:30pm: DM him with "report will miss the 3pm standard for [ADDRESS] without your approval."
