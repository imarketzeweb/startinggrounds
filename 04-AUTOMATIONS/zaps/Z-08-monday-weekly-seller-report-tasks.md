# Z-08  Monday 7am → Weekly Seller Report Tasks

## Name
`Z-08 Monday 7am → Weekly Seller Report Tasks`

## Purpose
Service standard 2: every active seller gets a written update every Monday. This Zap makes sure nobody forgets a seller. At 7:00am every Monday it creates one "Weekly Seller Report" task per Active seller Opportunity, with the data-pull checklist and the deadline chain: VA gathers numbers by 10am, `CB Seller Concierge` drafts, Charles approves by 12pm, sent by 3pm.

## Trigger
- **Schedule by Zapier: Every Week**, Monday, 7:00am local time.

## Steps

1. **Google Sheets: Get Many Spreadsheet Rows** from `Active Listings` where `Stage` = Active or Coming Soon (Coming Soon sellers also get a Monday note). Preferred if available: **KW Command: Find Opportunities** filtered to Seller pipeline, stage Active (verify search action exists; the sheet is the reliable source).
2. **Looping by Zapier: Create Loop from Line Items** over the rows.
3. Inside the loop, **Formatter: Date** compute `report_week` = this Monday's date and `days_on_market` = today minus live date.
4. **KW Command: Create Task** assigned to VA, due Monday 10:00am (verify action; fallback: Google Tasks, or one Slack checklist post listing every seller).

   | Source field | Destination field |
   |---|---|
   | "Weekly Seller Report: {address} ({seller_name})" | Task title |
   | Monday 10:00am | Due |
   | VA | Assignee |
   | checklist text below | Description |
   | Opportunity link | Related Opportunity |

   Description text:
   ```
   Pull by 10am (see 05-SELLER-SYSTEM/weekly-seller-report-template.md):
   - MLS views and saves (this week / total)
   - Zillow, Realtor.com views and saves
   - Showings this week / total, and feedback verbatim from ShowingTime
   - Open house attendance and sign-ins (Lead Log, Src-OpenHouse)
   - Sign QR inquiries (Lead Log, Src-Sign)
   - Social reach on this listing's posts
   - New competing listings, price changes, pendings within 1 mile
   - Days on market: {days_on_market}
   Then run CB Seller Concierge with the numbers, post draft to #listings by 11am.
   ```
5. **KW Command: Create Task** for Charles, due Monday 12:00pm: "Approve seller report: {address}".
6. After the loop, **Slack: Send Channel Message** to `#listings` (template below).
7. **Google Sheets: Create Row** in `Seller Report Log` for each listing with status `Pending` (VA marks `Sent` with the time; this feeds the scorecard).

## Filters / Paths
- Zero active listings: skip the loop and post `No active sellers this week.` to `#listings`.
- Listing under contract: excluded here; `SP-Seller Under Contract` milestone messages cover those clients, and Charles's Tuesday calls stay.
- Holiday Monday: the Zap still fires. Charles decides whether the report goes Monday or Tuesday; the standard is Monday.

## ChatGPT step
None inside the Zap. The narrative is drafted by the VA in `CB Seller Concierge` because the numbers are gathered by hand from several portals. If you later build a scraper or the portals expose data, add the OpenAI step between 4 and 5 with the prompt from `05-SELLER-SYSTEM/weekly-seller-report-template.md`.

## Alert message template (Slack `#listings`)
```
:calendar: MONDAY SELLER REPORTS  |  {report_week}
{count} active listings:
- {address} ({seller_name}) DOM {days_on_market} → VA task due 10am, Charles approval due 12pm
- ...
Standard: every seller has a written update by 3pm today. Log send time in Seller Report Log.
```

## Error handling / fallback
- Sheet stale (listing closed but still Active): the VA fixes the row when the task is obviously wrong and closes the task with note "closed". SOP-07 and SOP-08 require updating the sheet at every stage change.
- Command task action missing: Zapier posts the checklist per listing into `#listings` as separate threads; VA works from those threads.
- Zap fails on Monday: VA's daily checklist has "Monday 8:00: confirm Z-08 tasks exist; if not, create manually from Active Listings."

## Test checklist
- [ ] Run the Zap manually on a weekday with two test rows in Active Listings.
- [ ] Two VA tasks and two Charles tasks created with correct due times and Opportunity links.
- [ ] Description checklist renders fully.
- [ ] Slack summary lists both listings with DOM.
- [ ] Seller Report Log has two Pending rows.
- [ ] Zero-listing test posts the "No active sellers" message.

## Build time estimate
1.5 hours.
