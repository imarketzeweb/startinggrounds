# Z-01  Website Form → Command Contact + Speed to Lead

## Name
`Z-01 Website Form → Command Contact + Speed to Lead`

## Purpose
Every form on charlesbrewer.guru (Sell, Buy, Invest, and the generic Contact form) lands in Command as a contact with the correct type tag, `Src-Website`, `New-Lead`, `Haven't Met`, starts `SP-Speed to Lead`, creates an Opportunity in Cultivate on the matching pipeline, and wakes up Charles and the VA. This is the front door of the 5-minute standard.

## Trigger
- App: the website form tool (Command Sites form, Typeform, Gravity Forms, or Webflow, whichever the site uses). Event: **New Form Submission**.
- If the site's form tool has no Zapier trigger, use **Webhooks by Zapier: Catch Hook** and point the form's webhook at it. Last resort: Email Parser by Zapier reading the form notification email.
- Required form fields on every page: `first_name`, `last_name`, `email`, `phone`, `form_type` (hidden: Sell / Buy / Invest / Contact), `page_url`, `message`, `timeline` (dropdown: 0-30 days / 30-90 days / 90+ days), `address` (Sell only), `price_range` (Buy only), `strategy` (Invest only: Buy and hold / Flip / STR / Not sure).

## Steps

1. **Formatter by Zapier: Text: Capitalize** on first and last name. Phone: **Formatter: Numbers: Format Phone Number** to E.164.
2. **Paths by Zapier** on `form_type` (see Filters/Paths).
3. **KW Command: Find or Create Contact** (verify this action exists in your Command Zapier connection; the name may be "Create Contact" with a separate "Find Contact" search step).

   | Source field | Destination field |
   |---|---|
   | first_name (formatted) | First Name |
   | last_name (formatted) | Last Name |
   | email | Email |
   | phone (E.164) | Mobile Phone |
   | address | Address (Sell path only) |
   | "Src-Website", "New-Lead", "Haven't Met", type tag from path | Tags |
   | "Website form: {form_type} on {page_url}. Timeline: {timeline}. Message: {message}" | Note |
   | "Website" | Lead Source (if the field exists) |

4. **KW Command: Add Contact to SmartPlan** → `SP-Speed to Lead`. If the action is missing, the SmartPlan is started by the VA in SOP-01 (the alert in step 6 says so).
5. **KW Command: Create Opportunity** → pipeline by path, stage `Cultivate`, name `[Last Name] - [Type] - [Address or Price Range]`. If missing, VA creates it (SOP-01).
6. **Slack: Send Channel Message** to `#leads` (template below).
7. **SMS by Zapier** (or Twilio) to `[PHONE]` (Charles) and the VA's phone: `NEW {form_type} lead: {first_name} {last_name} {phone}. Details in #leads. 5-min clock started.`
8. **Google Sheets: Create Spreadsheet Row** in `Lead Log` (Date, Name, Type, Source, Page, Timeline, Command link). This is the scorecard feed and the CSV fallback.
9. **Delay by Zapier: Delay For 5 minutes** then hand off to the escalation logic in Z-14 (or build the Z-14 check inline here if you prefer one Zap).

## Filters / Paths

| Path | Condition | Type tag | Pipeline | Extra mapping |
|---|---|---|---|---|
| A: Sell | form_type = Sell | `Seller` | Seller | address → Address |
| B: Buy | form_type = Buy | `Buyer` | Buyer | price_range → Note |
| C: Invest | form_type = Invest | `Investor` (capital partner prospect) | Investor | strategy → Note; VA books the Criteria Call |
| D: Contact / other | anything else | `Sphere` | none (VA decides) | message → Note |

Filter before step 3: skip if `email` contains "test@" or `first_name` = "Test". Filter spam: skip if message contains "SEO" or "backlinks".

## ChatGPT step
None in this Zap. Drafting happens in Z-02 so that every new contact, from any source, gets the same treatment.

## Alert message template (Slack `#leads`)
```
:rotating_light: NEW {form_type} LEAD  |  Website  |  untriaged
Name: {first_name} {last_name}
Phone: {phone}  |  Email: {email}
Page: {page_url}
Timeline: {timeline}
Message: "{message}"
Command: {contact_link or "VA to create: SmartPlan + Opportunity not auto-created"}
Clock started: {zap_meta_human_now}. Human reply due by +5 min.
```

## Error handling / fallback
- Command step fails: Zapier's built-in Autoreplay on. Also send the payload to Command's "add contact via email" address via Email by Zapier (verify it is enabled in Command settings). The Slack alert still fires, so the VA always sees the lead.
- Duplicate contact: use Find before Create. If only Create exists, the VA dedupes daily (SOP-02).
- Missing phone: still create the contact; the Speed to Lead text step will fail silently, so the alert says "no phone: email only."
- Zap off or errored: Zapier sends error emails to `[EMAIL]` and the VA. The form tool's own notification email stays on as a backstop.

## Test checklist
- [ ] Submit one test per form type (Sell, Buy, Invest, Contact) with `first_name` = "Ztest".
- [ ] Contact appears in Command with all four tags and the note.
- [ ] `SP-Speed to Lead` shows on the contact (or the alert says the VA must add it).
- [ ] Opportunity appears in the right pipeline at Cultivate.
- [ ] Slack alert and SMS arrive within 60 seconds.
- [ ] Lead Log row appears.
- [ ] Spam filter blocks a message containing "backlinks".
- [ ] Delete the Ztest contacts from Command afterward.

## Build time estimate
3 hours including form field cleanup on the site. Add 1 hour if the form tool needs a webhook.
