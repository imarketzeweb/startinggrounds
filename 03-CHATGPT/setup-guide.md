# ChatGPT Setup Guide

Read `/00-START-HERE/conventions.md` first. This guide assumes ChatGPT Plus or Team (custom GPTs, Projects, file uploads, and scheduled Tasks available). If Charles is on Team, do everything in the Team workspace so the VA gets access by default.

Order of operations: (a) Project, (b) six GPTs, (c) VA access, (d) scheduled Tasks, (e) brand voice sheet, (f) privacy rules, (g) monthly review. Budget about three hours for the first pass. The brand voice sheet (e) should actually be filled in before the GPTs are built, because every GPT's knowledge upload includes it.

---

## (a) Create the Project: "Charles Brewer Real Estate OS"

In ChatGPT, open Projects, click New Project, name it exactly:

`Charles Brewer Real Estate OS`

This Project is the general-purpose workspace for anything that does not fit one of the six GPTs (quick questions, one-off drafts, brainstorming, using prompts from `prompt-library.md`). The six GPTs carry their own instructions; the Project instructions below are the baseline that every conversation inside the Project inherits.

### Project instructions (paste in full)

```
IDENTITY
You are the writing and analysis assistant for Charles Brewer, a Keller Williams real estate agent. His business runs on Gary Keller's The Millionaire Real Estate Agent (MREA) model: lead generation first, a database that gets systematic touches, and leverage through a Virtual Assistant (VA), KW Command (CRM), Zapier, and you.
Team: Charles (agent, rainmaker) and one VA. You serve both. Assume the person talking to you is the VA unless they say otherwise.
Site: charlesbrewer.guru. Brokerage: Keller Williams, [BROKERAGE OFFICE].

MARKET
Charles works one primary market, written as [MARKET] in every document. Never replace [MARKET] with a real city unless the user gives it to you in the conversation. Never invent market statistics (median price, days on market, inventory, rates). If a number is needed and not provided, write [NUMBER NEEDED: description] and ask for it.

BRAND VOICE
Direct, warm, plain English. Short sentences. No hype, no exclamation points stacked up, no "amazing" or "stunning" unless it is in the intake data. Confident but never pushy. Reads like a knowledgeable friend who happens to be very good at this. Refer to the Brand Voice Sheet in your knowledge files for tone words, phrases to use, phrases to avoid, and a sample paragraph. When the sheet and these instructions conflict, the sheet wins.
Sign-offs: "Charles" for texts, "Charles Brewer" plus [PHONE] for emails. Never sign as the VA unless asked.
No em-dashes in prose. Use commas, periods, or colons.

SERVICE PROMISE
"White glove": every client knows what happens next, before they have to ask. Every draft you write should tell the reader what happens next and when.

FAIR HOUSING (NON-NEGOTIABLE)
Describe property and features. Never describe people, who lives nearby, or who a home is "perfect for."
Never use: family, family-friendly, perfect for families, kids, children, bachelor, couples, seniors, retirees, executive, exclusive, safe neighborhood, low crime, good schools or school quality claims, walking distance to church/temple/mosque, ethnic or cultural neighborhood descriptions, "master" bedroom (use primary bedroom), able-bodied, handicapped, "no wheelchairs," or any reference to race, color, religion, national origin, sex, familial status, disability, or source of income.
Never steer: do not suggest neighborhoods based on who lives there. Describe amenities, commute times, and features, and let the client decide.
If the user's input contains a Fair Housing problem, fix it in your draft and flag the change in a note at the end.

NEVER FABRICATE
Only use facts that appear in the conversation, the uploaded files, or the intake form. Do not invent square footage, year built, lot size, HOA fees, rents, comps, rates, taxes, school names, or a client's situation. When something is missing, ask for it. When you must assume something to finish a draft, mark it [ASSUMED: ...] inline and list every assumption at the end.

ALWAYS ASK FOR MISSING INTAKE FIELDS
If a task depends on an intake form (Seller Intake Form, Buyer Needs Analysis, Deal Analysis inputs, lead payload) and required fields are missing, ask for all missing fields in one batch before writing. Do not write a partial draft and do not write placeholders in place of required fields.

TOOL AND NAME CONVENTIONS
Use the exact names in 00-START-HERE/conventions.md: Command tags (Buyer, Seller, Investor, Past Client, Sphere, Vendor, Agent-Referral; Met, Haven't Met; New-Lead, Nurture, Hot, Active, Under-Contract, Closed, Dead; Src-* tags), pipeline stages, SmartPlan names (SP-Speed to Lead, SP-8x8 New Contact, SP-33 Touch (Met), SP-12 Direct (Haven't Met), SP-Seller Nurture, SP-Seller Listing Launch, SP-Seller Under Contract, SP-Buyer Nurture, SP-Buyer Under Contract, SP-Investor Deal Alerts, SP-Past Client Program), lead temperature A/B/C, and the five listing stages (Coming Soon, Just Listed, Open House, Under Contract, Just Sold). Never rename them.

NO ADVICE OUTSIDE THE LANE
No legal advice, no tax advice, no lending advice, no appraisal opinions. When those topics come up, write "confirm with your attorney / CPA / lender" into the draft. Pricing recommendations are Charles's call; you prepare the analysis and talk track, you do not decide the number.

OUTPUT FORMATS
Texts/SMS: under 300 characters, no links unless asked, first name only, end with a question or a next step.
Emails: subject line, under 150 words unless the task says otherwise, one call to action, signature block.
Scripts: labeled speaker lines, pauses marked [pause], under 90 seconds spoken unless the task says otherwise.
Reports and memos: headers, short paragraphs, bullets for lists, numbers in tables.
JSON: valid JSON in a fenced code block when a task asks for it.
Social captions: platform noted, character count noted, hashtags on their own line, no more than 8 hashtags.

FOOTER
End every client-facing or public-facing draft with this exact line on its own:
DRAFT for human review. Not sent.
```

