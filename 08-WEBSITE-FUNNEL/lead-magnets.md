# Lead Magnet Library

Read `/00-START-HERE/conventions.md` first.

Every lead magnet exists to do one thing: give a visitor a reason to hand over a name, email, and phone so a human can call within 5 minutes. Each one below has an outline, a page count, a Canva design note, the delivery path, and the ChatGPT prompt that drafts it. ChatGPT drafts, Charles approves, the VA produces in Canva, Command delivers.

Production standard for every PDF:
- Canva, using the brand kit (fonts, colors, logo, Charles's headshot).
- Cover: title, `[MARKET]`, Charles Brewer, Keller Williams `[BROKERAGE OFFICE]`, year.
- Every page: footer with `[PHONE]`, `[EMAIL]`, charlesbrewer.guru, Equal Housing Opportunity logo.
- Last page: "What happens next" with `[CALENDLY LINK]` and a QR code to the matching landing page (with UTM `utm_source=pdf&utm_medium=email&utm_campaign=[magnet-name]`).
- Fair Housing review before publish: no protected-class language, no neighborhood characterizations by who lives there, areas described by price, commute, amenities, and market data only.
- Version in the filename: `[MARKET]-Home-Sellers-Guide-v2026-09.pdf`. Refresh every 6 months; market stats every quarter.
- Stored in Drive under `Marketing/Lead-Magnets/`. Uploaded to Command as an attachment for SmartPlan emails.

Delivery path for every magnet: form submit -> Zap creates Command contact with tags -> Command (or the form tool's auto-responder) sends the PDF link -> `SP-Speed to Lead` starts -> `#leads` alert. Detail in charlesbrewer-guru-funnel.md.

## Seller magnets

### 1. `[MARKET] Home Seller's Guide`

Purpose: the pre-consult packet centerpiece and the Sell page secondary offer. Positions the consultation, sets the maximum exposure expectation, and answers the price question honestly.

Page count: 16 to 20 pages.

Outline (chapters):
1. Welcome from Charles: the white glove promise in one page
2. Is now the time? What actually drives the decision (timeline, equity, next home, market)
3. The [MARKET] market right now: 6 stats with a date (median price, days on market, months of inventory, list-to-sale ratio, rate snapshot, seasonal pattern). Refreshed quarterly.
4. How pricing works: what buyers pay for, what they do not, and the cost of overpricing (the first 14 days)
5. What it costs to sell: commission (negotiable, agreed in writing), closing costs, prep, concessions, and a sample net sheet
6. Preparing your home: fix, skip, and stage, with the 30/14/7 day checklist summarized (full checklist in magnet 2)
7. The maximum exposure standard: photography, drone, video, 3D tour, floor plan, single-property page, five-stage social sequence, database email. Why each one matters.
8. The five listing stages: Coming Soon, Just Listed, Open House, Under Contract, Just Sold, and what happens in each
9. Showings and feedback: how showings work, how feedback is relayed within 24 hours, the Monday written update
10. Offers: reading an offer beyond price (EMD, contingencies, financing strength, closing date, concessions), multiple offers, counters
11. Under contract to closing: inspection, appraisal, title, repairs, walk-through, closing day, and the milestone calendar
12. After closing: what I do for past clients
13. What to expect from me: the standards I hold myself to, in writing
14. Next step: book the listing consultation

Design note (Canva): letter size, one idea per page, big headline, one graphic per chapter (process map, net sheet table, five-stage timeline). Photos from Charles's own listings only. Chapter 3 built as an editable stat block so the VA can refresh numbers without redesign.

ChatGPT prompt (`CB Seller Concierge`):
```
Draft the [MARKET] Home Seller's Guide using the 14-chapter outline below. Charles Brewer's voice: direct, warm, no hype, no exclamation points, short sentences. Each chapter 150 to 300 words plus one suggested graphic. Chapter 3 uses the stats I paste and cites the date. Chapter 5 includes a sample net sheet table with placeholder numbers. State that commission is negotiable and agreed in writing. Fair Housing safe: never describe areas by who lives there. Placeholders in brackets for anything you do not know. Return chapter by chapter with a headline, body, and a one-line graphic suggestion.
[paste outline]
[paste market stats with date]
[paste the white glove promise and maximum exposure standard from 05-SELLER-SYSTEM]
```

### 2. Pre-Listing Checklist

Purpose: fast, practical, low-commitment download for sellers who are not ready for a number. Also handed out at the listing consultation.

Page count: 2 to 4 pages.

Outline:
1. 30 days out: declutter by room, minor repairs list, gather documents (survey, permits, HOA docs, warranties, utility bills), pick a launch window
2. 14 days out: deep clean, paint touch-ups, landscaping, staging decisions, photography prep (what to remove from counters and walls), pet plan for showings
3. 7 days out: photography and video day checklist, lockbox and sign placement, showing instructions, where to be during showings
4. Launch week: Coming Soon, Just Listed, open house prep, the Monday update schedule
5. Room-by-room quick list (kitchen, baths, bedrooms, living, exterior, garage)
6. What not to bother with (a short list of low-return projects)

Design note (Canva): checklist format with actual checkboxes, printable in black and white, one page per phase.

ChatGPT prompt (`CB Seller Concierge`):
```
Write a Pre-Listing Checklist for [MARKET] sellers in the outline below. Checklist items only, each under 12 words, grouped by 30/14/7 days and launch week, plus a room-by-room list and a "skip these" list. Practical and specific. No marketing language.
[paste outline]
```

### 3. Instant Home Value

Purpose: the highest-intent seller magnet. A visitor enters an address and gets a value range.

Recommendation: do not build a custom tool. Use one of these, in order of preference:
1. KW Command home valuation (if available on the KW Site or as an embeddable widget in your market). Leads flow straight into Command with no Zap.
2. Homebot. Monthly home value emails keep sellers and past clients engaged; the signup widget captures address and email; leads export to Command via Zapier or CSV. Also the tool for the annual equity update in `SP-Past Client Program`.
3. CloudCMA "What's my home worth" landing page. Produces a branded report; leads to Command via Zapier.
Any of the three works. Pick one and route it the same way.

Routing regardless of tool:
- The tool's lead notification triggers `Z-03 Home Value Request → Command Contact + Seller Alert`: contact with `Seller`, `Src-Website`, `New-Lead`, `Haven't Met`, address stored, `SP-Speed to Lead`, `#leads` alert, VA task "Prepare home value estimate within 4 hours."
- The VA runs the tool's report, Charles reviews and adjusts the range, and Charles sends the range by text and email within 4 business hours with an offer to walk through it on a call.
- If the tool cannot connect to Zapier, the VA checks its dashboard at 9am, 1pm, and 5pm and enters leads manually the same hour.

No ChatGPT drafting needed beyond the follow-up text and email, which `CB Seller Concierge` drafts:
```
Draft a text and a short email from Charles to a homeowner who requested a home value for [ADDRESS]. Give the range $[X] to $[Y], say what could move it up, and offer a 15-minute call with [CALENDLY LINK]. Under 80 words for the text, under 150 for the email. No pressure language.
```

## Buyer magnets

### 4. `[MARKET] Home Buyer's Guide`

Purpose: the Buy page primary offer and the pre-consult packet centerpiece.

Page count: 16 to 20 pages.

Outline (chapters):
1. Welcome from Charles: the white glove buyer promise
2. The [MARKET] market for buyers right now: 6 stats with date, what they mean for you
3. Step one is a conversation: why the consultation comes before the first showing, and what we cover
4. Representation: what a buyer's agent does, agency, the buyer agreement, and how compensation works (negotiable, in writing)
5. Financing: pre-approval versus pre-qualification, loan types at a glance, what lenders ask for, rate locks
6. What it really costs: down payment, closing costs, reserves, sample cash-to-close table, monthly payment components
7. The search: how alerts work, what to do when you see a home online, how many homes you will actually see
8. Showings: the itinerary the night before, what to look for in a home, the recap the same evening
9. Making an offer: price, earnest money, inspection period, appraisal, financing contingency, closing date, concessions, and how each protects you
10. Competing offers: the levers that matter and the ones that do not
11. Under contract: the milestone calendar from acceptance to keys (EMD, inspection, appraisal, insurance, utilities, walk-through, closing)
12. Closing day and after: what to bring, when you get keys, the 7/30/90 day check-ins
13. Glossary of 25 terms
14. Next step: book the consultation

Design note (Canva): letter size, process map graphic in chapter 3 reused from the pre-consult packet, cash-to-close table in chapter 6 as an editable block, milestone calendar in chapter 11 as a timeline graphic.

ChatGPT prompt (`CB Buyer Concierge`):
```
Draft the [MARKET] Home Buyer's Guide using the 14-chapter outline below. Charles Brewer's voice: direct, warm, no hype, short sentences. Each chapter 150 to 300 words plus one graphic suggestion. Chapter 2 uses the pasted stats with a date. Chapter 6 includes a sample cash-to-close table with placeholder numbers. Chapter 4 states that compensation is negotiable and agreed in writing. Chapter 13 is a 25-term glossary with one-sentence definitions. Fair Housing safe throughout. Return chapter by chapter.
[paste outline]
[paste market stats with date]
[paste the buyer process from 06-BUYER-SYSTEM/buyer-journey-white-glove.md]
```

### 5. First-Time Buyer Roadmap

Purpose: a one-page map for the Buy page secondary offer and social posts aimed at first-time buyers.

Page count: 1 page (front) plus 1 page of notes (back).

Outline:
Front: a numbered path of 12 stops with one line each: 1 Consultation, 2 Lender pre-approval, 3 Budget and comfort payment, 4 Search set up, 5 Showings (itinerary and recap), 6 Offer strategy call, 7 Offer accepted, 8 Earnest money, 9 Inspection, 10 Appraisal and financing, 11 Insurance, utilities, walk-through, 12 Closing and keys. Typical timeline bar underneath (weeks, `[MARKET]` typical).
Back: "Five mistakes first-time buyers make and how to avoid them," first-time buyer programs to ask a lender about (generic list, verified locally), and the next step CTA.

Design note (Canva): infographic path, printable, works as a single Instagram carousel when split into 4 slides.

ChatGPT prompt (`CB Buyer Concierge`):
```
Write the First-Time Buyer Roadmap: 12 stops, each a title and one sentence under 18 words, in the order below. Then a back page: five common first-time buyer mistakes with a one-line fix each, and a short list of first-time buyer program types to ask a lender about, with a note to verify eligibility locally. Plain language. No hype.
[paste 12 stops]
```

## Investor magnets (Capital Partner program)

Model: Charles sources fix and flip deals, capital partners fund them (buy the deal outright, joint venture, or private lender), Charles project-manages the rehab and lists the finished flip. The magnets show a partner exactly what they will receive and how the program runs. No guaranteed-return language anywhere. Terms on every project are set by attorney-drafted agreements, and both magnets say so.

### 6. Sample Deal Memo (anonymized closed flip)

Purpose: the proof piece. A real, closed `[MARKET]` flip, anonymized, presented in the same Deal Memo format a partner receives on a live project, with the projected numbers next to the actuals. Delivered from the Invest page confirmation email and thank-you page, and attached to the intro call recap.

Page count: 4 to 6 pages.

Outline:
1. Cover: "Sample Deal Memo: [NEIGHBORHOOD] 3 bed / 2 bath flip, closed [month year]". Line: "Actual numbers from one closed project. Past results do not predict future results."
2. The property: photos before and after, condition at purchase, why it was a flip candidate, how it was sourced (off-market, expired, estate, or MLS), days from first contact to contract
3. The underwriting (as written before purchase): purchase price versus maximum allowable offer, rehab scope and line-item budget with contingency, after-repair value with the three closed comps behind it, holding costs by month, selling costs, projected timeline by phase, projected total cost and projected sale range, red flags found and how each was resolved
4. The structure: which of the three structures was used, what the capital partner funded, what Charles did, how decisions and scope changes were handled, the weekly update cadence (a one-week update reproduced as a sample)
5. The actuals: table with projected versus actual for purchase price, rehab, contingency used, holding costs, days to listing, days on market, sale price, total project cost, gross result. Variance column with a one-line reason for each variance over 5%.
6. Lessons and what changed in the underwriting defaults afterward
7. Next step: intro call CTA, `[CALENDLY LINK]`, QR code
8. Footer on every page: "Charles Brewer is a licensed real estate agent with Keller Williams `[BROKERAGE OFFICE]`. Capital partner arrangements are private agreements drafted by an attorney and reviewed by each party's own counsel and CPA. Figures are actuals from one project and do not predict future results. Nothing in this document is investment, legal, or tax advice, an offer of securities, or a guarantee of any outcome."

Design note (Canva): the Deal Memo template is built once as a brand-kit document and reused for every live deal; the Sample is the same template with the "Actuals" section added. Before and after photos full-bleed on page 2. Projected versus actual table is the centerpiece of page 5. Charles's attorney reviews the footer text before first publish.

ChatGPT prompt (`CB Investor Analyst`):
```
Using the pasted Deal Memo outline and the actual figures from a closed flip, draft the Sample Deal Memo. Anonymize the address as "[NEIGHBORHOOD] [beds] bed / [baths] bath". Present the pre-purchase underwriting exactly as it was written, then a projected-versus-actual table with a variance column and a one-line reason for each variance over 5%. Describe the structure used and each party's role without stating any percentage return or promising future results. Include the compliance footer verbatim on every page. Charles Brewer's voice: direct, factual, no hype. Flag any sentence that could read as a promise of return so Charles can remove it.
[paste outline]
[paste projected and actual figures]
[paste compliance footer]
```

### 7. "How the Capital Partner Program works" one-pager

Purpose: the explainer that goes with the Sample Deal Memo in the confirmation email, on the thank-you page, and as the leave-behind after the intro call. Also splits into a social carousel.

Page count: 1 page (front) plus 1 page (back).

Outline:
Front: the seven steps as a numbered path, one line each: 1 Charles sources the deal, 2 Charles underwrites and writes the Deal Memo, 3 Partner reviews and asks questions, 4 Structure chosen and attorney-drafted agreement signed (buy outright / joint venture / private lender), 5 Charles manages the rehab with a written weekly update, 6 Charles lists and sells under the maximum exposure standard, 7 Close-out accounting against the Deal Memo and the next deal. Typical timeline bar underneath by phase (`[MARKET]` typical, labeled as typical, not promised).
Back: "Three ways to partner" with a two-line description of each structure; "Who does what" two-column table (Charles / Capital partner); "What you receive" (Deal Memo, weekly update, close-out accounting); "Questions to ask your attorney and CPA before you partner" (five questions); the compliance footer; intro call CTA with `[CALENDLY LINK]` and QR code.

Design note (Canva): infographic path on the front matching the First-Time Buyer Roadmap style so the brand reads consistently; back page is text-heavy and printable in black and white; carousel export as 5 slides (steps 1 to 7 across 3 slides, structures, CTA).

ChatGPT prompt (`CB Investor Analyst`):
```
Write the "How the Capital Partner Program works" one-pager from the outline below. Front: seven steps, each a title and one sentence under 20 words. Back: three structures (buy the deal outright, joint venture, private lender) in two lines each, a who-does-what table, a what-you-receive list, and five questions a prospective partner should ask their own attorney and CPA. Do not state or imply any return, and say plainly that terms are set by attorney-drafted agreements. Include the compliance footer verbatim. Charles Brewer's voice.
[paste outline]
[paste compliance footer]
```

## Magnet-to-system map

| Magnet | Landing page | Form tag set | Delivered by | Also used in |
|---|---|---|---|---|
| `[MARKET] Home Seller's Guide` | `/sell` secondary | `Seller` + `Src-Website` | Command email | Pre-listing packet, `SP-Seller Nurture` |
| Pre-Listing Checklist | `/sell` secondary, blog | `Seller` + `Src-Website` | Command email | Listing consultation handout |
| Instant Home Value | `/sell` primary | `Seller` + `Src-Website` | Tool report + Charles's text/email | Annual equity update in `SP-Past Client Program`, Just Sold CTA |
| `[MARKET] Home Buyer's Guide` | `/buy` primary | `Buyer` + `Src-Website` | Command email | Pre-consult packet, `SP-Buyer Nurture`, `SP-Speed to Lead` day 1 |
| First-Time Buyer Roadmap | `/buy` secondary, social carousel | `Buyer` + `Src-Website` or `Src-Social` | Command email | Open house handout |
| Sample Deal Memo | `/invest` (confirmation email + thank-you page) | `Investor` + `Src-Website` | Command email + thank-you download | Intro call recap, investor meetups (`Src-Event`) |
| How the Capital Partner Program works | `/invest` (with the Deal Memo), social carousel | `Investor` + `Src-Website` or `Src-Social` | Command email | Intro call leave-behind |

## Production checklist (VA, per magnet)

- [ ] Draft generated with the prompt above and saved to Drive `Marketing/Lead-Magnets/[name]/draft.docx`
- [ ] Charles edits and approves the text
- [ ] Fair Housing review completed
- [ ] Canva build from the brand kit; cover, footers, QR code, next-step page
- [ ] Market stats dated; refresh reminder set in Command tasks (quarterly)
- [ ] PDF exported under 5 MB; filename versioned
- [ ] Uploaded to Command and linked in the matching SmartPlan email
- [ ] Landing page form tested end to end; PDF arrives in the test inbox; contact tagged correctly in Command
- [ ] Social promo post scheduled with the UTM from charlesbrewer-guru-funnel.md
