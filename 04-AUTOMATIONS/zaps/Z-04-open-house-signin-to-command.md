# Z-04  Open House Sign-in → Command + 8x8

## Name
`Z-04 Open House Sign-in → Command + 8x8`

## Purpose
Every open house visitor becomes a Command contact the same day with `Src-OpenHouse`, the listing they visited, and `SP-8x8 New Contact` running, and Charles gets a same-day text draft to approve while the visit is fresh. Open house leads are the highest-converting leads in the MREA model when followed up the same day.

## Trigger
- Preferred: **KW Command Open House app** sign-in. Command's Open House app writes contacts directly into Command; check whether your account exposes a "New Contact" or "Contact Tagged" trigger in Zapier to catch them. If it does, trigger on new contact where the note or source contains "Open House".
- Fallback (recommended as the primary until verified): **Google Forms: New Form Response** on the form `Open House Sign-in [ADDRESS]` (fields: first_name, last_name, phone, email, working_with_agent (Yes/No), timeline, interested_in_this_home (Yes/Maybe/No), notes). The VA creates one form per open house from a template (SOP-06). An iPad in kiosk mode runs it at the door.

## Steps

1. **Formatter:** capitalize names, E.164 phone.
2. **Lookup:** **Google Sheets: Lookup Row** in `Open House Schedule` sheet by form name to get `[ADDRESS]`, listing Opportunity link, and open house date.
3. **KW Command: Find or Create Contact** (verify action).

   | Source field | Destination field |
   |---|---|
   | first_name, last_name | First Name, Last Name |
   | email, phone | Email, Mobile Phone |
   | "Src-OpenHouse", "New-Lead", "Met", type tag (see Paths) | Tags |
   | "Open house {date} at {address}. Working with agent: {working_with_agent}. Timeline: {timeline}. Interested in this home: {interested}. Notes: {notes}" | Note |

   Note: open house visitors have met Charles in person, so relationship tag is `Met`, not `Haven't Met`.

4. **KW Command: Add to SmartPlan** → `SP-8x8 New Contact` (fallback: VA adds in SOP-06). Do not also add `SP-Speed to Lead`; the same-day text below replaces it.
5. **Paths:** if `interested_in_this_home` = Yes or `timeline` = 0-30 days → **KW Command: Create Opportunity** on Buyer pipeline at `Cultivate`, named `[Last Name] - Buyer - OH [Address]`.
6. **ChatGPT (OpenAI) by Zapier** same-day text draft (prompt below).
7. **Slack: Send Channel Message** to `#leads` (template below).
8. **Google Sheets: Create Row** in `Lead Log`, Source = OpenHouse, and in the open house's own sheet for the seller report.

## Filters / Paths

| Condition | Type tag | Action |
|---|---|---|
| working_with_agent = Yes and interested = No | `Sphere` | Contact + 8x8 only, no Opportunity, no text draft |
| working_with_agent = No | `Buyer` | Full flow |
| notes contain "sell" or "my house" | `Seller` (add `Buyer` note) | Also create Seller Opportunity |

## ChatGPT step

Prompt (System: "You are CB Lead Responder for Charles Brewer, KW agent in [MARKET]. Warm, brief, Fair Housing safe. Output JSON only."):

```
Draft a same-day thank-you text to an open house visitor.
Visitor first name: {first_name}
Property: {address}
Interested in this home: {interested}
Timeline: {timeline}
Working with an agent: {working_with_agent}
Notes from sign-in: {notes}

Rules: under 280 characters. Thank them for coming today. Reference the home by street name. One question that matches their answers (if interested: offer a private second look; if not interested: ask what they are looking for; if working with an agent: just thank them, no question). Sign -Charles.
Return: {"sms_draft":"","reason":""}
```

Expected output:
```json
{"sms_draft":"Hi Dana, Charles Brewer here. Thanks for stopping by Maple Ave today. You mentioned wanting to move by spring. Want me to send a few homes like this one before they hit the market? -Charles","reason":"Interested = Maybe, timeline 30-90 days, no agent."}
```

## Alert message template (Slack `#leads`)
```
:house: OPEN HOUSE SIGN-IN  |  {address}  |  {date}
Name: {first_name} {last_name}
Phone: {phone}  |  Email: {email}
Agent: {working_with_agent}  |  Interested: {interested}  |  Timeline: {timeline}
Notes: "{notes}"
Command: {contact_link}  |  SP-8x8 New Contact: {started or "VA to add"}

Same-day text draft:
{sms_draft}
React :white_check_mark: and VA sends from Command by 7pm today. DRAFT for human review. Not sent.
```

## Error handling / fallback
- No wifi at the open house: the Google Form queues offline in the browser; entries sync when connected. Paper sign-in sheet as backup; VA types entries into the same form that evening.
- Command Open House app used instead: VA checks Command the same evening, adds the tags and SmartPlan manually (SOP-06), and posts sign-ins to `#leads` so the text drafts still get made.
- Lookup fails (form not in schedule sheet): alert says `ADDRESS UNKNOWN`; VA fixes the sheet.

## Test checklist
- [ ] Submit a test sign-in from the iPad form; contact appears with `Src-OpenHouse` and `Met`.
- [ ] `SP-8x8 New Contact` started or alert says VA to add.
- [ ] Interested = Yes creates a Buyer Opportunity.
- [ ] Working with agent = Yes skips the text draft.
- [ ] Text draft is under 280 characters and references the street.
- [ ] Row lands in the open house sheet for Monday's seller report.

## Build time estimate
2 hours plus 30 minutes to build the sign-in form template.
