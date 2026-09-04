# SmartPlan: `SP-8x8 New Contact`

## Purpose
MREA's 8x8: eight touches in eight weeks for a new contact you have met (open house visitor, referral, event, sphere introduction). The goal is to be remembered as the agent in [MARKET] and to earn the right to be in the 33 Touch for life. The mix is intro note, market report, item of value, call, text, video, handwritten card, call.

## Entry trigger
- Tag `Met` added to a contact tagged `New-Lead` (or `Sphere`) with `Src-OpenHouse`, `Src-Referral`, `Src-Sphere`, or `Src-Event`. Zapier Z-04 adds open house sign-ins; the VA adds the rest (SOP-02). The plan adds tag `8x8-Active` on entry.

## Exit conditions
- Week 8 complete: plan removes `8x8-Active`, adds `33-Touch`, starts `SP-33 Touch (Met)`.
- Contact becomes an active buyer or seller: VA closes this plan and moves them to the type's nurture or launch plan.
- Contact asks to stop: remove, tag `Dead`, note why.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Email | Subject: Good meeting you, [First Name] | Hi [First Name], it was good to meet you [at the open house on [ADDRESS] / through [Referrer]]. I'm Charles Brewer with Keller Williams here in [MARKET]. I don't do pushy follow-up. What I do is keep people informed with real numbers and answer questions straight, whether or not you're buying or selling soon. If anything comes up about a home, a neighborhood, or a number you saw online, text me at [PHONE]. Glad to know you. Charles Brewer, Keller Williams [BROKERAGE OFFICE] | VA sends after review |
| 2 | Day 7 | Email | Subject: This month in [MARKET] real estate | Hi [First Name], here's the [Month] [MARKET] market report: [link or attached PDF]. The short version: median price [X], average days on market [Y], inventory is [up/down] from last month. What I'm watching: [one sentence]. If you want the numbers for your own street, reply "my street" and I'll pull them. Charles | VA (inserts current report) |
| 3 | Day 14 | Mail task | Item of value: the "[MARKET] Homeowner's Vendor List" | Task: mail the printed vendor list (plumber, electrician, handyman, cleaner, landscaper, inspector) with a sticky note: "[First Name], the list everyone asks me for. Keep it on the fridge. Charles [PHONE]". Log in Command. | VA orders, Charles signs |
| 4 | Day 21 | Call task | Check-in call | Script: "Hi [First Name], Charles Brewer. No agenda, just checking in after we met at [place]. Did the vendor list show up? Anything on your mind about the market?" Voicemail if no answer, under 20 seconds. Log the outcome. | Charles |
| 5 | Day 28 | Text | Quick text | Hi [First Name], Charles Brewer. Saw a home near [NEIGHBORHOOD] just closed at [PRICE], thought you'd find it interesting given what we talked about. If you ever want to know what that means for you, I'm a text away. -Charles | VA drafts with a real recent sale, Charles approves |
| 6 | Day 35 | Text | Video text | Hi [First Name], made a short video this week: "3 things I'd do before selling in [MARKET]" (works for buyers too, it's about what sellers are thinking). [link]. 90 seconds. -Charles | VA sends after review |
| 7 | Day 42 | Mail task | Handwritten card | Task: Charles writes a card: "[First Name], enjoyed meeting you. If a friend ever mentions moving, I'd be honored to help them the way I'd want my own family helped. Charles". Include two business cards. VA addresses and mails. | Charles writes, VA mails |
| 8 | Day 56 | Call task | Closing call of the 8x8 | Script: "Hi [First Name], Charles. It's been about two months since we met. I'll keep you on my monthly update unless you'd rather not. Quick question: is there anyone you know thinking about a move this year? I'd take great care of them." Log referrals. | Charles |
| 9 | Day 56 | Task | Graduate to 33 Touch | Task for VA: confirm `Met` tag, remove `8x8-Active`, add `33-Touch`, start `SP-33 Touch (Met)`. If the contact never responded to anything, ask Charles whether to move to `SP-12 Direct (Haven't Met)` instead. | VA |

## Notes
- If Command's SmartPlan builder supports "remove tag / add tag" actions, use them on step 9; otherwise the task carries the instruction.
- Every email is Fair Housing safe: property and process only, never people.
- Open house visitors: step 1 is preceded by the same-day text from Z-04, which is not part of this plan.
