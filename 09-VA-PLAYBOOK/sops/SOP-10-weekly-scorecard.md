# SOP-10  Weekly Scorecard

## Purpose
Every Friday by 3:00pm the week's numbers are in the `KPI Scorecard` sheet (from `10-SCORECARD/kpi-scorecard.md`), cross-checked, and marked Complete so Z-10 can send Charles the `CB Ops Manager` summary at 4:00pm. The scorecard is how Charles manages the business by numbers instead of feelings, and it is the VA's most visible weekly deliverable.

## Trigger
- Friday 1:30pm flex block (start earlier if Friday has closings or open houses).

## Steps
1. **Open the sheet.** Add the row for this `Week Ending` date (Friday) if not already there; set `Status` = In Progress.
2. **Leads by source.** From `Lead Log`: count new leads this week by `Src-*` (Website, Social, Referral, Sphere, OpenHouse, Sign, Paid, Investor-List, Event). Cross-check against Command: contacts created this week with `New-Lead`. If the counts differ by more than 1, find the missing lead and log it before continuing.
3. **Speed to lead.** From `Lead Log`: % of business-hours leads with `Human Response At` within 5 minutes; count of `5-min miss` = Yes. Note the reason for each miss in the `Notes` column.
4. **Appointments.** From Command Opportunities moved this week: seller `Appointment Set` and `Appointment Met`; buyer `Consult Set` and `Consult Met`; investor `Criteria Call` and `Partner Onboarded`.
5. **Agreements and pipeline.** Listings taken (`Listing Signed` this week), buyer agreements signed, active listings count, under contract count (buyers and sellers), closed units and closed volume this week (from the `Closed` tabs), GCI (from Charles or the commission sheet), capital partner deals: presented, committed, in rehab, sold, and preliminary profit on sold.
6. **Service standards.** Monday seller reports sent by 3pm % (`Seller Report Log`); Friday partner updates sent by 3pm % (`Project Update Log`); DMs answered within 1 hour % (scheduler inbox log or your tally); showing feedback relayed within 24 hours (tracker).
7. **Database.** Total contacts; `Met` / `Haven't Met` / `Past Client` / `Capital-Partner` counts; contacts added this week; 33 Touch and 12 Direct touches sent this week (Command send counts, mailer count); hygiene % (monthly, carry forward).
8. **Marketing.** Social posts published, reach, followers (per platform), video views, website sessions and form submissions (site analytics), reviews received (Testimonials sheet), open houses held and attendance.
9. **Operations.** Zapier errors this week and which Zaps; VA hours; tasks completed vs. created in Command.
10. **Targets and variance.** Confirm the `Targets` row is current (Charles updates it monthly from the annual goal). The sheet calculates variance; scan for anything red and write one line in `Notes` on why.
11. **Cross-check.** Before marking Complete: leads count matches Command; closed units match the Closed tabs; every % has a numerator and denominator visible in the helper columns. Blank cells get 0 with a note, never left empty.
12. **Mark Complete by 3:00pm.** Set `Status` = Complete. Z-10 fires at 4:00pm. If you finish late, run Z-10 manually from Zapier after marking Complete, or post the row in `#ops` with the `CB Ops Manager` summary run by hand from `03-CHATGPT/prompt-library.md`.
13. **1:1 at 2:00pm.** Bring the numbers you have so far; finish the rest after. Note in `#ops` any number you could not get and why.
14. **Monthly (first three business days).** Add the monthly totals row; source breakdown; database growth; hygiene %; touches by channel; costs (mailers, ads, tools). Send to Charles before the monthly meeting.

## Done-when
- Row complete, cross-checked, `Status` = Complete by 3:00pm; Z-10 summary delivered at 4:00pm; any gaps noted in `#ops`.

## Time
- 60 to 90 minutes weekly; 2 hours for the monthly close.

## Tools
- `KPI Scorecard`, `Lead Log`, `Seller Report Log`, `Project Update Log`, `Active Listings`, `Active Buyers`, `Deal Board`, `Capital Partners`, `Testimonials` sheets; KW Command reports; social scheduler analytics; site analytics; Zapier history; `CB Ops Manager`.

## Escalate-if
- A number cannot be sourced (Command report missing, analytics down): post in `#ops` before 3pm rather than estimating.
- Speed-to-lead % under 90% or any A lead missed: tell Charles directly at the 1:1, with the reasons.
- Closed volume or GCI differs from Charles's own record: flag and reconcile before marking Complete.
- A Zap has failed silently for more than a day (leads in the form tool but not in Command): tell Charles the moment you find it, then process the leads via `SOP-01`.
