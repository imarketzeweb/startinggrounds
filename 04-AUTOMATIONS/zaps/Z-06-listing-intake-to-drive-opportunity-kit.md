# Z-06  Listing Intake Form → Drive Folder + Opportunity + Marketing Kit

## Name
`Z-06 Listing Intake Form → Drive Folder + Opportunity + Marketing Kit`

## Purpose
When the VA submits the completed Seller Intake Form (from `05-SELLER-SYSTEM/pre-listing-process.md`), everything that can be built without judgment gets built: the Drive folder structure, the Seller Opportunity at `Listing Signed`, the first pass of the Listing Marketing Kit from `CB Listing Marketer`, a Google Doc in `04-Marketing-Kit`, a Slack approval request to Charles, and the VA's launch checklist as Command tasks.

## Trigger
- **Google Forms: New Form Response** (or **Typeform: New Entry**) on `Listing Intake Form`. Required fields: seller first/last name, seller email, seller phone, street address, city, zip, beds, baths, sqft, year built, lot size, list price, target live date, key features (5 to 10 bullets), recent updates, neighborhood highlights (places, not people), showing instructions, photographer date, 3D tour date, seller's story of the home (free text), anything to avoid mentioning.

## Steps

1. **Formatter: Date: Format** `target_live_date` and today as `YYYY-MM`.
2. **Google Drive: Create Folder** `Listings/[YYYY-MM] [Street Address]/`. Then five **Create Folder** steps inside it: `01-Photos`, `02-Video`, `03-3D-FloorPlan`, `04-Marketing-Kit`, `05-Docs`.
3. **KW Command: Find or Create Contact** for the seller (usually exists already). Update tags: remove `New-Lead`/`Nurture`, add `Active`, keep `Seller`, `Met`.
4. **KW Command: Create Opportunity** (or update existing) on Seller pipeline, stage `Listing Signed`, name `[Last Name] - Seller - [Address]`. Fallback: VA moves the stage manually and pastes the folder link.

   | Source field | Destination field |
   |---|---|
   | seller name, email, phone | Contact |
   | street address, city, zip | Opportunity address |
   | list price | Opportunity value |
   | target live date | Opportunity note "Target live: ..." |
   | Drive folder URL | Opportunity note "Drive: ..." |

5. **KW Command: Add to SmartPlan** → `SP-Seller Listing Launch` (fallback: VA).
6. **ChatGPT (OpenAI) by Zapier: Conversation** with the prompt below. If your Zapier plan's OpenAI action truncates long outputs, split into two calls: (a) MLS remarks + property page copy + email blast, (b) 5-stage social captions + video scripts + neighbor script.
7. **Google Docs: Create Document from Text** in `04-Marketing-Kit`, title `[Address] Marketing Kit v1 DRAFT`, body = GPT output.
8. **Google Sheets: Create Row** in `Active Listings` (address, seller, opp link, price, folder link, live date). This sheet feeds Z-05 and Z-08.
9. **Slack: Send Channel Message** to `#listings` (template below).
10. **KW Command: Create Task** for the VA, one per launch checklist line (verify action; fallback: Google Tasks or a Slack checklist post). Tasks: confirm photographer, confirm 3D and floor plan, order sign and QR rider, build single-property page, QA marketing kit against Fair Housing checklist, load MLS draft for Charles review, schedule 5-stage social, build Command email Campaign, print open house materials.

## Filters / Paths
- If `list price` is blank: stop after folder creation and alert `PRICE MISSING: intake incomplete`. Price is Charles's decision and the kit is not drafted without it.
- If the seller contact is not found: create it and flag in Slack for tag review.

## ChatGPT step

Prompt (System: "You are CB Listing Marketer for Charles Brewer, Keller Williams, [MARKET]. Write in a confident, warm, specific voice. Describe the property and places, never people. No school quality claims, no 'perfect for families', no 'safe neighborhood'. Never invent features not in the input. Every section ends with 'DRAFT for human review. Not sent.'"):

```
Build the Listing Marketing Kit from this intake. Use the fixed order in 05-SELLER-SYSTEM/listing-marketing-kit-template.md:
1. MLS public remarks (max 1000 characters) and 3 headline options
2. Single-property page copy (headline, 150-word description, 8 feature bullets)
3. Video walkthrough script (60-90 seconds, on camera, Charles voice)
4. Five-stage social captions, each for IG/FB and LinkedIn: Coming Soon, Just Listed, Open House, Under Contract, Just Sold. Include hashtags for [MARKET].
5. Database email blast (subject + 120 words)
6. Google Business Profile post (100 words)
7. Neighbor call and door-knock script for the open house invite
8. Fair Housing self-check: list any phrase you avoided and why

Intake:
Address: {street}, {city} {zip}
Price: {price}  Beds: {beds}  Baths: {baths}  Sqft: {sqft}  Year: {year}  Lot: {lot}
Key features: {features}
Recent updates: {updates}
Neighborhood highlights (places): {highlights}
Seller's story: {story}
Do not mention: {avoid}
Target live date: {live_date}
Open house: {oh_date or "TBD"}
```

Expected output: plain text with the eight numbered sections, each ending with the DRAFT footer. Not JSON.

## Alert message template (Slack `#listings`)
```
:new: LISTING INTAKE COMPLETE  |  {address}  |  ${price}
Seller: {seller_name}  |  Target live: {live_date}
Drive folder: {folder_link}
Opportunity: {opp_link} (Listing Signed)  |  SP-Seller Listing Launch: {started or "VA to add"}
Marketing Kit v1 (GPT draft): {doc_link}
Charles: review MLS remarks and property page copy first. Comment in the Doc or reply here.
VA: launch checklist tasks created in Command ({task_count}). Do not schedule any post until Charles approves the Doc.
DRAFT for human review. Not sent.
```

## Error handling / fallback
- Drive folder already exists (re-submitted form): use **Google Drive: Find Folder** first; skip creation if found.
- OpenAI step fails: Slack alert says `GPT step failed. VA: run CB Listing Marketer manually with the intake, paste into 04-Marketing-Kit.` (SOP-03 step 6.)
- Command Opportunity action missing: VA creates Opportunity and pastes the folder link within the hour.
- Task creation missing: Zapier posts the checklist as a Slack message with checkboxes; VA copies it into Command Tasks.

## Test checklist
- [ ] Submit a test intake for "123 Ztest St"; six folders created with the right names.
- [ ] Opportunity at Listing Signed with price and folder link.
- [ ] Doc created in `04-Marketing-Kit` with all eight sections and DRAFT footers.
- [ ] Fair Housing self-check section present; no people-descriptive language in any section.
- [ ] Slack alert links all resolve.
- [ ] Nine VA tasks created.
- [ ] Blank price test stops at the folder step with the PRICE MISSING alert.
- [ ] Delete test folders, Opportunity, and Doc.

## Build time estimate
5 hours. The GPT prompt and Doc formatting take the longest. Budget another hour after the first real listing to tune the kit.
