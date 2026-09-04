# Z-10  Friday 4pm → Scorecard Summary

## Name
`Z-10 Friday 4pm → Scorecard Summary`

## Purpose
Every Friday at 4pm Charles gets the week's numbers with a short written read from `CB Ops Manager`: what moved, what is off pace against the MREA funnel targets, and the one thing to fix next week. The VA has entered the numbers into the KPI sheet by 3pm (SOP-10). This Zap reads, summarizes, and delivers. It does not compute the numbers; the sheet does.

## Trigger
- **Schedule by Zapier: Every Week**, Friday, 4:00pm local time.

## Steps

1. **Google Sheets: Lookup Row** in `KPI Scorecard` (from `10-SCORECARD/kpi-scorecard.md`) where `Week Ending` = this Friday. Also lookup the previous week's row and the `Targets` row.
2. **Filter:** if `Status` column is not `Complete`, skip the summary and Slack `#ops`: `Scorecard not marked Complete by 4pm. VA: finish SOP-10 and re-run Z-10 manually.`
3. **ChatGPT (OpenAI) by Zapier: Conversation** with the prompt below.
4. **Gmail / Email by Zapier: Send Email** to `[EMAIL]` (Charles) subject `Friday Scorecard: week ending {date}` with the summary and a link to the sheet.
5. **Slack: Send Channel Message** to `#ops` with the same summary.
6. **Google Docs: Append Text** to `Friday Review Log` doc so Charles has a running record for the monthly review.

## Field mapping (sheet → prompt)

| Sheet column | Prompt field |
|---|---|
| New leads (by source: Website, Social, OpenHouse, Sign, Referral, Sphere, Paid, Investor-List, Event) | leads_by_source |
| Leads responded within 5 min (%) | speed_to_lead_pct |
| Appointments set / met (seller, buyer, investor) | appts |
| Listings taken / Active listings / Under contract / Closed units / Closed volume / GCI | pipeline |
| Seller reports sent on time (%) | seller_reports_pct |
| Database size: Met / Haven't Met / Past Client; 33 Touch and 12 Direct touches sent | database |
| Social posts published / reach / DMs answered within 1 hr (%) | social |
| Reviews received | reviews |
| Targets row (weekly targets derived from the annual goal) | targets |

## ChatGPT step

Prompt (System: "You are CB Ops Manager for Charles Brewer, KW, [MARKET]. Direct, numerate, no fluff. Compare to targets and to last week. Never invent numbers."):

```
Write the Friday scorecard summary.

This week (ending {week_ending}): {this_week_row as key: value list}
Last week: {last_week_row}
Weekly targets: {targets_row}

Format:
1. Headline (one sentence: on pace / off pace and why)
2. Funnel table: leads, appts set, appts met, agreements signed, closings, each with actual / target / last week
3. Three wins (specific, with numbers)
4. Three gaps (specific, with numbers, and the SOP or Zap that owns the fix)
5. Service standards check: 5-min response %, Monday reports %, DM replies %
6. One thing to fix next week (single sentence, assign to Charles or VA)
Under 300 words. Plain text.
```

Expected output: plain text in the six-part format above.

## Alert message template (Slack `#ops` and email)
```
:bar_chart: FRIDAY SCORECARD  |  week ending {week_ending}
{gpt_summary}
Sheet: {sheet_link}
Charles: reply here with next week's focus by Monday 8am. VA adds it to Monday huddle.
```

## Error handling / fallback
- Row not found: alert `No scorecard row for {date}. VA: add the row.`
- OpenAI fails: send the raw row as a table in the email; Charles reads numbers without the narrative.
- Numbers look wrong (e.g. leads = 0 with a Lead Log full of rows): the prompt cannot catch this reliably. SOP-10 has the VA cross-check Lead Log count against the scorecard before marking Complete.

## Test checklist
- [ ] Fill a test week row and mark Complete; run the Zap manually.
- [ ] Email and Slack arrive with the six-part summary.
- [ ] Summary numbers match the sheet exactly.
- [ ] Incomplete row test sends the VA reminder instead.
- [ ] Friday Review Log doc appended.

## Build time estimate
2 hours after the KPI sheet exists.