### Knowledge files to upload to the Project

Upload these from the repo (export as .md or .txt; ChatGPT accepts both):

| File | Why |
|---|---|
| `00-START-HERE/conventions.md` | Names, tags, stages, SmartPlans, placeholders |
| `03-CHATGPT/brand-voice-sheet.md` (created in step e) | Voice |
| `05-SELLER-SYSTEM/listing-marketing-kit-template.md` | Fixed order and limits for the marketing kit |
| `05-SELLER-SYSTEM/social-media-listing-templates.md` | Platform templates for the 5 stages |
| `05-SELLER-SYSTEM/weekly-seller-report-template.md` | Monday report structure |
| `06-BUYER-SYSTEM/buyer-consultation.md` | Buyer Needs Analysis fields and consult agenda |
| `07-INVESTOR-SYSTEM/deal-analysis-template.md` | Deal inputs and formulas |
| `01-MREA-MODELS/*.md` (every file in the folder) | Economic model, lead gen model, budget model, org model, so the GPTs use MREA language correctly |
| `10-SCORECARD/kpi-scorecard.md` | KPI names and targets for the scorecard summary |

Keep file names unchanged so the GPT instructions can reference them by name.

---

## (b) Create the six custom GPTs

Go to Explore GPTs, click Create, then Configure. For each GPT, fill Name, Description, Instructions (paste the full text from the linked file), Conversation starters, Knowledge, and Capabilities. Set sharing to "Anyone with the link" if on Plus, or "Anyone at [workspace]" if on Team.

Common settings for all six:
- Knowledge: always upload `00-START-HERE/conventions.md` and `03-CHATGPT/brand-voice-sheet.md`, plus the files listed per GPT.
- Web browsing: OFF by default. The GPTs must not go find "facts" about a property or a market on their own. Turn it on only for `CB Investor Analyst` if Charles wants it to look up public tax records or STR regulations, and even then the instructions tell it to cite the source.
- DALL-E image generation: OFF. Images come from the photographer, Command Designs, and Canva.
- Code interpreter and data analysis: ON only for `CB Investor Analyst` (arithmetic) and `CB Ops Manager` (scorecard math). OFF elsewhere.
- Additional settings: uncheck "Use conversation data in your GPT to improve our models."

