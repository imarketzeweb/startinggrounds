# 08 Website Funnel: Map

Read `/00-START-HERE/conventions.md` first. Every tag, SmartPlan, Zap name, and GPT name in this folder comes from that file.

## What charlesbrewer.guru is for

charlesbrewer.guru is the top of the funnel. Every piece of social content, every sign, every flyer, every Google Business Profile link, and every email signature points there. Its only job is to turn a visitor into a contact in Command with the right tags, so `SP-Speed to Lead` and a human can take over within 5 minutes.

The site is not the CRM, not the IDX search of record, and not a brochure. If a page does not move a visitor toward a form, a call, or a booking, it does not belong on the site.

Investor model note: Charles sources fix and flip deals, capital partners fund them (buy the deal outright, joint venture, or private lender), Charles project-manages the rehab and lists the finished flip. The Invest page recruits capital partners; it is not a deal-alert list. Terms are set by attorney-drafted agreements and the site never promises a return.

Three entry paths, one destination:

| Visitor | Entry path | Lead magnet | Lands in Command as |
|---|---|---|---|
| Seller | Sell page: "What's my home worth" + Pre-Listing Checklist | Instant home value, `[MARKET] Home Seller's Guide`, Pre-Listing Checklist | `Seller` + `Src-Website` + `New-Lead` + `Haven't Met` + `SP-Speed to Lead` |
| Buyer | Buy page: Buyer's Guide + consult booking | `[MARKET] Home Buyer's Guide`, First-Time Buyer Roadmap, consult booking | `Buyer` + `Src-Website` + `New-Lead` + `Haven't Met` + `SP-Speed to Lead` |
| Capital partner (Investor) | Invest page: Capital Partner program application | Sample Deal Memo (anonymized closed flip) + "How the Capital Partner Program works" one-pager | `Investor` + `Src-Website` + `New-Lead` + `Haven't Met` + `SP-Speed to Lead` |

Platform note: the site platform is not specified. Every instruction in this folder is written for any site builder whose forms can post to Zapier (native integration) or to a webhook URL. If the platform cannot do that, replace its forms with an embedded form tool that can (Typeform, Tally, Jotform, Google Forms via Zapier, or Command's own lead capture forms on a KW Site).

## Who does what

| Role | Owns | Never does |
|---|---|---|
| Charles | Approves all copy, records the About video, appears in every hero photo, responds to leads within 5 minutes when available, writes or approves the monthly blog piece | Building pages, testing forms, configuring Zaps |
| VA ([VA NAME]) | Page builds and edits, form and Zap testing every Monday, single-property page for every listing, UTM links for every post, QR codes, Google Business Profile posts and links, monthly conversion checklist audit, lead magnet PDF production in Canva | Publishing copy Charles has not approved |
| Zapier | `Z-01 Website Form → Command Contact + Speed to Lead`, `Z-02 Calendly Consult Booked → Command Stage + Slack`, `Z-03 Home Value Request → Command Contact + Seller Alert`, `Z-04 Capital Partner Form → Command Contact + Investor Alert` | Client communication |
| Command | Contact of record, tags, `SP-Speed to Lead`, lead routing tasks | Hosting the site (unless the KW Site is chosen as the platform) |
| ChatGPT (`CB Listing Marketer`, `CB Seller Concierge`, `CB Buyer Concierge`, `CB Investor Analyst`, `CB Ops Manager`) | Drafts of page copy, lead magnet content, blog posts, single-property page copy | Publishing. Rule: ChatGPT drafts, a human approves, then the VA publishes. |

## Files in this folder

| File | Use it when |
|---|---|
| `charlesbrewer-guru-funnel.md` | You are building or auditing the site. Funnel architecture, page list, per-page goal and form spec, post-submit automation, social-to-site traffic plan, UTM naming, QR codes, conversion checklist. |
| `landing-page-copy.md` | You need the words. Full copy for the Home hero, Sell, Buy, and Invest pages with headlines, subheads, bullets, CTAs, and form labels. |
| `lead-magnets.md` | You are producing a lead magnet. Outlines, page counts, Canva design notes, and the ChatGPT prompt for each guide, checklist, the Sample Deal Memo, the Capital Partner one-pager, and the home value tool recommendation. |

## The weekly site rhythm

| Day | Charles | VA |
|---|---|---|
| Monday | | Submit a test lead through every form; confirm it lands in Command with the right tags and that `#leads` fires. Fix or escalate anything broken before 10am. |
| Tuesday | | Publish the week's social posts with UTM links back to the site. |
| Wednesday | Approve the monthly blog post (first Wednesday of the month) | Post a Google Business Profile update linking to a site page. |
| Friday | Record one 60-second video for a page or post if scheduled | Report site leads by path (Sell / Buy / Invest) and source in the weekly scorecard. |
| Monthly | Review the conversion checklist audit and pick one improvement | Run the conversion checklist; refresh reviews on the site; verify every single-property page is current (sold listings show "Just Sold"). |

## Numbers Charles watches

| Metric | Source | Target |
|---|---|---|
| Site visits by page | Site analytics | tracked |
| Form submissions by path | Command contacts with `Src-Website`, by type tag | grow monthly |
| Visit to lead conversion | Submissions / visits on landing pages | 3% or better on Sell and Invest, 2% on Buy |
| Lead to human reply under 5 minutes | Command timeline versus contact created time | 100% during 8am to 8pm |
| Consult bookings from site | Calendly bookings with `utm_source` set | tracked |
| Social clicks to site | UTM reports | grow monthly |
