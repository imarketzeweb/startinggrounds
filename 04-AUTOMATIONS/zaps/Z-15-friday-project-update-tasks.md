# Z-15  Friday 9am → Project Update Tasks for Every Deal in Rehab

## Name
`Z-15 Friday 9am → Project Update Tasks (Rehab Deals)`

## Purpose
Capital partners get a written project update every Friday for every deal in Rehab: budget vs. actual, schedule vs. plan, photos, next week's milestones, and any decision needed. This is the investor mirror of Z-08. The VA gathers the inputs by 11am, `CB Investor Analyst` drafts, Charles approves by 1pm, sent by 3pm. Partners who are never surprised fund the next deal.

## Trigger
- **Schedule by Zapier: Every Week**, Friday, 9:00am local time.

## Steps

1. **Google Sheets: Get Many Spreadsheet Rows** from `Deal Board` where Status = Rehab (also Acquisition Under Contract, which gets a shorter "closing progress" update). Columns used: Address, Deal ID, Budget, Spent to Date, Rehab Start, Planned Completion, Contractor, Partner tag `Deal-{Deal ID}`, Deal folder link.
2. **Looping by Zapier** over the rows.
3. **Formatter: Date** compute week number of rehab, days to planned completion, percent of budget spent.
4. **KW Command: Create Task** for VA, due Friday 11:00am (verify action; fallback: Google Tasks or a Slack checklist):

   | Source field | Destination field |
   |---|---|
   | "Project Update: {address} (Rehab wk {week})" | Task title |
   | Friday 11:00am | Due |
   | VA | Assignee |
   | checklist below | Description |

   Description text:
   ```
   Gather by 11am into the deal's Project Update form:
   - Budget: approved {budget}, spent to date (from contractor invoices in 05-Partner-Docs), change orders this week
   - Schedule: planned completion {planned}, contractor's current estimate, milestones hit this week, next week's milestones
   - Photos: 5 to 10 progress photos uploaded to 01-Photos/week-{week}, hero photo named 00-hero-wk{week}.jpg
   - Issues: anything found (permits, inspection, hidden damage) with contractor quote
   - Decisions needed from partners or Charles
   Submit the Project Update form; Z-15 drafts from it.
   ```
5. **KW Command: Create Task** for Charles: "Approve project update: {address}" due Friday 1:00pm.
6. **Slack: Send Channel Message** to `#ops` listing every deal and its deadlines (template below).
7. **Second trigger, same Zap family (`Z-15b`): Google Forms: New Form Response** on `Project Update` form. On submission: **ChatGPT (OpenAI) by Zapier** with the prompt below, **Google Docs: Create Document** `Project Update {address} {date} DRAFT` in the deal folder, **Slack** to `#ops` with the draft, and **KW Command: Create Task** for VA: "After Charles approves: send Project Update via Command Campaign to tag Deal-{deal_id} by 3pm; log Sent in Project Update Log."
8. **Google Sheets: Create Row** `Project Update Log` (deal, week, status Pending; VA marks Sent with time). Feeds the scorecard.

## Filters / Paths
- Zero deals in Rehab: post `No rehab projects this week.` and stop.
- Status = Acquisition Under Contract: shorter template (closing date, inspection, financing, what partners need to sign).
- Budget spent > 90% with completion < 75%: add `:warning: BUDGET WATCH` to the Slack line and to Charles's task title.

## ChatGPT step

Prompt (System: "You are CB Investor Analyst for Charles Brewer, KW, [MARKET], writing a weekly project update to capital partners on a fix-and-flip. Clear, honest, numerate, no spin. Report bad news plainly with the plan to fix it. Never invent numbers. End with 'DRAFT for human review. Not sent.'"):

```
Write the Friday Project Update for capital partners.
Address: {address}  Rehab week: {week} of {planned_weeks}
Budget: approved {budget}, spent to date {spent}, change orders this week: {change_orders}
Schedule: planned completion {planned}, contractor's current estimate {current_estimate}
Milestones hit this week: {hit}
Next week's milestones: {next}
Issues found: {issues}
Decisions needed: {decisions}
Photos: {photo_links}

Format: subject line "{address}: Week {week} update"; 4 short sections: Budget (with % spent and variance), Schedule (on time / X days behind and why), This Week / Next Week, Decisions Needed (or "None"). Then a one-line "Bottom line". Under 250 words. Plain text.
Return: {"subject":"","body":""}
```

Expected output: JSON with subject and body.

## Alert message template (Slack `#ops`)
```
:hammer_and_wrench: FRIDAY PROJECT UPDATES  |  {date}
{count} deals in Rehab:
- {address}: week {week}, {pct_spent}% of budget, completion {planned} → VA inputs due 11am, Charles approval 1pm, send by 3pm
- ...
Standard: every partner has a written update by 3pm. Log send time in Project Update Log.
```

## Error handling / fallback
- Contractor has not sent invoices: VA reports "no invoices received this week" rather than guessing; Charles calls the contractor.
- OpenAI fails: VA runs `CB Investor Analyst` manually with the form answers.
- Command cannot send to a tag from Zapier: expected; VA sends from Command.
- Deal Board status stale: VA updates status at every stage change (SOP-09 investor section).

## Test checklist
- [ ] Two test rows in Rehab; two VA tasks and two Charles tasks created with correct due times.
- [ ] Budget watch flag appears on a row with 95% spent and 50% complete.
- [ ] Submit a test Project Update form; draft Doc and Slack message appear with four sections.
- [ ] Project Update Log rows created.
- [ ] Zero-deal test posts the "No rehab projects" message.

## Build time estimate
3 hours including the Project Update form.