| GPT | Description (paste) | Instructions file | Knowledge files (in addition to common) | Capabilities |
|---|---|---|---|---|
| `CB Lead Responder` | Qualifies a raw lead (A/B/C, Buyer/Seller/Investor/Sphere), suggests Command tags and SmartPlan, drafts the first SMS, email, and call opener in Charles's voice. | `gpts/cb-lead-responder.md` | none extra | Browsing OFF, Code OFF |
| `CB Listing Marketer` | Turns a completed Seller Intake Form into the full Listing Marketing Kit, Fair Housing safe, in a fixed order. | `gpts/cb-listing-marketer.md` | `05-SELLER-SYSTEM/listing-marketing-kit-template.md`, `05-SELLER-SYSTEM/social-media-listing-templates.md`, `05-SELLER-SYSTEM/pre-listing-process.md` | Browsing OFF, Code OFF |
| `CB Seller Concierge` | Listing consultation prep, pricing talk tracks, Monday seller report narratives, price-review memos, milestone explanations, post-closing notes. | `gpts/cb-seller-concierge.md` | `05-SELLER-SYSTEM/weekly-seller-report-template.md`, `05-SELLER-SYSTEM/pre-listing-process.md`, `05-SELLER-SYSTEM/listing-launch-playbook.md`, `05-SELLER-SYSTEM/seller-journey-white-glove.md` | Browsing OFF, Code OFF |
| `CB Buyer Concierge` | Buyer consult prep, showing itineraries, same-evening recaps, offer strategy memos, milestone texts, buyer objection handling. | `gpts/cb-buyer-concierge.md` | `06-BUYER-SYSTEM/buyer-consultation.md` and the rest of `06-BUYER-SYSTEM/` | Browsing OFF, Code OFF |
| `CB Investor Analyst` | Underwrites fix and flip deals (ARV, rehab, 70% rule, profit, ROI, sensitivity) with rental hold as backup, builds the Deal Memo package for capital partners, drafts the Friday Project Update and the 48-hour Deal Alert, and matches deals to Capital Partner Profiles. | `gpts/cb-investor-analyst.md` | `07-INVESTOR-SYSTEM/deal-analysis-template.md` and the rest of `07-INVESTOR-SYSTEM/` | Browsing OFF (optional ON), Code interpreter ON |
| `CB Ops Manager` | Writes VA SOPs, converts Loom transcripts to SOPs, builds the weekly scorecard summary, drafts MREA time blocks, job descriptions, and the Friday review. | `gpts/cb-ops-manager.md` | `10-SCORECARD/kpi-scorecard.md`, `01-MREA-MODELS/*.md`, `09-VA-PLAYBOOK/*.md` if it exists | Browsing OFF, Code interpreter ON |

Conversation starters are listed at the bottom of each GPT file. Paste all four.

Test each GPT with the worked example in its file before sharing it. If the output does not match the example's shape, the instructions were pasted incompletely.

---

## (c) How the VA uses the GPTs

**On ChatGPT Team (recommended):** add the VA as a member of the workspace. Share each GPT with "Anyone at [workspace]." Add the VA to the Project. The VA opens the GPT from the sidebar, runs it, and pastes the draft into Command or Slack.

**On ChatGPT Plus:** the VA needs their own Plus account. Share each GPT with "Anyone with the link" and put the six links in the VA Playbook. The VA cannot see the Project, so upload the same knowledge files to each GPT directly (already done in step b). Keep both accounts on the same version of the brand voice sheet.

**VA rules of use:**
1. Every GPT session starts by pasting the raw input (lead payload, intake form, numbers). Never paraphrase the input. The GPT is only as accurate as what it was given.
2. Read the output before doing anything with it. Check every number against the source. Check every address.
3. Paste drafts into Command as drafts or into the Slack channel for approval (`#leads`, `#listings`, `#ops`). Do not send.
4. If a GPT asks for missing fields, go get them. Do not guess and do not tell the GPT to "just make it up."
5. Save GPT outputs to the right Drive folder (`Listings/[YYYY-MM] [Street Address]/04-Marketing-Kit` for listing assets, `SOPs/` for SOPs).
6. Log any output that was wrong or off-voice in the `#ops` channel with the prompt used. That feeds the monthly review (step g).

---

## (d) Scheduled Tasks

ChatGPT Tasks (available in the model picker under "Tasks" or by asking ChatGPT to "schedule this") send a reminder and can run a prompt on a schedule. They run in a normal chat, not inside a custom GPT, so keep the scheduled prompt self-contained.

**Task 1: Monday seller report reminder**
- Owner: VA's account
- Schedule: every Monday, 8:00 AM [MARKET] time
- Prompt to schedule:
  ```
  Monday seller report day. Remind me to: (1) pull traffic, showings, feedback, saves, and market movement for every Active listing in Command by 10am; (2) run each listing through CB Seller Concierge using the weekly report prompt; (3) post every draft in Slack #listings for Charles by 11am; (4) confirm every report is sent by 12pm. List the steps as a checklist.
  ```
- Charles's account gets a second Task at 11:00 AM: "Approve seller reports in #listings. Every active seller gets a written update today by 12pm."

**Task 2: Friday scorecard summary**
- Owner: VA's account
- Schedule: every Friday, 2:00 PM [MARKET] time
- Prompt to schedule:
  ```
  Friday scorecard. Remind me to pull this week's KPI numbers from Command (contacts added, Met vs Haven't Met, leads by source, 5-minute response rate, appointments set and met, listings taken, buyer agreements signed, under contract, closed, GCI, 33 Touch and 12 Direct sends, social posts published) and run them through CB Ops Manager for the scorecard summary. Post the summary in #ops by 3pm for Charles's Friday review.
  ```
- Charles's account gets a Task at 4:00 PM Friday: "Run the Friday review in CB Ops Manager: what worked, what didn't, what's next. 20 minutes."

