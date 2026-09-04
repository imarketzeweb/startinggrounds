# Z-12  New Deal on Deal Board → Deal Memo Draft → Partner Match → Deal Alert

## Name
`Z-12 New Deal on Deal Board → Deal Memo → Partner Match → Deal Alert`

## Purpose
Charles sources fix-and-flip deals; capital partners fund them. When Charles or the VA adds a candidate to the `Deal Board` sheet, `CB Investor Analyst` drafts the Deal Memo into the deal's Drive folder, Charles reviews and approves every number, and only then does the Deal Alert go out via Command to the capital partners whose profile matches, with a 48-hour first-look window. Tier 1 partners get a call from Charles, not just an email.

## Trigger
- **Google Sheets: New Spreadsheet Row** on `Deal Board`. Columns: Address, Source, Asking, ARV, Rehab Est, MAO, Status, plus helper columns: Deal ID, Strategy (Flip / BRRRR / Wholesale), Min Capital, Est. Timeline (months), Target Partner Return, Approved (checkbox), Memo Link, Sent At, First-Look Ends.
- Second trigger (same Zap, second path, or a separate Zap `Z-12b`): **Google Sheets: Updated Spreadsheet Row** where `Approved` flips to TRUE.

## Steps

**Path A: new row (Status = Analyzing)**

1. **Filter:** Address, Asking, ARV, Rehab Est are all filled. If not, Slack `#ops`: `Deal Board row incomplete for {address}. Fill Asking, ARV, Rehab before the memo can draft.`
2. **Formatter:** compute check values to show the GPT: 70% rule MAO = ARV x 0.70 minus Rehab Est; spread = ARV minus Asking minus Rehab Est.
3. **Google Drive: Create Folder** `Deals/[YYYY-MM] [Address]/` with subfolders `01-Photos`, `02-Comps`, `03-Rehab-Scope`, `04-Deal-Memo`, `05-Partner-Docs`, `06-Closing`.
4. **ChatGPT (OpenAI) by Zapier** Deal Memo draft (prompt below).
5. **Google Docs: Create Document from Text** in `04-Deal-Memo`, title `Deal Memo [Address] v1 DRAFT`.
6. **Google Sheets: Update Row** Memo Link, Status = Memo Drafted.
7. **KW Command: Create Opportunity** on Investor pipeline named `Deal - [Address]`, stage `Deal Presented` is not yet right; use `Cultivate` for the deal record until a partner commits (verify action; fallback: VA). Note: the Investor pipeline tracks partners, so a deal record is optional; the Deal Board is the deal system of record.
8. **Slack: Send Channel Message** to `#ops` (template A).
9. **KW Command: Create Task** for Charles: "Review Deal Memo {address}: verify ARV, rehab, MAO; tick Approved on Deal Board" due +1 business day.

**Path B: Approved flipped to TRUE**

10. **Filter:** Approved = TRUE and Sent At is blank.
11. **Google Sheets: Get Many Rows** from `Capital Partners` sheet (mirrors Command contacts tagged `Capital-Partner`; columns: Name, Email, Command link, Tier (1/2/3), Min Deal, Max Deal, Strategies, Markets, Status Active).
12. **Partner match (Formatter / Code by Zapier):** keep partners where Status Active = Yes, Strategies contains the deal Strategy, Markets contains [MARKET] or the deal's city, Min Deal <= capital needed <= Max Deal. Output list of matched emails and Tier 1 names.
13. **KW Command: Add Tag** `Deal-{Deal ID}` to matched partner contacts (verify action; fallback: VA tags them from the Slack list). This temporary tag is the Command audience for the send.
14. **Google Docs: Get Document** approved memo; **Formatter** build the Deal Alert email body (summary section of the memo, not the whole memo).
15. **Command send.** Command's Zapier connection likely does not send an email to a tag; verify. Standard path: **Slack** to `#ops` with the ready-to-paste subject and body, and **KW Command: Create Task** for VA: "Build Command email Campaign to tag Deal-{Deal ID}, send now, first look ends {now + 48h}." The VA sends within 30 minutes (SOP-09 pattern). If a send action exists, use it.
16. **KW Command: Create Task** for Charles: "Call Tier 1 partners on {address}: {tier1 names}" due today.
17. **Google Sheets: Update Row** Sent At, First-Look Ends = Sent At + 48h, Status = Deal Presented. **Delay Until** First-Look Ends, then Slack `#ops`: `First look on {address} ended. Commitments: VA update Deal Board. Uncommitted: Charles decides whether to widen to Tier 2/3.`

