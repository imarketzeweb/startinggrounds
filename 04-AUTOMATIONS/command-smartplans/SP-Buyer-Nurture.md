# SmartPlan: `SP-Buyer Nurture`

## Purpose
For buyer leads who are real but not ready (B or C after `SP-Speed to Lead`, or who have not yet booked a consultation). Six months of buyer-specific value every two to three weeks, aimed at one outcome: a buyer consultation before the first showing.

## Entry trigger
- Tags `Buyer` + `Nurture` added by the VA at Speed to Lead exit (SOP-01). Plan adds `Buyer-Nurture`.

## Exit conditions
- Opportunity moves to `Consult Set`: VA pauses the plan.
- Day 180: plan removes `Buyer-Nurture`; VA routes to `SP-33 Touch (Met)` or `SP-12 Direct (Haven't Met)`.
- Contact says stop: remove, tag `Dead`.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Email | Subject: How buying works here, [First Name] (the short version) | Hi [First Name], since a purchase is on your horizon, here is how I work with buyers: a 45-minute consultation first (your needs, your numbers, the process, the plan), then showings with an itinerary the night before and a recap the same evening, then a written offer strategy when you find the one. No pressure to start; when you're ready, book here: [CALENDLY LINK]. Until then I'll send useful, short notes about [MARKET]. Charles Brewer, Keller Williams, [PHONE] | VA sends after review |
| 2 | Day 12 | Email | Subject: What [PRICE RANGE] buys in [MARKET] right now | Hi [First Name], three homes that closed this month in your range: [address, beds/baths, price, days on market] x3. This is the real market, not the listing photos. Want a saved search built to your criteria (not the portal's)? Reply "search" and I'll set it up in an hour. Charles | VA pulls sales, Charles approves |
| 3 | Day 19 | Call task | Check-in call | Script: "Hi [First Name], Charles Brewer. Wanted to check in on your timing and see if the saved search is showing you the right stuff. What's been the biggest question so far?" | Charles |
| 4 | Day 33 | Email | Subject: The pre-approval question, answered | Hi [First Name], the one thing that separates buyers who win from buyers who wait: a full pre-approval (not a pre-qualification) before the first showing. It takes a few days and tells you your real number. I work with two lenders who are fast and honest; if you want an intro, reply "lender" and I'll connect you, no obligation. Charles | VA, Charles approves |
| 5 | Day 47 | Text | Quick text | Hi [First Name], Charles. A client just closed on a home in [NEIGHBORHOOD] with a [X]-day close. Happy to tell you how we did it whenever you're curious. -Charles | VA drafts with a real example, Charles approves |
| 6 | Day 61 | Email | Subject: Five things buyers wish they'd known about [MARKET] | Hi [First Name], from my last 20 buyer clients: 1) [item], 2) [item], 3) [item], 4) [item], 5) [item]. I go through all of these in the consultation so there are no surprises later. [CALENDLY LINK]. Charles | VA, Charles approves |
| 7 | Day 75 | Call task | Second call | Script: "Hi [First Name], Charles. Has the timeline moved at all? If it helps to talk through numbers before you're ready to look, that's what the consult is for." | Charles |
| 8 | Day 89 | Email | Subject: Quarter check: [MARKET] and your budget | Hi [First Name], this quarter: [3 bullets: prices, inventory, rates]. What it means for a buyer in your range in one sentence: [Charles's read]. Nothing here requires action, but if you want your numbers updated, I'm a reply away. Charles | VA fills, Charles writes the read |
| 9 | Day 110 | Mail task | Handwritten note | Task: Charles writes "[First Name], whenever you're ready to look, I've got the plan. No rush. Charles". VA mails with the buyer roadmap card. | Charles, VA |
| 10 | Day 131 | Email | Subject: What to look for at a showing (my checklist) | Hi [First Name], the showing checklist I give clients: water stains, window age, roof from the street, panel type, water heater date, drainage, noise at two different times of day. Print it: [link]. And when you're ready to look for real, we'll go together. Charles | VA, Charles approves |
| 11 | Day 152 | Text | Text | Hi [First Name], Charles. Still here, still happy to help when the timing's right. Any question, any time. -Charles | VA |
| 12 | Day 173 | Call task | Six-month decision call | Script: "Hi [First Name], Charles. Six months in: this year, next year, or on hold? I'll match how often you hear from me." | Charles |
| 13 | Day 180 | Task | Exit and re-route | Task for VA: remove `Buyer-Nurture`; route to 33 Touch or 12 Direct; if consult set, move Opportunity and stop. | VA |

## Notes
- Saved searches come from Command (or the MLS portal). The VA builds them; Charles reviews criteria.
- No lender or rate advice in any email beyond "talk to a lender." Fair Housing: property and process only.
