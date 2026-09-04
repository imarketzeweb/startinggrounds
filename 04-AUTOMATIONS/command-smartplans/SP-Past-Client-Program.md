# SmartPlan: `SP-Past Client Program`

## Purpose
Year one after closing. Turns a closed client into a raving fan and a referral source: closing-day thanks, Day 7 review request, 30-day check-in, the boring-but-valuable homeowner touches (tax, insurance, maintenance), and the one-year home anniversary. At month 12 the client graduates into `SP-33 Touch (Met)` for life. Service standard 5: every closed client enters this plan the day of closing.

## Entry trigger
- Opportunity stage `Closed` on any pipeline (Zapier Z-09 adds; fallback: VA in SOP-08). Plan adds `Past-Client-Program`. Day 0 = closing date.

## Exit conditions
- Day 365: plan removes `Past-Client-Program`, adds `33-Touch`, starts `SP-33 Touch (Met)`. The home anniversary date lives on the contact for the yearly reminder (Z-09 also creates the calendar event).
- Client asks to stop: remove, note why. Past clients are never tagged `Dead` without Charles's say.

## Steps

| Step | Day offset | Channel | Subject or purpose | Full copy | Owner |
|---|---|---|---|---|---|
| 1 | Day 0 | Text | Closing day | Hi [First Name], Charles. It's official. Congratulations on [ADDRESS]. Thank you for trusting me with this; it was a privilege. I'm still your agent for life, so anything home-related, I'm here. Enjoy tonight. -Charles | Charles |
| 2 | Day 1 | Call task | Personal thank-you call | Task for Charles: call, no agenda except thanks and "how was the first night?" Ask if anything from closing is unresolved. | Charles |
| 3 | Day 2 | Email | Subject: Your closing documents and the after-closing checklist | Hi [First Name], your closing documents are attached (or here: [link]). Keep them with your tax records; the settlement statement matters at tax time. Checklist for the first two weeks: change the locks, file for the homestead exemption if you're eligible ([link]), confirm utilities are in your name, update your address with [list], and register your warranty items. [VA NAME] is a text away for any of it. Charles | VA sends, Charles approves once |
| 4 | Day 3 | Task | Closing gift delivered | Task for VA: confirm the closing gift (ordered by Z-09) was delivered; log in Command. | VA |
| 5 | Day 7 | Email | Subject: One small favor, [First Name] | Hi [First Name], a week in, and I hope the house already feels like yours. A small favor: my business grows on reviews from clients like you. If you have two minutes, would you share a few words here? [Google review link]. It helps the next family find me. Thank you, truly. Charles Brewer, Keller Williams, [PHONE] | Charles approves, VA sends |
| 6 | Day 7 | Task | Review request check | Task for VA: confirm the review email went; if the client prefers text, send the link by text. Log. If a review posts, Z-11 handles the thank-you. | VA |
| 7 | Day 30 | Call task | 30-day check-in | Script: "Hi [First Name], Charles. A month in. How's the house? Anything not working the way you expected? Need a contractor name?" Log anything that needs follow-up. | Charles |
| 8 | Day 45 | Email | Subject: The vendor list, updated | Hi [First Name], the [MARKET] Homeowner's Vendor List: plumber, electrician, handyman, HVAC, cleaner, landscaper, roofer, painter. These are people my clients use and rate. Text me if any of them ever falls short; I keep the list honest. Charles | VA sends |
| 9 | Day 60 | Text | Quick text | Hi [First Name], Charles. Two months in. Quick question: if a friend or coworker mentioned they were thinking about moving, would you be comfortable sending them my way? No pressure; just letting you know I'd treat them like I treated you. -Charles | Charles approves, VA sends |
| 10 | Day 90 | Email | Subject: Your home, three months later: values and taxes | Hi [First Name], a quarterly note. Homes near [ADDRESS] have [sold/listed] at [range] since you closed. Also on the list this quarter: check your property tax assessment when it arrives (I can help you read it), and review your homeowner's insurance now that you've lived there a bit. Charles | VA pulls sales, Charles approves |
| 11 | Day 120 | Mail task | Handwritten note | Task: Charles writes a note referencing something specific about their move. VA mails with two business cards. | Charles, VA |
| 12 | Day 150 | Email | Subject: Seasonal maintenance for [ADDRESS] | Hi [First Name], the seasonal checklist for your home: [5 items for the season]. Fifteen minutes now saves a repair later. Need a name for any of it? Reply and I'll send one. Charles | VA sends |
| 13 | Day 180 | Call task | Six-month call | Script: "Hi [First Name], Charles. Half a year. What's been the best thing about the house? Anything I can help with? And is there anyone in your life thinking about a move?" | Charles |
| 14 | Day 210 | Email | Subject: [MARKET] market update and what it means for your equity | Hi [First Name], the [MARKET] market at a glance: [3 bullets]. For you, that's an estimated [range] of equity built since closing, based on nearby sales. Curious about the specifics? Reply "equity" and I'll send a short update. Charles | VA fills, Charles sets the range |
| 15 | Day 240 | Text | Quick text | Hi [First Name], Charles. Thinking of you. If any home project is on the list this season and you want a second opinion or a vendor, I'm here. -Charles | VA sends |
| 16 | Day 270 | Email | Subject: Nine months in: the tax-time checklist | Hi [First Name], before tax season: your settlement statement, mortgage interest statement (Form 1098), property taxes paid, and any energy-efficiency upgrades. Hand these to your CPA; they'll know what applies. Not tax advice, just the list. Charles | VA sends |
| 17 | Day 300 | Mail task | Item of value | Task: mail the "[MARKET] Favorites" card or the seasonal checklist with a sticky note from Charles. | VA |
| 18 | Day 330 | Email | Subject: Almost a year at [ADDRESS] | Hi [First Name], you're coming up on one year in the house. I'll call on the anniversary, but wanted to say it now: thank you again. If you know anyone considering a move in the next year, I'd be honored to help them. Charles | Charles approves, VA sends |
| 19 | Day 358 | Mail task | Anniversary card | Task: VA mails the home anniversary card, signed by Charles, to arrive by Day 365. | VA, Charles signs |
| 20 | Day 365 | Call task | Home anniversary call | Script: "Happy home anniversary, [First Name]. One year today. Charles Brewer. How's the house treating you?" | Charles |
| 21 | Day 365 | Task | Graduate to 33 Touch | Task for VA: remove `Past-Client-Program`, add `33-Touch`, start `SP-33 Touch (Met)`. Confirm the anniversary calendar event exists. | VA |

## Notes
- Steps 3, 8, 12, 16 are pre-approved templates the VA sends alone once Charles has approved the master copy.
- Any equity or value range comes from Charles, never from the VA or a portal estimate.
- Capital partners who are also past clients stay in `SP-Capital Partner Program` in parallel.
