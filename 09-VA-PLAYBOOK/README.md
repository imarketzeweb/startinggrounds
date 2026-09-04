# 09 VA Playbook: Map

Read `/00-START-HERE/conventions.md` first. Every tag, stage, SmartPlan, GPT name, and Zap name in this folder comes from that file. Investor-side changes (capital partner model, `Capital-Partner` tag, `SP-Capital Partner Program`, Deal Board) are described in `/04-AUTOMATIONS/README.md`.

## Mission

[VA NAME] runs the systems so Charles can spend his time on the four things only he can do: lead conversations, listing consultations, negotiations, and client relationships. The VA's job is that every lead is logged and answered, every listing launches the same way, every client hears from us before they have to ask, and every number is on the scorecard by Friday. When the VA is doing the job well, Charles never opens a spreadsheet, never chases a vendor, and never wonders whether a lead fell through the cracks.

The rule that governs everything: **ChatGPT drafts, a human approves, Command sends.** The VA is the human on most drafts. Charles is the human on anything involving price, negotiation, legal terms, bad news, or a capital partner's money.

## Responsibilities by MREA leverage area

### 1. Lead coordination
- Watch `#leads` and the Command inbox all day; the 5-minute standard (8am to 8pm) applies to the VA whenever Charles is unavailable.
- Process every new lead per `SOP-01`: verify Command record, tags, `SP-Speed to Lead`, Opportunity, run or review `CB Lead Responder` drafts, send approved replies from Command, log the human response in the Slack thread.
- Route leads at Speed to Lead exit: `Hot`, `Nurture`, or `Dead`; start the right nurture plan.
- Book consults and listing appointments on Charles's calendar; send confirmations and pre-appointment packets.

### 2. Listing coordination
- Complete the Seller Intake Form with the seller after the listing is signed; submit it (this fires Z-06).
- Book photographer, drone, video, 3D tour, floor plan; set up the Drive folder; keep the `Active Listings` sheet current.
- Run `CB Listing Marketer`, QA the kit against the Fair Housing checklist, hand MLS input to Charles for review, check syndication, order sign and QR rider, build the single-property page. `SOP-03`.
- Monday seller reports: pull numbers by 10am, draft via `CB Seller Concierge`, get approval, send by 3pm. `SOP-05`.
- Open house logistics and same-day follow-up. `SOP-06`.

### 3. Transaction coordination
- Milestone tracker for every contract; adjust SmartPlan step dates to the actual contract deadlines; schedule inspectors, appraiser access, walk-throughs; send logistics messages; keep title, lender, and the other agent's coordinator informed. `SOP-07`.
- Closing day: confirm recording, move the Opportunity to Closed, closing gift, review request, Past Client Program. `SOP-08`.
- Capital partner deals: keep the Deal Board current at every stage; gather Friday project update inputs; prepare distribution statement inputs for Charles and the accountant.

### 4. Marketing
- Daily social posting from Command Designs / Canva templates; scheduling; UTM links; story sequences; comment and DM replies within 1 hour; log every DM lead. `SOP-04`.
- Monthly market report assembly, video captioning in CapCut, testimonial cards from reviews (Z-11 output).
- Website: keep single-property pages and the testimonials section current.

### 5. Database
- Command hygiene: exactly one type tag, one relationship tag, one source tag per contact; dedupe; SmartPlan membership. `SOP-02`.
- Execute the monthly 33 Touch and 12 Direct tasks: emails filled with current numbers, mailer ordering with the mailing house, personal-note prompts for Charles. `SOP-09`.
- Weekly scorecard by Friday 3pm. `SOP-10`.

## What the VA never does

- Gives an opinion on price, value, or offer terms to anyone. "Charles will call you about that" is the complete answer.
- Negotiates anything: repairs, credits, deadlines, commission, partner splits.
- Interprets a contract, disclosure, or legal document, or tells a client what a contract term means.
- Delivers bad news to a client (low appraisal, failed inspection, buyer walked, deal fell through). That is a phone call from Charles.
- Sends anything to a client, partner, or the public that Charles has not approved, unless the SOP for that message type explicitly says "VA approves."
- Quotes returns, guarantees, or projections to a capital partner.
- Performs any activity that requires a real estate license in Charles's state. What counts varies by state and brokerage (showing property, discussing terms, hosting an open house alone, soliciting listings). **Verify the list with the brokerage's compliance contact before the VA's first week and record it at the bottom of this file.**
- Shares client data outside the tool stack, or pastes client financial or identifying details into ChatGPT beyond what the GPT instructions allow.

## Tools and access

