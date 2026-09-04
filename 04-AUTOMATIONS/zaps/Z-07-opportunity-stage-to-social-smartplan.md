# Z-07  Opportunity Stage Change → Social + SmartPlan + Seller Email

## Name
`Z-07 Opportunity Stage Change → Social + SmartPlan + Seller Email`

## Purpose
When a seller Opportunity moves to Coming Soon, Active, Under Contract, or Closed, the matching listing-stage social post goes to the scheduler, the correct SmartPlan starts, and a seller milestone email draft goes to Charles. The post copy already exists in the approved Marketing Kit Doc (Z-06); this Zap moves it, it does not write it.

## Trigger
- Preferred: **KW Command: Opportunity Stage Changed** (verify this trigger exists in your Command Zapier connection; some accounts expose "Updated Opportunity" only).
- Fallback: **Google Sheets: Updated Spreadsheet Row** on `Active Listings`, column `Stage`, which the VA updates when moving the stage in Command (SOP-03, SOP-07). This is the reliable version; build it first.

## Steps

1. **Filter:** pipeline = Seller and new stage is one of Coming Soon, Active, Under Contract, Closed.
2. **Google Sheets: Lookup Row** in `Active Listings` by address: Marketing Kit Doc link, photo folder link, approved-post status, seller contact, list price.
3. **Filter:** `kit_approved` = Yes. If No, stop and alert `#listings`: `Stage moved to {stage} but the Marketing Kit is not approved. No post scheduled.`
4. **Google Docs: Get Document** (Marketing Kit) and **Formatter: Text: Extract** the caption block whose header matches the stage (headers in the kit are fixed: `## Coming Soon`, `## Just Listed`, `## Under Contract`, `## Just Sold`).
5. **Paths by Zapier** by stage (table below).
6. **Buffer / Later / Metricool: Create Post** (whichever scheduler you use; each has a Zapier action). Media: the hero image URL from `01-Photos` (VA marks the hero file `00-hero.jpg`, and Zapier reads it via **Google Drive: Find File**). Status: **draft/pending** in the scheduler, not published, so the VA gives it one last look (SOP-04).
7. **KW Command: Add to SmartPlan** per path (fallback: VA).
8. **ChatGPT (OpenAI) by Zapier** seller milestone email draft (prompt below). Skip on Closed (Z-09 handles the closing email).
9. **Slack: Send Channel Message** to `#listings` with the post preview and the seller email draft.
10. **Google Sheets: Update Row** `Active Listings` with stage date and post-scheduled timestamp.

## Filters / Paths

| New stage | Listing stage post | SmartPlan | Seller email purpose |
|---|---|---|---|
| Coming Soon | `[Address]-ComingSoon-IG` and `-FB` | `SP-Seller Listing Launch` (already running from Z-06; no change) | "We're live in Coming Soon, here is what happens this week" |
| Active | `[Address]-JustListed-IG`, `-FB`, `-LI` | `SP-Seller Listing Launch` continues | "You're live, here is how showings and feedback work" |
| Under Contract | `[Address]-UnderContract-IG`, `-FB` | Remove `SP-Seller Listing Launch`; add `SP-Seller Under Contract` | "Under contract, here is the road to closing" (sent by Charles after his phone call, never before) |
| Closed | `[Address]-JustSold-IG`, `-FB`, `-LI` | handled by Z-09 | none here |

Open House posts are scheduled by the VA from the kit when an open house is booked (SOP-04); they are not stage-driven.

## ChatGPT step

Prompt (System: "You are CB Seller Concierge for Charles Brewer, KW, [MARKET]. Warm, clear, no jargon, no price opinion, no legal advice. Fair Housing safe. End with 'DRAFT for human review. Not sent.'"):

```
Write the seller milestone email for this stage.
Seller first name: {seller_first}
Address: {address}
New stage: {stage}
List price: {price}
Next scheduled items: {next_items from sheet, e.g. photos Thursday, live Friday 9am, open house Sunday 1-3}
Rules: 90-130 words. Open with what just happened. Give the 3 things that happen next with days. Close with "Questions? Call me any time" and [PHONE]. Sign Charles Brewer, Keller Williams [BROKERAGE OFFICE].
Return: {"subject":"","body":""}
```

Expected output:
```json
{"subject":"Maple Ave is officially live","body":"Hi Dana, ... DRAFT for human review. Not sent."}
```

## Alert message template (Slack `#listings`)
```
:arrow_right: STAGE: {address} → {stage}
Post queued as DRAFT in {scheduler}: {post_names}. Preview: {caption first 200 chars}
SmartPlan: {smartplan_action}
Seller email draft ({subject}):
{body}
Charles: :white_check_mark: to approve email. VA: approve post in scheduler after Charles approves here.
DRAFT for human review. Not sent.
```

## Error handling / fallback
- Trigger fires twice (stage changed then corrected): filter on `stage_changed_at` newer than the sheet's last stage date.
- Caption not found in Doc (header renamed): alert `CAPTION NOT FOUND for {stage}`; VA schedules manually from the kit.
- Scheduler action fails: post the caption and hero image link to `#listings`; VA schedules by hand (SOP-04).
- Under Contract: the email must not reach the seller before Charles has called. The Zap only drafts. Charles sends from Command after the call.

## Test checklist
- [ ] Move a test Opportunity (or sheet row) to Coming Soon; draft post appears in scheduler with hero image.
- [ ] Move to Active; Just Listed post drafted; seller email draft posted.
- [ ] Move to Under Contract; `SP-Seller Listing Launch` removed, `SP-Seller Under Contract` added (or VA instruction shown).
- [ ] Unapproved kit test stops with the not-approved alert.
- [ ] No post is ever auto-published; scheduler shows draft status.

## Build time estimate
4 hours. Add 1 hour if the Command stage trigger needs to be replaced by the sheet fallback.
