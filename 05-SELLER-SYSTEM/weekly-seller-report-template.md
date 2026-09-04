# Weekly Seller Report (Monday Update)

Service standard 2: every active seller gets a written update every Monday. Traffic, feedback, showings, market movement, next step. Sent by 12pm, whether the news is good or bad. Listings over 14 days also get a Tuesday call.

Flow: VA pulls the numbers by 10am → VA hands the raw numbers to `CB Seller Concierge` → GPT drafts the narrative → Charles edits and approves → VA sends from Command (so it logs on the contact timeline) → Charles calls on Tuesday if the listing is over 14 days.

Rule: ChatGPT drafts, a human approves, Command sends. The recommendation section is always written or rewritten by Charles.

## 1. VA data-gathering checklist (Monday, done by 10am)

One row per active listing. Keep a running sheet per listing at `05-Docs/Weekly-Report-Data.xlsx` (or a Command note) so week-over-week and cumulative numbers are always available.

| # | Number | Where to pull it | Notes |
|---|---|---|---|
| 1 | Showings this week | ShowingTime (or equivalent) → listing → activity report, filter last 7 days | Count confirmed showings only. Note cancellations separately |
| 2 | Showings total | Same, all time | |
| 3 | Showing feedback received | ShowingTime feedback tab | Copy verbatim, with agent name and date. Note how many showings gave no feedback |
| 4 | Open house groups and sign-ins | `05-Docs/OpenHouse-[date].md` | Include neighbors and agents separately |
| 5 | MLS views and agent activity | MLS listing stats (hits, detail views, saved searches matched) | Field names vary by MLS |
| 6 | Zillow views and saves | Zillow Owner Dashboard (seller can share) or agent's Zillow listing stats via the claimed listing | Weekly and total |
| 7 | Realtor.com views and saves | Realtor.com Pro listing dashboard | Weekly and total |
| 8 | Redfin views and favorites | Redfin listing page (public "views" and "favorites" if shown) or Redfin Partner dashboard | Some markets show it publicly |
| 9 | Homes.com views | Homes.com agent dashboard | If available |
| 10 | Property page views and form submissions | charlesbrewer.guru analytics, filter to the listing page | Note QR scans from the sign via the UTM |
| 11 | Social reach and engagement | IG insights, FB insights, TikTok analytics for posts tagged `[Address]-*` | Reach, saves, shares, DMs with the listing keyword |
| 12 | Email blast stats | Command Campaigns or SmartPlan email stats | Sent, opens, clicks |
| 13 | New competing listings | MLS search: same neighborhood or radius, price plus or minus 10 percent, listed in last 7 days | Address, price, beds/baths/sqft, DOM |
| 14 | New pendings | Same search, status pending, last 7 days | List price and DOM at pending |
| 15 | New solds | Same search, sold in last 7 days | List, sold, DOM, list-to-sale ratio |
| 16 | Price changes nearby | MLS price change report, same radius | Who cut and by how much |
| 17 | Our position | Rank our list price and price per sqft against every active in the same bracket | "3rd of 7 actives on $/sqft" style |
| 18 | Days on market | MLS | Cumulative and since last price change |
| 19 | Marketing done this week | Social schedule, Command Campaigns, ShowingTime, open house log, agent emails | List with dates |
| 20 | Marketing planned next week | Social schedule, open house calendar, launch playbook timeline | List with dates |
| 21 | Offers or agent inquiries | Charles, `#listings`, Opportunity notes | Any "is the seller flexible" calls count as interest |

Save the completed row, then paste it into the prompt in section 3.

## 2. Report template

Sent from Command as an email. Subject: `[ADDRESS] Weekly Update: Week [N]`. Sections in this order, every week, even if a section says "nothing new this week."

```
Subject: [ADDRESS] Weekly Update: Week [N]

Hi [Seller first name(s)],

Here is where we are as of Monday, [date]. Week [N] on market, [N] days total.

1. SHOWINGS
This week: [N] (last week: [N])
Total: [N]
Open house: [N] groups on [date], [N] neighbors, [N] agents
Scheduled for this week so far: [N]

2. ONLINE TRAFFIC
Zillow: [N] views, [N] saves this week ([N] / [N] total)
Realtor.com: [N] views, [N] saves ([N] total)
Redfin: [N] views, [N] favorites
Homes.com: [N] views
MLS agent views: [N], matched to [N] buyer saved searches
Property page: [N] visits, [N] from the sign QR, [N] showing requests
Social: [N] reach, [N] saves, [N] DMs asking about the home
Email blast: [N] sent, [N] percent opened, [N] clicked

What this tells us: [one or two sentences. Views vs saves vs showings ratio. Is the funnel healthy?]

3. SHOWING FEEDBACK
[Date, agent]: "[verbatim]"
[Date, agent]: "[verbatim]"
[N] showings gave no feedback despite two requests.

What I hear in it: [Charles's interpretation. Theme: price / condition / layout / location / nothing actionable]

4. THE MARKET AROUND YOU (last 7 days, [NEIGHBORHOOD] and similar)
New listings: [address, price, beds/baths/sqft] ...
Went pending: [address, list price, DOM] ...
Sold: [address, list vs sold, DOM] ...
Price changes: [address, from → to] ...

5. WHERE WE SIT
List price: [PRICE]. Price per sqft: $[N].
Against the [N] active comparables: [rank on price, rank on $/sqft].
Days on market: [N] (neighborhood average for this price band: [N]).

6. MARKETING THIS PAST WEEK
- [date]: [action]
- [date]: [action]

7. MARKETING THIS COMING WEEK
- [date]: [action]
- [date]: [action]

8. MY RECOMMENDATION
[Charles writes this. One of: stay the course and why / marketing adjustment and what / price conversation and the specific number / meeting requested.]

9. NEXT STEP
[One line. What happens next and when. If a decision is needed from the seller, say so and give a deadline.]

I'll call you [Tuesday at time] to talk it through. Reply here anytime.

Charles
[PHONE] | [EMAIL] | [CALENDLY LINK]
```

