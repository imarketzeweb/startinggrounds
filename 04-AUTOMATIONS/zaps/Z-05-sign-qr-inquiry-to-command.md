# Z-05  Sign QR Inquiry → Command + Listing Link

## Name
`Z-05 Sign QR Inquiry → Command + Listing Link`

## Purpose
A drive-by scans the QR code on the yard sign or rider, lands on the single-property page on charlesbrewer.guru, and submits the "Ask about this home" form. That lead gets created in Command with `Src-Sign`, a note linking it to the listing's Opportunity, `SP-Speed to Lead`, and an alert. Sign leads are usually buyers for that house or neighbors who will sell next, so the alert names the listing and the seller so Charles can respond in context.

## Trigger
- **Website form tool: New Form Submission** on the single-property page form. Required fields: first_name, last_name, phone, email, message, plus hidden `property_address`, `listing_id` (the Command Opportunity name or an internal ID), `utm_source` (= `sign` when the QR code is used; = `social` when the link came from a post).
- If the form tool has no trigger: **Webhooks by Zapier: Catch Hook**.

## Steps

1. **Filter:** continue only if `utm_source` = sign or `qr` (social-sourced submissions from the same page are routed to Z-03 logic by a second Zap or a Path; keep source tags honest).
2. **Formatter:** capitalize names, E.164 phone.
3. **Google Sheets: Lookup Row** in `Active Listings` sheet by `property_address` to pull: seller name, listing Opportunity link, list price, open house date, showing instructions. (The VA keeps this sheet current in SOP-03.)
4. **KW Command: Find or Create Contact** (verify action).

   | Source field | Destination field |
   |---|---|
   | first_name, last_name | First Name, Last Name |
   | email, phone | Email, Mobile Phone |
   | "Src-Sign", "New-Lead", "Haven't Met", "Buyer" | Tags |
   | "Sign QR inquiry on {property_address}. Listing Opportunity: {opportunity_link}. Message: {message}" | Note |

5. **KW Command: Add to SmartPlan** → `SP-Speed to Lead` (fallback: VA).
6. **KW Command: Create Opportunity** on Buyer pipeline, `Cultivate`, named `[Last Name] - Buyer - Sign [Address]`. Command may not support linking two Opportunities; the note in step 4 is the link.
7. **KW Command: Add Note to Opportunity** on the listing (seller) Opportunity: "Sign inquiry from {name} {phone} on {date}" (verify action; fallback: VA adds it, and it shows in Monday's seller report as sign traffic).
8. **Slack: Send Channel Message** to `#leads` (template below).
9. **SMS by Zapier** to Charles and VA: `SIGN LEAD on {property_address}: {name} {phone}. #leads. 5-min clock.`
10. **Google Sheets: Create Row** in `Lead Log`, Source = Sign, Property = address. Also increment the listing's sign-inquiry count for the seller report.

## Filters / Paths

| Condition | Action |
|---|---|
| message contains "sell", "my home", "what's mine worth" | Add `Seller` tag instead of `Buyer`, Seller pipeline Opportunity, note "Neighbor / potential seller" |
| message contains "agent" and "I have" | Keep contact, no Opportunity, alert says "has agent" |
| property not found in Active Listings sheet | Alert `LISTING NOT FOUND: VA update sheet`, continue with contact creation |

## ChatGPT step
None. Z-02 drafts the reply from the Slack alert. The alert includes listing context so the draft is specific.

## Alert message template (Slack `#leads`)
```
:round_pushpin: SIGN LEAD  |  {property_address}  |  untriaged
Name: {first_name} {last_name}
Phone: {phone}  |  Email: {email}
Message: "{message}"
Listing: {list_price}  |  Seller: {seller_name}  |  Next OH: {open_house_date}
Showing instructions: {showing_instructions}
Command contact: {contact_link}  |  Listing Opp: {opportunity_link}
Clock started: {zap_meta_human_now}. Human reply due by +5 min.
```

## Error handling / fallback
- No UTM on the form (someone typed the URL): source defaults to `Src-Website`; Z-01 handles it. Make sure the QR code URL always carries `?utm_source=sign&utm_medium=qr&utm_campaign=[Address]`.
- Lookup fails: contact still created; VA fixes the sheet and adds the listing note.
- Command Opportunity note action missing: VA adds sign inquiries to the listing Opportunity during Monday data pull (SOP-05).

## Test checklist
- [ ] Scan a test QR code, submit the form; contact created with `Src-Sign`.
- [ ] Note contains the listing Opportunity link.
- [ ] Buyer Opportunity created; seller-language test creates a Seller Opportunity instead.
- [ ] Alert shows list price, seller name, and showing instructions from the sheet.
- [ ] SMS received.
- [ ] Lead Log row with Property filled.

## Build time estimate
2 hours, plus 15 minutes per listing to add the sheet row and generate the QR code (SOP-03 covers that).
