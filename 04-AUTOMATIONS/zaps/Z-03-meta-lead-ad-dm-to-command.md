# Z-03  Meta Lead Ad / DM → Command + Speed to Lead

## Name
`Z-03 Meta Lead Ad / DM → Command + Speed to Lead`

## Purpose
Instagram and Facebook leads get the same 5-minute treatment as website leads. Meta Lead Ads has a native Zapier trigger. Instagram and Facebook DMs do not reliably expose a Zapier trigger, so DMs are captured by the VA with a one-click Slack shortcut or a short Google Form, which then flows through this same Zap.

## Trigger
- Path 1: **Facebook Lead Ads: New Lead** (covers Instagram lead forms run through Meta Ads Manager). Verify the page and form are selected in the Zapier connection.
- Path 2: **Google Forms: New Form Response** on the form `DM Lead Capture` (fields: platform, handle, first_name, last_name, phone, email, what they asked, which post, timeline). The VA fills this in under 60 seconds when a DM turns into a lead (SOP-04). Alternative: a Slack Workflow form posting to `#leads` with the same fields, triggering on **Slack: New Message** with prefix `DM LEAD`.

## Steps

1. **Paths by Zapier:** Path 1 = Lead Ads, Path 2 = DM form.
2. **Formatter:** capitalize names, E.164 phone, lowercase email.
3. **KW Command: Find or Create Contact** (verify action).

   | Source field | Destination field |
   |---|---|
   | first_name / full_name split | First Name, Last Name |
   | email | Email |
   | phone_number | Mobile Phone |
   | "Src-Social", "New-Lead", "Haven't Met", type tag (see Paths) | Tags |
   | "Social lead. Platform: {platform}. Form/Post: {form_name or post}. Handle: @{handle}. Asked: {question}. Timeline: {timeline}" | Note |
   | ad_name / campaign_name | Note (Lead Ads only) |

4. **KW Command: Add to SmartPlan** → `SP-Speed to Lead` (fallback: VA adds in SOP-01).
5. **KW Command: Create Opportunity** → stage `Cultivate` on the pipeline matching the type tag. Sphere or unknown: no Opportunity, VA decides.
6. **Slack: Send Channel Message** to `#leads` (template below). This message also triggers Z-02.
7. **SMS by Zapier** to Charles and VA: `NEW social lead ({platform}): {name} {phone}. #leads. 5-min clock started.`
8. **Google Sheets: Create Row** in `Lead Log` with Source = Social.

## Filters / Paths

| Condition | Type tag | Pipeline |
|---|---|---|
| Lead Ads form name contains "Sell" or "Home Value" | `Seller` | Seller |
| Lead Ads form name contains "Buy" or "Search" | `Buyer` | Buyer |
| Lead Ads form name contains "Invest" | `Investor` | Investor |
| DM form field `lead_type` (VA selects) | as selected | as selected |
| Anything else | `Sphere` | none |

Skip if email or phone missing on both fields (Lead Ads occasionally sends blanks): post to Slack with `INCOMPLETE LEAD: reply to the DM to get contact info` and stop.

## ChatGPT step
None here. Z-02 handles drafting off the Slack alert.

## Alert message template (Slack `#leads`)
```
:rotating_light: NEW {type} LEAD  |  Social ({platform})  |  untriaged
Name: {first_name} {last_name}  (@{handle})
Phone: {phone}  |  Email: {email}
Post / Form: {post_or_form}
Timeline: {timeline}
Message: "{question}"
Command: {contact_link or "VA to create"}
Clock started: {zap_meta_human_now}. Human reply due by +5 min. Reply in the DM first, then log.
```

## Error handling / fallback
- Meta Lead Ads trigger stops (token expiry is common): Zapier emails an error. VA checks Meta Ads Manager leads export every morning (SOP-01) until reconnected. Reconnect the Facebook account in Zapier.
- Command step fails: Email by Zapier to Command's "add contact via email" address (verify enabled) plus the Slack alert. VA completes in Command.
- DMs: no automation reads DMs. The 1-hour DM reply rule in SOP-04 is the real safeguard. The form is only for logging the lead into Command.

## Test checklist
- [ ] Use Meta's Lead Ads Testing Tool to send a test lead; confirm it reaches Command with `Src-Social`.
- [ ] Submit a DM Lead Capture form entry; confirm the same result.
- [ ] Opportunity in Cultivate on the right pipeline.
- [ ] Slack alert posts and Z-02 thread reply follows.
- [ ] SMS received by Charles and VA.
- [ ] Blank-contact test posts the INCOMPLETE message and does not create a contact.

## Build time estimate
2 hours (Lead Ads) plus 30 minutes for the DM form.
