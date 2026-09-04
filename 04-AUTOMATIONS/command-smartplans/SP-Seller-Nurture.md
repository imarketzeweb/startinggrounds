# SmartPlan: `SP-Seller Nurture`

## Purpose
For seller leads who are real but not ready (temperature B or C after `SP-Speed to Lead`). Keeps Charles in front of them with seller-specific value every two to three weeks for six months, so when they are ready, he is the call. Ends with either an appointment or a hand-off to the 33 Touch / 12 Direct.

## Entry trigger
- Tags `Seller` + `Nurture` added by the VA at Speed to Lead exit (SOP-01) or when a listing appointment is postponed. Plan adds tag `Seller-Nurture`.

## Exit conditions
- Opportunity moves to `Appointment Set`: VA pauses the plan (Command: remove from plan; re-add later if the appointment falls through).
- Day 180 reached: plan removes `Seller-Nurture`; VA confirms `Met` (33 Touch) or `Haven't Met` (12 Direct) and moves them there.
- Contact says stop: remove, tag `Dead`.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Email | Subject: Your timeline is the plan, [First Name] | Hi [First Name], you mentioned a move is likely in the next [few months / year]. That's the right time to start thinking, not the time to list. Between now and then I'll send short, seller-specific notes: what to fix, what to skip, what your street is doing. Nothing salesy. When you want a proper plan with real numbers, that's a 30-minute conversation at your kitchen table: [CALENDLY LINK]. Charles Brewer, Keller Williams, [PHONE] | VA sends after review |
| 2 | Day 14 | Email | Subject: What your street sold for this quarter | Hi [First Name], three recent sales near [ADDRESS]: [sale 1], [sale 2], [sale 3]. The range tells you more than any online estimate. If you want me to narrow it to your home specifically, reply "range" and I'll do a quick desk review. Charles | VA pulls sales, Charles approves |
| 3 | Day 21 | Call task | Check-in call | Script: "Hi [First Name], Charles Brewer. Sent over the recent sales near you. Any of those surprise you? Anything changed with your timing?" Log outcome and any date. | Charles |
| 4 | Day 35 | Email | Subject: Fix this, skip that: pre-sale prep in [MARKET] | Hi [First Name], the pre-sale list that pays: paint, lighting, deep clean, landscaping tidy, small repairs. The list that usually doesn't: new kitchen, new roof (unless failing), additions. I'll walk your home and tell you exactly which bucket each item is in, free, before you spend anything. [CALENDLY LINK]. Charles | VA, Charles approves |
| 5 | Day 49 | Text | Quick text | Hi [First Name], Charles. A seller I worked with this month netted [X] more than the first offer by doing two small prep items. Happy to tell you which two. -Charles | VA drafts with a real example, Charles approves |
| 6 | Day 63 | Email | Subject: How I sell a home in [MARKET] (the 5-stage launch) | Hi [First Name], since you'll interview agents at some point, here is what every listing of mine gets: pro photos, drone, video walkthrough, 3D tour, floor plan, its own web page, a 5-stage social campaign, an email to my database, and a written update to you every Monday. See a recent example: [link]. Compare it to anything else you're shown. Charles | VA, Charles approves |
| 7 | Day 77 | Call task | Second call | Script: "Hi [First Name], Charles. Quick one: has the timing come into focus at all? If a walkthrough would help you plan, I'm happy to come by, no obligation." | Charles |
| 8 | Day 91 | Email | Subject: Quarter check: [MARKET] and your equity | Hi [First Name], this quarter in [MARKET]: [3 bullets]. For you, the question is what your equity looks like now vs. when you plan to move. I can show you both numbers in ten minutes. [CALENDLY LINK]. Charles | VA fills, Charles approves |
| 9 | Day 112 | Mail task | Handwritten note | Task: Charles writes: "[First Name], thinking about your move. Whenever you're ready, I've got a plan for you. No pressure. Charles". VA mails. | Charles, VA |
| 10 | Day 133 | Email | Subject: The seller mistake I see most | Hi [First Name], the most expensive mistake in [MARKET]: listing before the prep is done, then cutting the price. The fix is a 30-day prep calendar, which I build for every seller. Want yours, even if the move is a year out? Reply "calendar". Charles | VA, Charles approves |
| 11 | Day 154 | Text | Text | Hi [First Name], Charles. Still here whenever you're ready. Anything you need in the meantime, a contractor name, a number, a straight answer, just text. -Charles | VA |
| 12 | Day 175 | Call task | Six-month decision call | Script: "Hi [First Name], Charles. It's been about six months. Where does a move sit for you now: this year, next year, or on hold? I'll adjust how often you hear from me." Set next step. | Charles |
| 13 | Day 180 | Task | Exit and re-route | Task for VA: remove `Seller-Nurture`; if Met, confirm `SP-33 Touch (Met)`; if Haven't Met, `SP-12 Direct (Haven't Met)`; if appointment set, move Opportunity and stop. | VA |

## Notes
- Emails 2, 5, and 8 need real local numbers. The VA keeps a monthly "recent sales by area" sheet so these take minutes, not hours.
- Never include a price opinion the VA generated. Any range comes from Charles.
