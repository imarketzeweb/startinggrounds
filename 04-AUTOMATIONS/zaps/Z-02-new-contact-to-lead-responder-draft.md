# Z-02  New Command Contact → Lead Responder Draft

## Name
`Z-02 New Command Contact → Lead Responder Draft`

## Purpose
Every new lead gets a qualified, drafted first reply within about a minute of arriving so the human reply (5-minute standard) is a review, not a writing job. The Zap runs the `CB Lead Responder` logic through Zapier's ChatGPT/OpenAI action and posts SMS and email drafts to Slack for approval. If the ChatGPT step is unavailable, the VA runs the GPT manually from the alert.

## Trigger
- Preferred: **KW Command: New Contact** (verify this trigger exists in your Command Zapier connection).
- Fallback A: **Slack: New Message Posted to Channel** on `#leads`, filtered to messages starting with `:rotating_light: NEW`. This means Z-01, Z-03, Z-04, Z-05 all feed Z-02 through Slack without any Command trigger.
- Fallback B: **Google Sheets: New Spreadsheet Row** on `Lead Log`.

## Steps

1. **Filter by Zapier:** only continue if tags contain `New-Lead` (Command trigger) or the message contains "NEW" and "LEAD" (Slack trigger).
2. **Formatter: Text: Extract** name, phone, email, source, page, message, timeline from the trigger payload.
3. **ChatGPT (OpenAI) by Zapier: Conversation** using the prompt below. Model: the latest GPT-4 class model available in the action. Temperature 0.4.
4. **Formatter: Utilities: Line Itemizer / JSON parse** the response into fields `type`, `temperature`, `suggested_tags`, `suggested_smartplan`, `summary`, `sms_draft`, `email_subject`, `email_body`, `call_opener`, `questions`.
5. **Slack: Send Channel Message** to `#leads`, as a thread reply to the original alert when the Slack trigger is used (template below).
6. **KW Command: Update Contact** add tags `A`, `B`, or `C` from `temperature` (verify action). If unavailable, the VA adds the tag when approving.
7. **Filter:** if `temperature` = A, also **SMS by Zapier** to Charles: `A LEAD: {name} ({type}). Draft in #leads. Call now if free.`

## Field mapping

| Source field | Destination field |
|---|---|
| ChatGPT `temperature` | Command tag `A` / `B` / `C` |
| ChatGPT `type` | Check against existing type tag; mismatch flagged in Slack |
| ChatGPT `summary` | Command contact note "Lead Responder summary: ..." |
| ChatGPT `sms_draft`, `email_subject`, `email_body` | Slack thread (never Command send) |

## ChatGPT step

Prompt text used in the Zapier OpenAI action (User message; System message = "You are CB Lead Responder for Charles Brewer, a Keller Williams agent in [MARKET]. Warm, direct, professional. Fair Housing safe: never describe people, neighborhoods by who lives there, or schools by quality. Never quote a price opinion. Output valid JSON only."):

```
Here is a raw lead payload. Classify it and draft the first-touch replies.

Name: {name}
Phone: {phone}
Email: {email}
Source: {source}
Page or property: {page}
Timeline stated: {timeline}
Message: {message}

Rules:
- type is one of Buyer, Seller, Investor, Sphere.
- temperature: A = wants to transact in 0-30 days, B = 30-90 days, C = 90+ days or undecided. If unclear, choose C and say why in summary.
- suggested_tags: choose from Buyer, Seller, Investor, Sphere, Src-Website, Src-Social, Src-OpenHouse, Src-Sign, New-Lead, Haven't Met, A, B, C.
- suggested_smartplan: SP-Speed to Lead for any web or social lead; SP-8x8 New Contact for open house or sphere.
- sms_draft: under 300 characters, first name, one question, sign as Charles.
- email_body: 60-110 words, plain text, sign as Charles Brewer, Keller Williams [BROKERAGE OFFICE], [PHONE], book a call: [CALENDLY LINK].
- questions: 3 short qualifying questions for the human caller.
- End nothing with a signature block inside JSON strings other than as specified.

Return exactly this JSON:
{"type":"","temperature":"","suggested_tags":[],"suggested_smartplan":"","summary":"","sms_draft":"","email_subject":"","email_body":"","call_opener":"","questions":["","",""]}
```

Expected output (example):
```json
{"type":"Seller","temperature":"B","suggested_tags":["Seller","Src-Website","New-Lead","Haven't Met","B"],"suggested_smartplan":"SP-Speed to Lead","summary":"Homeowner on Sell page, wants to move in 2-3 months, asked about timing.","sms_draft":"Hi Maria, Charles Brewer here with Keller Williams. Thanks for reaching out about your home on Oak St. Quick question so I can be useful: are you thinking spring, or sooner? -Charles","email_subject":"Your home on Oak St, next steps","email_body":"...","call_opener":"Hi Maria, it's Charles Brewer. You just filled out the form on my site about Oak St. Did I catch you at a decent time?","questions":["What's driving the move?","Have you had a valuation done recently?","Is there a date you need to be moved by?"]}
```

## Alert message template (Slack `#leads`, thread reply)
```
:memo: DRAFTS READY  |  {type}  |  {temperature}
Summary: {summary}
Suggested tags: {suggested_tags}  |  SmartPlan: {suggested_smartplan}

SMS draft:
{sms_draft}

Email: {email_subject}
{email_body}

Call opener: {call_opener}
Questions: {questions}

React :white_check_mark: to approve as-is, or reply with edits. VA sends from Command. DRAFT for human review. Not sent.
```

## Error handling / fallback
- OpenAI step fails or returns bad JSON: Slack message says `GPT step failed. VA: open CB Lead Responder, paste the alert, post drafts here.` The VA follows SOP-01 step 4.
- No Command trigger available: use the Slack trigger (Fallback A). It is reliable and keeps one lead thread per lead.
- Duplicate runs (Command and Slack both firing): use only one trigger. Never run both.
- Never map `sms_draft` or `email_body` to a Command send action. That is the human-approval rule.

## Test checklist
- [ ] Create a contact "Ztest Buyer" with `New-Lead` tag (or post a test alert in `#leads`).
- [ ] Thread reply appears within 90 seconds with valid drafts.
- [ ] JSON parses; all nine fields populated.
- [ ] Temperature tag added to the contact (or alert says VA adds).
- [ ] An A-lead test triggers the SMS to Charles.
- [ ] Output contains no price opinion and no people-descriptive language.

## Build time estimate
2.5 hours. Add 30 minutes to tune the prompt after the first 10 live leads.