| Tool | Access level | Used for |
|---|---|---|
| KW Command | Team member seat (contacts, SmartPlans, Opportunities, Tasks, Designs, Campaigns) | Everything CRM |
| ChatGPT (Team workspace) | Shared custom GPTs: `CB Lead Responder`, `CB Listing Marketer`, `CB Seller Concierge`, `CB Buyer Concierge`, `CB Investor Analyst`, `CB Ops Manager` | Drafting |
| Zapier | Viewer (to read errors and re-run failed Zaps); Charles owns the account | Monitoring Z-01 to Z-16 |
| Slack | `#leads`, `#listings`, `#ops` | All approvals and alerts |
| Google Workspace | Drive `Listings/`, `Deals/`, `Investor/`; Sheets: `Lead Log`, `Active Listings`, `Active Buyers`, `Deal Board`, `Capital Partners`, `KPI Scorecard`, `Testimonials`, `Open House Schedule`, `Do Not Text` | Files and data |
| Social scheduler (Buffer / Later / Metricool) | Editor | Posting |
| Canva | Brand kit editor | Design when Command Designs can't |
| CapCut | Own account, brand assets shared | Short video |
| Calendly | Admin on Charles's booking pages | Consults and showings |
| Google Voice / phone system | Shared inbox view | Missed calls, texts |
| Mailing house portal | Order access, Charles approves invoices | 12 Direct and 33 Touch mailers |
| Loom | Own account | Recording SOP videos |
| Password manager | Shared vault, no personal Charles logins | Access |

## Communication rhythm

**Daily huddle, 8:15am, 15 minutes (Slack huddle or call).** Agenda: (1) leads since yesterday 5pm and their status, (2) today's client-facing sends waiting on Charles, (3) listings and contracts: anything due today, (4) Charles's calendar: what the VA needs to protect or prep, (5) one blocker.

**EOD report, 4:30pm, posted in `#ops`.** Format in `daily-weekly-checklists.md`. Under 10 lines. Charles reads it, replies only if something needs a decision.

**Weekly 1:1, Friday 2:00pm, 30 minutes.** Agenda: (1) scorecard first look (VA has the numbers in by 3pm; the 1:1 reviews what is trending), (2) what broke this week and which SOP or Zap fixes it, (3) next week's listings, closings, open houses, deals, (4) one SOP to improve or record on Loom, (5) VA's hours and workload check.

**Monthly, first Friday, 60 minutes.** Database numbers, 33 Touch and 12 Direct execution, review count, marketing calendar for the month, and one process to automate next.

## KPIs the VA owns

| KPI | Standard | Where it lives |
|---|---|---|
| Leads logged in Command within 15 minutes of arrival | 100% | Lead Log vs. Command |
| Human response within 5 minutes (8am to 8pm) when Charles is unavailable | 95%+ | Lead Log `Human Response At` |
| Monday seller reports sent by 3pm | 100% | Seller Report Log |
| Friday partner project updates sent by 3pm | 100% | Project Update Log |
| Listing launch checklist complete before go-live | 100%, zero QA misses | Active Listings sheet |
| Social posts published per plan | 5 per week minimum plus every listing stage post | Scheduler |
| DMs and comments answered within 1 hour (business hours) | 90%+ | Scheduler inbox log |
| Database hygiene: contacts with exactly one type, one relationship, one source tag | 98%+ | Monthly Command audit |
| 33 Touch and 12 Direct tasks completed on schedule | 100% | Command task completion |
| Scorecard complete by Friday 3pm | 100% | KPI Scorecard `Status` |
| Review requests sent Day 7 after every closing | 100% | Past Client checklist |

## Files in this folder

| File | Use it when |
|---|---|
| `daily-weekly-checklists.md` | Every day. Time-blocked daily checklist, weekly by day, monthly, and the EOD report template. |
| `sops/SOP-01-new-lead-processing.md` | A lead arrives. |
| `sops/SOP-02-command-contact-hygiene.md` | Tagging, dedupe, Met vs. Haven't Met, SmartPlan membership. |
| `sops/SOP-03-listing-launch-coordination.md` | A listing is signed. |
| `sops/SOP-04-social-posting.md` | Building, scheduling, and replying on social. |
| `sops/SOP-05-weekly-seller-report.md` | Monday. |
| `sops/SOP-06-open-house-followup.md` | An open house is scheduled or just happened. |
| `sops/SOP-07-under-contract-coordination.md` | An offer is accepted. |
| `sops/SOP-08-closing-and-past-client.md` | A closing is this week. |
| `sops/SOP-09-database-touches.md` | The 1st of the month. |
| `sops/SOP-10-weekly-scorecard.md` | Friday by 3pm. |

## Brokerage compliance notes (fill in before week one)

- Compliance contact at [BROKERAGE OFFICE]: [name, phone]
- Activities the VA may not perform in this state: [list from brokerage]
- Advertising rules for social and mailers (logo, office, license number placement): [summary]
- Team name and disclosure rules for the VA signing emails and texts: [summary]
