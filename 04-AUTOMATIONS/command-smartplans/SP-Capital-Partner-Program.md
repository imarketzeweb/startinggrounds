# SmartPlan: `SP-Capital Partner Program`

## Purpose
The nurture plan for capital partners. Charles sources fix-and-flip deals and project-manages them white glove; partners fund them. This plan onboards a new partner, shows them what a Charles deal looks like before they ever commit capital, keeps them informed monthly with the deals Charles passed on and why (which builds more trust than the deals he took), and puts a quarterly portfolio call on Charles's calendar. Deal-specific communication (Deal Alerts, Friday project updates, distribution statements) is handled by Z-12, Z-15, and Z-16, not by this plan.

## Entry trigger
- Tag `Capital-Partner` added when the Investor Opportunity moves to `Partner Onboarded` after the Criteria Call (VA, SOP-02). Plan adds `Capital-Partner-Program`. Prerequisite: the partner's profile row exists in the `Capital Partners` sheet (Tier, Min Deal, Max Deal, Strategies, Markets) so Z-12 can match them.

## Exit conditions
- Partner asks to pause: VA sets Status Active = No in the sheet (Z-12 stops matching) and removes this plan; keep the tag and add `Nurture`.
- Partner exits entirely: remove plan, remove `Capital-Partner`, tag `Sphere` and `Met`, start `SP-33 Touch (Met)`.
- Plan repeats yearly for active partners (steps 5 onward form the ongoing cadence).

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Email | Subject: Welcome aboard, [First Name]. Your partner packet | Hi [First Name], thank you for the conversation and for your interest in partnering on deals in [MARKET]. Attached is the Capital Partner Packet: how I source deals, how I underwrite (ARV, rehab, the 70% rule as a floor), how I manage the project, how partners are updated (a written update every Friday during rehab, a distribution statement at sale), and the structure options our attorney has drafted. Nothing here is a commitment. Read it, mark it up, and we'll walk through questions on our next call. Charles Brewer, Keller Williams [BROKERAGE OFFICE], [PHONE] | Charles approves, VA sends |
| 2 | Day 0 | Task | Partner profile check | Task for VA: confirm the Capital Partners sheet row is complete (Tier, Min/Max Deal, Strategies, Markets, Status Active = Yes); add note in Command; confirm Opportunity at `Partner Onboarded`. | VA |
| 3 | Day 3 | Email | Subject: A sample Deal Memo so you know what to expect | Hi [First Name], before a live deal lands in your inbox, here is a sample Deal Memo from a completed project: [link to sanitized memo]. Notice what's in it: the numbers with formulas shown, why the deal made the list, what could have killed it, the timeline, and the partner ask. Live deals arrive the same way, with a 48-hour first-look window for partners at your tier. Reply with any question, or anything you'd want added. Charles | VA sends, Charles approves the sample once |
| 4 | Day 7 | Call task | Packet review call | Script for Charles: "Hi [First Name], Charles. Did the packet and the sample memo make sense? What would you need to see on a live deal to say yes? What's your comfortable range, and how fast can you move once you commit?" Update the sheet with answers. | Charles |
| 5 | Day 14 | Email | Subject: How I say no to deals (and why that matters to you) | Hi [First Name], most of my week is passing on deals. This month I looked at [X] and moved on [Y]. The ones I passed on, and why: [3 short examples: address area, the number that killed it]. I share this every month so you can see the filter your capital sits behind. When a deal does make it through, you'll know it earned it. Charles | VA compiles from Deal Board, Charles approves |
| 6 | Day 30 | Email | Subject: This month: deals we passed on, deals in progress | Hi [First Name], the monthly partner note. Passed on: [3 examples with the reason]. In progress: [address, stage, one-line status] for any deal you're in, and a one-line note on deals you aren't in so you see the whole board. Coming up: [what's in the pipeline]. Questions or capital changes on your side? Reply or book: [CALENDLY LINK]. Charles | VA drafts via `CB Investor Analyst`, Charles approves |
| 7 | Day 60 | Email | Subject: Monthly partner note, [Month] | Same structure as step 6: passed-on deals with reasons, in-progress board, coming up. Keep it under 250 words. | VA, Charles approves |
| 8 | Day 90 | Call task | Quarterly portfolio call | Task for Charles: 30-minute call or video. Agenda: deals completed this quarter and returns, deals in progress, partner's capital availability next quarter, any change in criteria, feedback on updates. VA preps a one-page portfolio summary from the Deal Board and Capital Partners sheet the day before. Update Tier if warranted. | Charles, VA preps |
| 9 | Day 90 | Email | Subject: Your quarterly portfolio summary | Hi [First Name], ahead of our call, here is your one-page summary: deals participated: [list], capital deployed: [X], returned: [Y], preliminary return: [Z]%, deals in progress: [list]. Figures are from our records and the accountant's statements; your CPA has the final word. Talk [day]. Charles | VA prepares, Charles approves |
| 10 | Day 120, 150 | Email | Monthly partner notes | Same structure as step 6, months 4 and 5. | VA, Charles approves |
| 11 | Day 180 | Call task | Quarterly portfolio call (Q2) | Same agenda as step 8. Ask directly: "Are we still a fit? Anything you'd change?" | Charles |
| 12 | Day 210, 240 | Email | Monthly partner notes | Months 7 and 8. | VA, Charles approves |
| 13 | Day 270 | Call task + Email | Quarterly portfolio call (Q3) + summary | As steps 8 and 9. | Charles, VA |
| 14 | Day 300, 330 | Email | Monthly partner notes | Months 10 and 11. | VA, Charles approves |
| 15 | Day 350 | Mail task | Year-end thank-you | Task: Charles handwrites a note: "[First Name], thank you for trusting me with your capital this year. [One specific deal memory]. Looking forward to next year. Charles". VA mails with the annual partner summary. | Charles, VA |
| 16 | Day 360 | Call task + Email | Annual review call + annual summary | Agenda: full-year returns, next year's capital plan, criteria update, tier review. VA preps the annual summary email (same format as step 9, full year). Restart the plan from step 5. | Charles, VA |

## Notes
- No email in this plan states or implies guaranteed returns. Every number is historical or labeled preliminary, and the CPA/attorney line appears on every summary.
- Deal Alerts go only to partners matched by Z-12; this plan never sends deal offers.
- Add tag `Capital-Partner` and stages `Partner Onboarded`, `Deal Presented`, `Deal Committed`, `Acquisition Under Contract`, `Rehab`, `Listed`, `Sold`, `Repeat` to `00-START-HERE/conventions.md` so every document agrees.