## Field mapping

| Source field | Destination field |
|---|---|
| Deal Board Address, Asking, ARV, Rehab Est, MAO, Strategy, Timeline, Target Return | GPT prompt; memo Doc; alert email |
| Capital Partners Tier, Min/Max Deal, Strategies, Markets | Match filter |
| Matched partner Command links | Tag `Deal-{Deal ID}`; Campaign audience |
| Approved checkbox | Path B trigger |

## ChatGPT step

Prompt (System: "You are CB Investor Analyst for Charles Brewer, KW, [MARKET]. Charles sources fix-and-flip deals and project-manages them; capital partners fund them. Numerate, skeptical, plain English. Every number comes from the input or a stated formula; show formulas. Never invent ARV, rents, taxes, or comps. This is not investment, legal, or tax advice; say so once. End with 'DRAFT for human review. Not sent.'"):

```
Draft a one-page Deal Memo for capital partners.
Address: {address}  Source: {source}
Asking: {asking}  ARV (Charles's estimate): {arv}  Rehab estimate: {rehab}
Strategy: {strategy}  Est. timeline: {timeline} months
Capital needed (asking + rehab + 10% holding/closing): compute and show
Target partner return: {target_return}
Pre-computed: 70% MAO = {mao_calc}; gross spread = {spread}

Sections: 1. Snapshot (5 lines). 2. The numbers (table: asking, rehab, holding/closing, all-in, ARV, gross profit, margin %, partner return at target, Charles's project fee if stated). 3. Why this deal (3 bullets). 4. Risks and what would kill it (3 bullets). 5. Timeline (acquisition, rehab, list, sell). 6. Partner ask: capital amount, structure placeholder "[structure per attorney]", 48-hour first look. 7. Disclaimer.
Also produce a 120-word Deal Alert email summary with subject line for the partner email.
Return: {"memo":"","alert_subject":"","alert_body":""}
```

Expected output: JSON with the full memo as plain text plus the short alert subject and body, each ending with the DRAFT footer.

## Alert message templates (Slack `#ops`)

Template A (memo drafted):
```
:moneybag: NEW DEAL  |  {address}  |  Ask {asking}  ARV {arv}  Rehab {rehab}  MAO {mao}
Memo draft: {memo_link}  |  Folder: {folder_link}
Charles: verify every number in the Doc, then tick Approved on the Deal Board. Nothing goes to partners until then.
DRAFT for human review. Not sent.
```
Template B (approved):
```
:white_check_mark: DEAL APPROVED  |  {address}  |  {matched_count} partners matched ({tier1_count} Tier 1)
Subject: {alert_subject}
{alert_body}
VA: Command Campaign to tag Deal-{deal_id}, send now. First look ends {first_look_ends}.
Charles: call Tier 1 today: {tier1_names}.
```

## Error handling / fallback
- No partners match: alert Charles `0 partners matched {address}. Widen criteria or add partners.` Do not send to everyone.
- OpenAI fails: VA runs `CB Investor Analyst` manually with the same prompt; pastes into `04-Deal-Memo`.
- Charles edits the Doc after approval: the Doc is the source of truth; VA copies from the Doc.
- Tag action missing: VA tags matched partners from the Slack list before building the Campaign.
- Never send before Approved = TRUE. The checkbox is the human gate.

## Test checklist
- [ ] Add a test row "123 Ztest St"; folder, memo Doc, Slack A, and Charles task appear.
- [ ] Memo shows formulas and the disclaimer; capital needed computed.
- [ ] Tick Approved; matched partner list is correct against a test Capital Partners sheet with 3 partners of different tiers and ranges.
- [ ] Temporary `Deal-{id}` tag applied (or VA instruction shown).
- [ ] Charles Tier 1 call task created; First-Look Ends set to +48h.
- [ ] 48-hour follow-up Slack fires.

## Build time estimate
5 hours across both paths.
