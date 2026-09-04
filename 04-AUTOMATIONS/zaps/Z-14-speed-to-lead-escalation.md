# Z-14  Speed to Lead Escalation

## Name
`Z-14 Speed to Lead Escalation`

## Purpose
Service standard 1 says every new lead gets a human response within 5 minutes between 8am and 8pm. `SP-Speed to Lead` sends the instant acknowledgment. This Zap enforces the human part: five minutes after a lead arrives, if nobody has logged a human response, Charles gets a second, louder SMS and the VA gets a call task. Outside 8pm to 8am the check runs at 8:05am the next morning.

## Trigger
- **Slack: New Message Posted to Channel** `#leads`, filtered to messages starting with `:rotating_light: NEW` or `:round_pushpin: SIGN LEAD` or `:house: OPEN HOUSE SIGN-IN`. Every lead Zap (Z-01, Z-03, Z-04, Z-05) posts this alert, so one escalation Zap covers all sources.
- Alternative: build the delay and check as the last steps of each lead Zap. One central Zap is easier to maintain.

## Steps

1. **Formatter: Text: Extract** contact link, name, phone, source, and the Slack message timestamp.
2. **Formatter: Date/Time:** compute local hour. **Paths:** business hours (8:00 to 19:55) → Delay 5 minutes. After hours → **Delay Until** next day 8:05am.
3. **Delay by Zapier: Delay For 5 minutes** (or Delay Until).
4. **Check for a human response.** Options in order of preference; verify which is available:
   - **KW Command: Find Contact** and read last activity / last note timestamp (verify the search returns activity data).
   - **Slack: Find Message** in the lead's thread for a reply from Charles or the VA containing "called", "texted", "replied", or the :white_check_mark: reaction (the SOP-01 rule: log the human response in the thread with one of those words).
   - **Google Sheets: Lookup Row** `Lead Log` column `Human Response At` (VA fills it as part of SOP-01).
5. **Filter:** continue only if no human response found.
6. **SMS by Zapier / Twilio** to Charles: `ESCALATION: {name} ({source}) has had no human reply in 5 min. {phone}. Call now or reply "VA" and [VA NAME] takes it.`
7. **KW Command: Create Task** for VA: "CALL {name} now, no human response logged. {phone}" due immediately (fallback: Slack mention).
8. **Slack: Send Channel Message** as a thread reply on the original alert (template below), with `@channel`.
9. **Delay 10 more minutes**, re-check (steps 4 and 5). If still nothing: SMS to Charles and VA: `15 MIN: {name} still unanswered. Standard broken. Log the reason in the thread.` and **Google Sheets: Update Row** `Lead Log` column `5-min miss` = Yes (feeds the scorecard's speed-to-lead %).

## Field mapping

| Source field | Destination field |
|---|---|
| Slack alert name, phone, source, contact link | SMS text; task title; thread reply |
| Slack message ts | Thread reply target; clock start |
| Human response evidence | Filter; Lead Log `Human Response At` |

## Filters / Paths

| Condition | Behavior |
|---|---|
| Alert contains "has agent" or "INCOMPLETE LEAD" | Skip escalation |
| Alert source is OpenHouse and hour is after 6pm | Delay until 8:05am (open house drafts are approved same evening but the standard is next morning) |
| Charles replied "VA" to the SMS (SMS by Zapier cannot read replies; Twilio can) | Optional: second Zap on Twilio inbound SMS posts "Charles handed to VA" in the thread |

## ChatGPT step
None. Speed matters more than words here.

## Alert message template (Slack thread reply)
```
:alarm_clock: 5-MINUTE ESCALATION  @channel
{name} ({source}) has no logged human response.
Phone: {phone}  |  Command: {contact_link}
Charles texted. VA: call now, then reply in this thread with "called" or "texted" and what happened.
```

## Error handling / fallback
- The response-check method is the weak point. Until a reliable Command activity read exists, the rule is behavioral: whoever responds replies in the Slack thread with "called", "texted", or "replied" within the 5 minutes. The Zap reads the thread. SOP-01 makes this non-negotiable.
- False escalation (human responded but forgot to log): acceptable cost. The thread reply takes 5 seconds.
- Zapier delay drift: Zapier delays can run a minute late. The SMS still says 5 minutes.
- After-hours leads: the acknowledgment text and email from `SP-Speed to Lead` already went out; the escalation waits for morning.

## Test checklist
- [ ] Post a test alert in `#leads` at 10am; do nothing; escalation SMS and thread reply arrive at 5 minutes; second at 15.
- [ ] Post a test alert; reply "called" in the thread within 2 minutes; no escalation.
- [ ] Post a test alert at 9pm; escalation waits until 8:05am.
- [ ] "has agent" alert does not escalate.
- [ ] Lead Log `5-min miss` column updates on the 15-minute miss.

## Build time estimate
2 hours, plus 30 minutes to agree the "log it in the thread" habit with Charles and the VA.
