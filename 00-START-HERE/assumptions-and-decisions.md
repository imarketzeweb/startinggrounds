# Assumptions and Decisions to Confirm

This system was built from a short brief. Everything below is an assumption Charles should confirm or change. Change the value here, then update `conventions.md`; every other file follows those two.

## Assumptions made

| # | Assumption | Why it matters | If wrong |
|---|---|---|---|
| 1 | Brokerage is Keller Williams (because Command is KW's CRM) | Command features, cap structure, KW Designs, Kelle | Replace Command-specific steps with your CRM's equivalents; the model does not change |
| 2 | One primary market, written as `[MARKET]` | Copy, farm selection, lead magnets | Duplicate the funnel pages per market |
| 3 | Solo agent plus one VA at ~20–40 hrs/week | Time blocking, VA checklists, hiring path | Adjust `09-VA-PLAYBOOK/daily-weekly-checklists.md` |
| 4 | ChatGPT Plus or Team (custom GPTs, Projects, file uploads) | The six GPTs | On free tier, use the Project instructions as a pasted prompt instead |
| 5 | Zapier is the glue; Command's Zapier integration exposes at least "create contact" and "new contact" | Z-01..Z-14 | Each zap spec has a fallback (email parser, CSV import, VA manual step) |
| 6 | charlesbrewer.guru can host forms or embed a form tool that posts to Zapier | The funnel | Use a form tool (Typeform, Jotform, Google Forms) embedded or linked |
| 7 | Local MLS allows a Coming Soon status | Launch timeline | Drop the Coming Soon stage and run those touches at Just Listed |
| 8 | Drone photography is legal at the listing locations | Exposure standard | Skip drone; keep everything else |
| 9 | Example economic numbers ($250k net, $400k average price, 2.5% per side, 35% expenses) are placeholders | Every target in the scorecard | Run the calculator; every target rescales |
| 10 | VA's unlicensed-activity limits follow typical US state rules | VA charter | Confirm with [BROKERAGE OFFICE] and adjust `09-VA-PLAYBOOK/README.md` |

## Decisions for Charles (fill in)

| Decision | Options | Your choice |
|---|---|---|
| Net income goal for the next 12 months | $ | |
| Seller / buyer / investor mix target | e.g. 55 / 45 with 20% investors | |
| Geographic farm for 12 Direct (≈400 homes, turnover ≥ 6%) | Neighborhood name | |
| Social platforms in priority order | IG, FB, TikTok, LinkedIn, GBP, Nextdoor | |
| Scheduling tool | Buffer / Later / Metricool | |
| Photographer + 3D vendor | Name | |
| Booking tool | Calendly / Command | |
| Team chat | Slack / WhatsApp | |
| Who approves lead replies when Charles is in appointments | VA sends approved templates / VA waits | |
| Closing gift standard | e.g. $75–150 local gift + handwritten card | |
| Brand voice words (3–5) | e.g. calm, direct, generous, local | |
| Colors and fonts for Canva | | |

## Things this repo does not do

- It does not give legal, tax, or Fair Housing legal advice. Every client-facing template is written to be Fair Housing safe, but Charles and the brokerage are responsible for compliance in [MARKET].
- It does not connect to Command's API directly. Everything runs through Command's own features, Zapier, or the VA.
- It does not replace human judgment on pricing, offers, and negotiation. Those are Charles's, by design.
