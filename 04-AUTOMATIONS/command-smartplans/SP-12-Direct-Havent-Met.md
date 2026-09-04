# SmartPlan: `SP-12 Direct (Haven't Met)`

## Purpose
MREA's 12 Direct: twelve direct-mail touches per year to the Haven't Met database (geographic farm, cold web leads that never replied, purchased lists, sign-in sheets from events where Charles did not personally meet the person). Keller's math: 12 Direct produces roughly one transaction per 50 Haven't Met contacts per year. The medium is mail because it reaches people who never opened an email. Every piece has one job: make Charles the obvious name in [MARKET] when a move comes up.

## Entry trigger
- Tag `Haven't Met` present and the contact is out of `SP-Speed to Lead` (Day 10, no reply) or was imported as a farm/list contact (SOP-02). The plan adds tag `12-Direct`.
- Command SmartPlans do not mail postcards. Each step is a monthly Mail task; the VA exports the `12-Direct` list to the mailing house on the 1st (SOP-09). Because the whole list mails together, anchor the plan to the 1st of the month.

## Exit conditions
- Contact responds (call, text, QR scan, form): VA moves them to `SP-Speed to Lead`, and on a real conversation retags `Met` and starts `SP-8x8 New Contact`.
- Mail returned undeliverable twice: tag `Dead`, note "bad address".
- Contact opts out: remove and tag `Dead`.

## The 12 postcards

| Step | Day offset | Channel | Headline | Body copy (postcard back, 40-70 words) | Owner |
|---|---|---|---|---|---|
| 1 | Jan 1 (Day 0) | Mail task | What did [NEIGHBORHOOD] homes actually sell for last year? | Not the Zestimate. The real closed prices, by street, for all of last year. I put the whole list on one page. Text "LIST" to [PHONE] or scan the code and I'll send it, no strings. Charles Brewer, Keller Williams [BROKERAGE OFFICE]. Licensed in [MARKET]. | VA orders, Charles approves design |
| 2 | Feb 1 (Day 31) | Mail task | The 3 repairs that pay you back (and the 2 that don't) | Before spending on a kitchen, read this. In [MARKET] last year, [item 1] returned about [X]%, [item 2] about [Y]%. A full remodel? Usually not. The full list is at [short URL]. Charles Brewer, Keller Williams. Real numbers for [MARKET] homeowners. [PHONE] | VA |
| 3 | Mar 1 (Day 59) | Mail task | Just Sold nearby: [ADDRESS], [PRICE], [X] days | Your neighbor's home at [ADDRESS] sold for [PRICE] after [X] days on the market. I share these so [NEIGHBORHOOD] owners know what's really happening. Curious what it means for your home? Scan for a no-pressure range. Charles Brewer, Keller Williams, [PHONE] | VA (uses Charles's or a public sold, marked as such) |
| 4 | Apr 1 (Day 90) | Mail task | Spring maintenance checklist (keep this one) | Gutters. HVAC service. Irrigation check. Exterior caulk. Roof look-over. Tear off and stick on the fridge. From Charles Brewer, Keller Williams, the agent who'd rather help you keep your house than rush you to sell it. Need a vendor? Text "VENDOR" to [PHONE]. | VA |
| 5 | May 1 (Day 120) | Mail task | Free: the [MARKET] Homeowner's Vendor List | Plumber. Electrician. Handyman. Cleaner. Landscaper. Roofer. The people my clients actually use, vetted by results. Text "VENDOR" to [PHONE] or scan and I'll email the list today. Charles Brewer, Keller Williams. | VA |
| 6 | Jun 1 (Day 151) | Mail task | Your home's value, updated for summer | Prices in [NEIGHBORHOOD] moved [X]% over the last 12 months. That changes your equity, your insurance needs, and your options. Want a written value range with the three sales it's based on? Scan the code. Takes me a day, costs you nothing. Charles Brewer, Keller Williams, [PHONE] | VA, Charles approves the stat |
| 7 | Jul 1 (Day 181) | Mail task | Summer in [MARKET]: my favorites list | Best coffee. Best tacos. Best place to take out-of-town guests. Best hardware store. My list, and I'll defend every pick. See it at [short URL]. Charles Brewer, Keller Williams. Local since [YEAR]. [PHONE] | VA |
| 8 | Aug 1 (Day 212) | Mail task | Thinking about a fall move? The prep window is now | Fall buyers in [MARKET] are fewer but more serious. Listings that launch in [Month] have averaged [X] days on market. If a move is even a maybe this year, a 20-minute planning call now saves weeks later. Scan to book. Charles Brewer, Keller Williams, [PHONE] | VA, Charles approves stat |
| 9 | Sep 1 (Day 243) | Mail task | Just Sold nearby: [ADDRESS], [PRICE], [X]% of list | Another [NEIGHBORHOOD] sale: [ADDRESS] closed at [PRICE], [X]% of asking, in [Y] days. Pricing right the first time is the whole game. Want to know where your home would land? Scan for a range. Charles Brewer, Keller Williams, [PHONE] | VA |
| 10 | Oct 1 (Day 273) | Mail task | Fall and winter home checklist | Furnace service. Gutters again. Hose bibs off. Weatherstripping. Chimney check. Detector batteries. Stick it on the fridge. From Charles Brewer, Keller Williams. Need a name for any of these? Text "VENDOR" to [PHONE]. | VA |
| 11 | Nov 1 (Day 304) | Mail task | Thank you, [NEIGHBORHOOD] | No pitch this month. I've had the privilege of helping [X] [MARKET] families move this year, and several live near you. Thank you for letting me be part of this neighborhood. Happy Thanksgiving. Charles Brewer, Keller Williams, [PHONE] | VA, Charles approves |
| 12 | Dec 1 (Day 334) | Mail task | Year in review: [NEIGHBORHOOD] by the numbers | Homes sold: [X]. Median price: [Y]. Average days on market: [Z]. Highest sale: [ADDRESS] at [PRICE]. What's ahead in 2027: my two-sentence read on the back. Happy holidays from Charles Brewer, Keller Williams, [PHONE]. Want your street's numbers? Scan. | VA, Charles writes the read |

## Notes
- Every card carries: photo of Charles, Keller Williams logo and office per brokerage advertising rules, license number if required by state, [PHONE], a QR code with `utm_source=mail&utm_campaign=12direct-[month]` landing on charlesbrewer.guru so responses flow through Z-01 and get `Src-Website` corrected to the mail source by the VA (SOP-01).
- Response tracking: each card's keyword ("LIST", "VENDOR") and QR campaign tag are logged in the scorecard.
- Fair Housing: the cards talk about houses, prices, repairs, and places. Never about who lives in the neighborhood, schools' quality, or "the kind of people" anywhere.
- Design in Command Designs where a postcard template exists; otherwise Canva with the brand kit.
