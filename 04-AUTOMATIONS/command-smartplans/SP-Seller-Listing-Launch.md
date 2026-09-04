# SmartPlan: `SP-Seller Listing Launch`

## Purpose
From Listing Signed through the first 30 days on market. Keeps the seller informed before they have to ask (the white glove promise), drives the launch checklist, and schedules the Day 14 and Day 30 reviews. Pairs with `05-SELLER-SYSTEM/listing-launch-playbook.md`; this plan is the Command mechanism behind that playbook.

## Entry trigger
- Opportunity stage `Listing Signed` (Zapier Z-06 adds the contact to the plan; fallback: VA). Day 0 = the day the listing agreement is signed. Assumes a 14-day pre-launch; adjust the offsets if the live date is sooner.

## Exit conditions
- Opportunity moves to `Under Contract`: Z-07 (or VA) removes this plan and starts `SP-Seller Under Contract`.
- Listing withdrawn or expired: remove from plan, tag `Nurture`, start `SP-Seller Nurture`.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Email | Subject: Welcome aboard, [First Name]. Here's the launch plan | Hi [First Name], thank you for trusting me with [ADDRESS]. Here is what happens next: photos, drone, video, and 3D tour on [date]; your home goes live in Coming Soon on [date] and fully live on [date]. I'll send a written update every Monday from now until closing, and you'll hear from me before every milestone, not after. [VA NAME] on my team will coordinate vendors and will introduce themselves shortly. Questions anytime: [PHONE]. Charles Brewer, Keller Williams [BROKERAGE OFFICE] | Charles approves, VA sends |
| 2 | Day 0 | Task | Launch checklist (VA) | Task: confirm photographer, 3D, floor plan, sign and QR rider ordered, single-property page started, Marketing Kit draft in `04-Marketing-Kit`, Active Listings sheet row created. See SOP-03. | VA |
| 3 | Day 1 | Email | Subject: Meet [VA NAME], and the photo-day prep list | Hi [First Name], I'm [VA NAME], Charles's listing coordinator. I'll be your point of contact for scheduling and logistics; Charles handles pricing, showings, and negotiations. Photo day is [date] at [time]. Prep list attached: lights on, blinds open, counters clear, cars out of the driveway, pets arranged, personal items tucked away. Text me with anything: [VA phone]. [VA NAME], Team Charles Brewer, Keller Williams | VA sends (VA may approve) |
| 4 | Day 3 | Call task | Pre-photo check-in | Script: "Hi [First Name], Charles. Photos are [day]. Anything on the prep list you need help with? I can send a handyman or cleaner." | Charles |
| 5 | Day 6 | Text | Day-before photos | Hi [First Name], [VA NAME] here. Photos tomorrow at [time]. Lights on, blinds open, counters clear, and you're set. The photographer will be there about 2 hours. Thank you! | VA (VA approves) |
| 6 | Day 9 | Email | Subject: Your photos are in, and the Coming Soon plan | Hi [First Name], your photos, video, and 3D tour are ready: [links]. They look great. Your Coming Soon post goes out [date] to [X] followers and my database of [Y] contacts, and the sign goes up [date]. Full launch is [date] at 9am. Please review the MLS description attached and reply with any corrections by [date]. Charles | Charles approves, VA sends |
| 7 | Day 12 | Task | Pre-launch QA | Task: run the QA checklist in SOP-03 (MLS draft, photos order, 3D link, floor plan, property page live in preview, sign installed, social scheduled, email Campaign built, showing instructions set). Report to Charles in #listings. | VA |
| 8 | Day 14 | Text | Live day | Hi [First Name], you're live. [ADDRESS] is on the MLS, all portals, and my site: [link]. Showing requests will come through [ShowingTime/app]; approve them fast, and I'll handle everything else. First written update Monday. -Charles | Charles approves, VA sends |
| 9 | Day 14 | Email | Subject: Live: what to expect in week one | Hi [First Name], week one is the loudest week. Expect the most showings in the first 7 to 10 days, feedback within 24 hours of each one (I'll send it verbatim plus what it means), and your first Monday report. Please keep the home show-ready and approve showing requests within an hour when you can. If you get a call from anyone other than me or [VA NAME], send them my way. Charles | Charles approves, VA sends |
| 10 | Day 17 | Call task | First-showings call | Script: "Hi [First Name], Charles. [X] showings so far. Here's what I'm hearing... Any questions from your side?" | Charles |
| 11 | Day 21 | Email | Subject: Open house this weekend: the plan | Hi [First Name], open house is [day] from [time]. I'll be there, [VA NAME] handles sign-ins, and every visitor becomes a follow-up in my system the same day. Please be out of the house by [time]; I'll text when we wrap with a headcount and first impressions. Charles | VA, Charles approves |
| 12 | Day 28 | Task | Day 14 on-market review | Task for Charles: run the Day 14 review (showings, feedback themes, online views vs. area average, price position). Call the seller with the review; VA drafts the memo via `CB Seller Concierge`. | Charles, VA |
| 13 | Day 35 | Email | Subject: Three weeks in: where we stand | Hi [First Name], three weeks live: [X] showings, [Y] online views, [Z] saves, feedback themes: [themes]. What I recommend next: [Charles's recommendation]. Let's talk [day] at [time]. Charles | Charles writes recommendation |
| 14 | Day 44 | Task | Day 30 price and strategy review | Task for Charles: Day 30 review meeting with seller, in person or video. VA prepares comps and traffic summary. Any price discussion is Charles only. | Charles |

## Notes
- Monday reports are not in this plan; Z-08 creates them weekly so they never depend on a day offset.
- The `Coming Soon` and `Just Listed` social posts are triggered by Z-07 on stage change, not by this plan.
- Steps 3 and 5 are logistics texts the VA may send without Charles's approval (SOP-03 grants this).