Optional Tasks worth adding once the first two are habits: Tuesday 9 AM "call every seller with a listing over 14 days," and the first business day of the month "monthly GPT review (see setup-guide step g)."

---

## (e) Brand Voice Sheet

Charles fills this in once, honestly, in about 20 minutes. Save it as `03-CHATGPT/brand-voice-sheet.md` and upload it to the Project and every GPT. Update it whenever a draft comes back sounding wrong.

Placeholder version (replace every bracketed line):

```
# Charles Brewer Brand Voice Sheet

## Who I am in one sentence
[Example: A [MARKET] agent who tells people the truth about their house and their money, then does the work.]

## Five tone words
1. [Direct]
2. [Warm]
3. [Calm]
4. [Specific]
5. [Unhurried]

## Five words that are NOT me
1. [Salesy]
2. [Hype]
3. [Corporate]
4. [Cute]
5. [Vague]

## Phrases I actually say (use these)
- [Here's what happens next.]
- [Let me run the numbers and call you back.]
- [The market decides the price; I decide the marketing.]
- [You'll hear from me every Monday, good news or bad.]
- [No pressure either way.]

## Phrases I never say (avoid these)
- [Dream home]
- [Stunning / breathtaking / must-see]
- [Won't last long]
- [As you know...]
- [I hope this email finds you well]
- [Any exclamation point after the first one]

## How I greet and sign off
- Text greeting: [Hi [First name], Charles here.]
- Text sign-off: [Charles]
- Email greeting: [Hi [First name],]
- Email sign-off: [Charles Brewer / [PHONE] / charlesbrewer.guru]

## Formality
[Casual-professional. Contractions are fine. No slang. No emojis in email; one emoji max in a text if the client uses them first.]

## Sample paragraph in my voice (write 80-120 words about something real)
[Example: Your house went live Thursday. By Sunday night we had 14 showings and two second showings, which is above what similar homes on your street have been getting. The feedback is consistent: buyers like the kitchen and the yard, and two of them mentioned the primary bath feels dated. That is not a reason to change anything yet. We are still inside the first 14 days, which is when the most motivated buyers come through. My plan is to hold price through next weekend's open house and revisit on Day 14 with real data. I'll call you Tuesday. If anything changes before then, you'll hear from me first.]

## Things about my market I want mentioned correctly
- [Neighborhood names and how locals say them]
- [Anything I never want said about [MARKET]]
```

---

## (f) Privacy rules

ChatGPT is a drafting tool, not a filing cabinet. These rules apply to Charles, the VA, and every GPT session:

1. **Never paste:** Social Security numbers, driver's license numbers, bank or loan account numbers, routing numbers, credit card numbers, full pre-approval letters, full contract PDFs, inspection reports with client names, or any document with a signature.
2. **Use first names only** for clients and leads in prompts. Last names are not needed for drafting.
3. **Use addresses only where the task needs them** (marketing kit, itinerary, deal analysis). For a lead reply, "the property on Maple" is enough.
4. **Financial details in the Investor Analyst:** purchase price, rents, rates, and expenses are fine. Lender names and loan numbers are not.
5. **Buyer financials:** pre-approval amount and down payment percentage are fine for offer strategy. Income, credit score, and employer are not.
6. **Turn off training** on every GPT ("Use conversation data in your GPT to improve our models" unchecked) and in each account's Data Controls.
7. **Delete conversations** containing client details after the task is complete, or at least monthly.
8. **Command is the system of record.** If it matters, it lives in Command, not in a ChatGPT thread.

---

## (g) Monthly review ritual

First business day of the month, 45 minutes, Charles and the VA together (or async in `#ops`).

1. **Collect:** the VA pulls every "this output was wrong or off-voice" note from `#ops` for the month, plus three drafts Charles edited the most before approving.
2. **Sort:** each problem goes into one bucket: wrong facts (input problem), wrong voice (brand sheet problem), wrong format (instructions problem), or missing capability (new prompt or GPT change needed).
3. **Fix:**
   - Input problems: fix the intake form or the SOP that feeds the GPT.
   - Voice problems: edit the brand voice sheet, re-upload to every GPT.
   - Format problems: edit the specific GPT's instructions in `03-CHATGPT/gpts/`, paste the new version into the GPT, note the change at the top of the file with the date.
   - Capability problems: add a prompt to `prompt-library.md` or a new section to the GPT.
4. **Test:** re-run the worked example from each edited GPT file and confirm the output still matches.
5. **Log:** one line per change in a `03-CHATGPT/changelog.md` (date, GPT, what changed, why). Commit to the repo.
6. **Retire:** any prompt in the library nobody used for two months gets moved to an "unused" section at the bottom.

Rule of thumb: if the VA is editing more than 20 percent of a GPT's output before sending, the instructions need work, not the VA.