Notes on tone:
- Numbers first, interpretation second, recommendation third. Never bury bad news.
- No exclamation points in a report with zero showings.
- "Price improvement," never "price reduction," in seller-facing copy. In the recommendation, be plain: "I recommend we move to $[X]."
- Every feedback quote is verbatim, including the unflattering ones. Sellers lose trust when they hear it later from a neighbor.

## 3. Prompt for `CB Seller Concierge` (VA runs, Monday 10am)

Paste the completed data row, the previous week's report, and this prompt.

```
Draft the Monday weekly seller update for [ADDRESS] using the fixed report template
(sections 1 to 9). Here are the raw numbers for the week ending [date]:

[paste data row: showings this week/total, open house, portal views and saves by portal,
property page, social, email, feedback verbatim, new listings/pendings/solds/price changes
nearby, our price position, DOM, marketing done, marketing planned, offers or inquiries]

Last week's report for continuity:
[paste]

Instructions:
- Fill sections 1 through 7 exactly. Use the numbers as given. Do not invent or round up.
- In section 2, write the "What this tells us" line from the ratio of views to saves to
  showings, compared to last week.
- In section 3, quote feedback verbatim and propose an interpretation (price, condition,
  layout, location, or nothing actionable). Label it "DRAFT INTERPRETATION" so Charles
  rewrites it.
- In section 4, list only what is in the data. If a category has nothing, write "None this week."
- Leave section 8 as "[CHARLES TO WRITE]" and section 9 as "[CHARLES TO CONFIRM]".
- Plain, direct, warm. No exclamation points. No em-dashes. Use "price improvement," not
  "price reduction," in seller-facing language.
- Flag anything in the numbers that suggests a Day 14 or Day 30 review is due.
- Return only the report, ready to paste.
```

VA then:
1. Reads the draft for number accuracy against the data row.
2. Pastes it into a Command email draft to the seller (from Charles's account or with Charles as sender).
3. Messages Charles in `#listings`: "[ADDRESS] Week [N] draft ready, sections 8 and 9 need you. Flags: [any]."

Charles then:
1. Rewrites the feedback interpretation in his own words.
2. Writes the recommendation and next step.
3. Approves. VA sends by 12pm and logs it in the Opportunity.

## 4. Interpretation cheat sheet (for Charles, and for the GPT's draft)

| Pattern | Likely meaning | Usual move |
|---|---|---|
| High views, low saves, low showings | Hero photo or price looks wrong at a glance | New hero, check price vs bracket |
| High views, high saves, low showings | Price. Buyers like it and are waiting | Price conversation |
| Showings healthy, no offers, feedback says "nice but..." | Condition or layout relative to price | Fix the one thing, or price |
| Showings healthy, no offers, feedback says "chose another home" | Competition is winning on value | Compare against the homes that beat us, adjust |
| Low views everywhere | Exposure gap (syndication, search bracket, remarks) or a dead price band | Syndication recheck, bracket check, remarks rewrite |
| Feedback silent | Agents not responding | VA calls each showing agent personally on Tuesday |
| Neighborhood pendings at lower $/sqft | Market moved under us | Show the seller the pendings, price conversation |

## 5. Tuesday call (Charles, listings over 14 days)

"Did you get a chance to read the update? What jumped out? Here's what I'd do this week and why." Ten minutes. Confirm the decision from section 8. Log the call in the Opportunity.

## 6. Weekly checklist

VA
- [ ] Monday 8am: start data pull, one row per active listing
- [ ] Monday 10am: run `CB Seller Concierge` for each listing, draft in Command, ping Charles
- [ ] Monday 12pm: all reports sent, Opportunity notes updated, data sheet saved
- [ ] Tuesday: call any showing agent who did not give feedback
- [ ] Note any Day 14 or Day 30 checkpoint due this week in `#listings`

Charles
- [ ] Monday by 11:30am: sections 3, 8, 9 written on every report, approved
- [ ] Tuesday: call every seller over 14 days
- [ ] Hold Day 14 and Day 30 reviews on schedule (listing-launch-playbook.md section 5)
