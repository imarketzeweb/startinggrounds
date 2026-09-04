# SmartPlan: `SP-Speed to Lead`

## Purpose
The first 10 days for any web or social lead. Day 0 sends the instant acknowledgment (the only client-facing message automation sends without a human reading it), creates the human call task, and then keeps a light, useful cadence so the lead hears from Charles six more times while the VA and Charles work the phone. Goal: a conversation, then a consult booked.

## Entry trigger
- Tag `New-Lead` added with any of `Src-Website`, `Src-Social`, `Src-Sign`, `Src-Paid` (Zapier Z-01, Z-03, Z-05 add the contact to this plan; fallback: VA adds in SOP-01).
- Adds tag `8x8-Active`? No. This plan is standalone; at exit the contact moves to a nurture plan or the 8x8.

## Exit conditions
- Contact replies or a call connects: VA marks the plan complete, changes status tag to `Hot` or `Nurture`, and starts `SP-Seller Nurture`, `SP-Buyer Nurture`, or `SP-Capital Partner Program` (after the Criteria Call) as appropriate. Consult booked: Opportunity stage moves to Appointment Set / Consult Set / Criteria Call.
- Day 10 with no response: plan ends, VA adds `Nurture` and the type's nurture plan; Haven't Met contacts also enter `SP-12 Direct (Haven't Met)`.
- Contact says stop or unsubscribes: remove from plan, tag `Dead`, note why.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0, immediate | Text | Instant acknowledgment | Hi [First Name], Charles Brewer here with Keller Williams. Got your note through my site, thank you. I'm going to call you shortly from [PHONE], so you know who's calling. If there's a better time or you'd rather text, just reply here. -Charles | Command (auto) |
| 2 | Day 0, immediate | Email | Subject: Got it, [First Name]. Here's what happens next | Hi [First Name], thanks for reaching out about [buying / selling / investing] in [MARKET]. Here is what to expect: I'll call you within the next few minutes. If we miss each other, I'll text, and you can grab a time that works at [CALENDLY LINK]. No pressure and no scripts. My job on the first call is to understand what you're trying to do and tell you honestly whether I can help. Talk soon. Charles Brewer, Keller Williams [BROKERAGE OFFICE], [PHONE], [EMAIL] | Command (auto) |
| 3 | Day 0, immediate | Call task | "CALL NEW LEAD within 5 min: [First Name] [Last Name]" | Task description: open the #leads thread, read the CB Lead Responder drafts, call. Log "called" in the thread. Use the 3 qualifying questions. | Charles (VA if Charles unavailable) |
| 4 | Day 1, 9:00am | Text | Follow-up with value | Hi [First Name], Charles again. In case yesterday got busy: I put together a quick [MARKET] market snapshot for [NEIGHBORHOOD], the kind of thing I'd show you on a first call. Want me to send it? Reply YES and I'll shoot it over. -Charles | VA sends after review |
| 5 | Day 2, 11:00am | Email | Subject: The [MARKET] snapshot I mentioned | Hi [First Name], here is the short version of what's happening in [MARKET] right now: [3 bullets: median price, days on market, inventory trend, from this month's market report]. What this means for you depends on your timeline, which is the first thing I'd want to understand. If a 15-minute call makes sense, pick a time here: [CALENDLY LINK]. If not yet, no problem, I'll keep the updates useful and short. Charles Brewer, Keller Williams, [PHONE] | VA (fills bullets from monthly report), Charles approves |
| 6 | Day 3, 2:00pm | Call task | Second call attempt | Task: call, leave a voicemail if no answer: "Hi [First Name], Charles Brewer with Keller Williams. Just following up on your note from a few days ago. I'm at [PHONE] whenever you're ready. No rush." Log result in Command. | Charles or VA |
| 7 | Day 5, 10:00am | Text | Video text | Hi [First Name], I recorded a 60-second video answering the question I get most from people in your situation: [link to the "What happens first when you buy / sell / invest" video]. Worth a look with your coffee. -Charles | VA sends after review |
| 8 | Day 7, 9:00am | Email | Subject: Two ways I can help, one question | Hi [First Name], a week in, so a quick check. Two ways I help people at your stage: a no-obligation consult where we map your timeline and numbers, or simply staying in touch with the monthly [MARKET] report until the timing is right. One question: which of those fits better right now? Reply with "consult" or "updates" and I'll take it from there. Charles Brewer, Keller Williams, [PHONE], [CALENDLY LINK] | Charles approves, VA sends |
| 9 | Day 10, 10:00am | Text | Close the loop | Hi [First Name], last note from me for a bit. I'll add you to my monthly [MARKET] update so you have real numbers when you need them. Whenever the timing's right, I'm at [PHONE]. Thanks for reaching out. -Charles | VA sends after review |
| 10 | Day 10, 10:05am | Task | Triage and exit | Task for VA: set status tag (`Hot` / `Nurture` / `Dead`), start the nurture plan for the type, add `SP-12 Direct (Haven't Met)` if Haven't Met, close this plan. Log in Lead Log. | VA |

## Notes
- Steps 1 and 2 are the only auto-sends. In Command, set steps 4, 5, 7, 8, 9 as "task to send" or pause-for-approval steps if your Command version supports it; if it does not, build them as tasks that contain the copy and have the VA send manually.
- Personalize the type words ([buying / selling / investing]) with three copies of this plan if Command cannot merge them: `SP-Speed to Lead` with variants noted in the step name.
- Fair Housing: nothing here describes people or neighborhoods by who lives there. Keep it that way in edits.
