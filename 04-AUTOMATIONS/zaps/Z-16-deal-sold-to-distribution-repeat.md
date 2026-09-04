# Z-16  Deal Stage Sold → Distribution Statement + Partner Review + Next Deal + Repeat

## Name
`Z-16 Deal Sold → Profit Distribution + Partner Review + Next Deal Call + Repeat`

## Purpose
When a flip sells, the partners get a profit distribution statement, a thank-you and review request, a "next deal" conversation with Charles, and their Command Opportunity moves to `Repeat`. This is the moment that turns a one-time capital partner into a repeat one. Nothing about the money is automated; the Zap creates the tasks and drafts, Charles verifies every number, the accountant or attorney handles the actual distribution.

## Trigger
- **Google Sheets: Updated Spreadsheet Row** on `Deal Board` where Status changes to Sold (VA sets this when the sale closes, SOP-08 investor section). Preferred alternative: **KW Command: Opportunity Stage Changed** to `Sold` on the Investor pipeline (verify trigger).

## Steps

1. **Filter:** Status = Sold and Sold Processed column is blank.
2. **Google Sheets: Lookup** Deal Board row: Address, Deal ID, Sale Price, All-in Cost (acquisition + rehab + holding + selling costs), Gross Profit, Partner Split %, Charles Split %, Partners list (from `Capital Partners` sheet where Deals contains Deal ID, with each partner's capital amount and share).
3. **Formatter / Code by Zapier:** compute each partner's distribution = gross profit x partner split x (partner capital / total partner capital) plus return of capital. Mark as "preliminary, subject to final closing statement and accountant review."
4. **Google Docs: Create Document** `Distribution Statement {address} DRAFT` in the deal folder `06-Closing`, one section per partner, with the closing statement link placeholder.
5. **KW Command: Create Task** for Charles: "Verify distribution statement for {address} against the final closing statement; send to [accountant] for review; approve" due closing +2 days.
6. **ChatGPT (OpenAI) by Zapier** partner closing email and review request (prompt below).
7. **Slack: Send Channel Message** to `#ops` (template below).
8. **KW Command: Create Task** for VA: "After Charles approves: send closing email + distribution statement to each partner from Command (individually, not to the tag), attach statement PDF" due closing +3 days.
9. **KW Command: Create Task** for Charles: "Next-deal call with each partner on {address}: {partner names}. Ask: same amount again, more, or pause? Update Capital Partners sheet." due closing +7 days.
10. **Delay Until** closing +10 days, then **KW Command: Create Task** for VA: "Send partner review request (Google review link) to {partner names} unless they already reviewed" and Slack reminder.
11. **KW Command: Update Opportunity** for each partner's Investor Opportunity → stage `Repeat` (verify action; fallback: VA). Keep tag `Capital-Partner`; add note "Completed deal {address}, {date}, return {x}%".
12. **KW Command: Remove Tag** `Deal-{Deal ID}` from partner contacts (the temporary audience tag from Z-12).
13. **Google Sheets: Update Row** Deal Board: Sold Processed = TRUE, Closed Date, Final Profit; **Create Row** in `Deals Closed` tab (feeds scorecard: deals sold, profit, partner returns) and update each partner's row in `Capital Partners` (Deals Completed +1, Total Returned).
14. **Z-07 already handles the Just Sold social post** when the listing Opportunity moves to Closed; make sure the flip's listing is on the Seller pipeline so that fires.

## Field mapping

| Source field | Destination field |
|---|---|
| Deal Board Sale Price, All-in, Gross Profit, splits | Distribution Doc; GPT prompt |
| Capital Partners capital per partner | Distribution per partner |
| Partner Command links | Opportunity stage `Repeat`; tag removal; tasks |
| Closed Date | Delay anchors; Deals Closed row |

## ChatGPT step

Prompt (System: "You are CB Investor Analyst writing for Charles Brewer, KW, [MARKET]. Warm, precise, grateful. Numbers only from input. Include a line that figures are preliminary until the accountant's final statement. Not tax or legal advice. End with 'DRAFT for human review. Not sent.'"):

```
Write the partner closing email for a completed flip.
Address: {address}  Sold: {sale_price} on {closed_date}
All-in cost: {all_in}  Gross profit: {gross_profit}  Project length: {months} months
Partner: {partner_first}  Capital in: {capital}  Preliminary distribution: {distribution} (return of capital + profit share)  Preliminary return: {return_pct}
Format: subject; 3 short paragraphs: what happened and thank you; the numbers with the preliminary note and where the statement is; what's next (Charles will call within a week about the next deal; a Google review would mean a lot: [review link]). Under 180 words.
Return: {"subject":"","body":""}
```

Expected output: JSON with subject and body per partner (loop the step per partner or produce one template with merge fields).

## Alert message template (Slack `#ops`)
```
:tada: DEAL SOLD  |  {address}  |  {sale_price}  |  gross profit {gross_profit} (preliminary)
Partners: {partner list with capital and preliminary distribution}
Distribution statement draft: {doc_link}
Charles: verify against closing statement, accountant review, then approve. VA: send individually from Command after approval.
Tasks: verify statement (Charles, +2d), send (VA, +3d), next-deal calls (Charles, +7d), review request (VA, +10d).
Opportunities → Repeat. Deal-{deal_id} tag removed. Scorecard updated.
DRAFT for human review. Not sent.
```

## Error handling / fallback
- Any split or capital field blank: stop and alert `Distribution inputs missing for {address}`. Never send a partial statement.
- Command Opportunity stage action missing: VA moves each partner to `Repeat` (SOP-08).
- Delay limit on Zapier plan: replace the +10 day delay with a task due date.
- Partner asks a tax question: Charles refers to the CPA; nothing in the email or memo answers it.

## Test checklist
- [ ] Set a test deal to Sold with two test partners; distribution Doc shows two sections with correct math.
- [ ] Four tasks created with the right owners and due dates.
- [ ] Closing email draft per partner posted to Slack with the preliminary note.
- [ ] Partner Opportunities at `Repeat`; `Deal-{id}` tag removed.
- [ ] Deals Closed row and Capital Partners totals updated.
- [ ] Blank-split test stops with the missing-inputs alert.

## Build time estimate
3.5 hours.
