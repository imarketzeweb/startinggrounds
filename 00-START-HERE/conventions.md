# Conventions (read this first — every document in this repo uses these)

This file is the single source of truth for names, tags, stages, and tools.
If another document disagrees with this one, this one wins.

## Business facts and assumptions

| Item | Value |
|---|---|
| Agent | Charles Brewer |
| Brand site | charlesbrewer.guru (personal funnel site) |
| Brokerage | Keller Williams (Command is the KW CRM) |
| Team today | Charles (agent / rainmaker) + 1 Virtual Assistant ("VA") |
| Client types | Buyers, Sellers, Investors |
| Service promise | "White glove": every client knows what happens next, before they have to ask |
| Model | The Millionaire Real Estate Agent (MREA) — Gary Keller |
| Content channel now | Social media (Instagram, Facebook, TikTok, LinkedIn, Google Business Profile) |
| Content channel later | YouTube (parked — see 11-YOUTUBE-LATER) |

Assumptions we are working under (change here if wrong):
- Charles is licensed in one primary market; docs say `[MARKET]` where the city/area goes.
- The VA works ~20–40 hrs/week, remote, US business hours overlap, and is the human in every "human review" step below.
- ChatGPT is ChatGPT Plus/Team (custom GPTs + Projects + file uploads available).
- Zapier is the automation glue (Make.com works identically; the specs are tool-agnostic).

## The tool stack (keep it this small)

| Job | Tool | Notes |
|---|---|---|
| CRM, database, pipelines, drips, tasks | **KW Command** | Contacts, SmartPlans, Opportunities, Designs, Campaigns, Sites |
| Thinking, writing, analysis | **ChatGPT** (custom GPTs) | Six GPTs defined in 03-CHATGPT |
| Glue between tools | **Zapier** | Command has a Zapier integration; verify available triggers/actions in your account |
| Website / funnel | **charlesbrewer.guru** | Landing pages + forms → Command |
| Design | **Command Designs** first, **Canva** when Designs can't | Brand kit lives in Canva |
| Short video edit | **CapCut** | Reels / Shorts / TikTok |
| Listing media | Pro photographer w/ drone + **Matterport or Zillow 3D Home** + floor plan | Non-negotiable on every listing |
| Scheduling | **Calendly** (or Command's booking link) | One link for consults, one for showings |
| E-sign / transaction | **DocuSign via Command Opportunities** | |
| VA task board & SOP videos | **Command Tasks** + **Loom** | Trello/Notion are fine if VA prefers |
| Team chat | **Slack or WhatsApp** | One channel: `#leads`, one: `#listings`, one: `#ops` |

## Command contact tags (exact spelling)

Type (exactly one per contact):
- `Buyer` `Seller` `Investor` `Past Client` `Sphere` `Vendor` `Agent-Referral`

Relationship (MREA database rule — exactly one per contact):
- `Met` (they know you) → gets the **33 Touch**
- `Haven't Met` → gets **12 Direct**

Status:
- `New-Lead` `Nurture` `Hot` `Active` `Under-Contract` `Closed` `Dead`

Source (exactly one, set at creation, never changed):
- `Src-Website` `Src-Social` `Src-Referral` `Src-Sphere` `Src-OpenHouse` `Src-Sign` `Src-Paid` `Src-Investor-List` `Src-Event`

Program / plan tags (added by SmartPlans, used for reporting):
- `8x8-Active` `33-Touch` `12-Direct` `Seller-Nurture` `Buyer-Nurture` `Investor-Deal-Alerts` `Past-Client-Program`

Lead temperature (used by the Lead Response GPT and the VA):
- `A` = wants to transact in 0–30 days
- `B` = 30–90 days
- `C` = 90+ days / undecided

## Command Opportunities pipelines (stage names)

Seller pipeline: `Cultivate → Appointment Set → Appointment Met → Listing Signed → Coming Soon → Active → Under Contract → Closed`

Buyer pipeline: `Cultivate → Consult Set → Consult Met → Buyer Agreement Signed → Showing → Offer Written → Under Contract → Closed`

Investor pipeline: `Cultivate → Criteria Call → Deal Alerts On → Analyzing Deal → Offer Written → Under Contract → Closed → Repeat`

## SmartPlan names (exact)

- `SP-8x8 New Contact`
- `SP-33 Touch (Met)`
- `SP-12 Direct (Haven't Met)`
- `SP-Seller Nurture`
- `SP-Seller Listing Launch`
- `SP-Seller Under Contract`
- `SP-Buyer Nurture`
- `SP-Buyer Under Contract`
- `SP-Investor Deal Alerts`
- `SP-Past Client Program`
- `SP-Speed to Lead` (first 10 days for any web/social lead)

## The six ChatGPT GPTs (exact names)

1. `CB Lead Responder` — drafts first-touch replies and qualifies leads (A/B/C)
2. `CB Listing Marketer` — turns a listing intake form into the full marketing kit
3. `CB Seller Concierge` — pre-listing, pricing conversation, weekly seller update drafts
4. `CB Buyer Concierge` — buyer consult prep, showing itineraries, offer strategy notes
5. `CB Investor Analyst` — deal analysis, rental comps, investor updates
6. `CB Ops Manager` — VA SOP writer, weekly scorecard summary, hiring and time blocking

Rule: **ChatGPT drafts, a human approves, Command sends.** Nothing goes to a client without a human (Charles or the VA) reading it.

## Naming conventions for files, folders, and Zaps

- Zap names: `Z-##  Trigger → Outcome` (e.g., `Z-01 Website Form → Command Contact + Speed to Lead`)
- Listing folders (Google Drive): `Listings/[YYYY-MM] [Street Address]/` with subfolders `01-Photos`, `02-Video`, `03-3D-FloorPlan`, `04-Marketing-Kit`, `05-Docs`
- Social posts: `[Address]-[Stage]-[Platform]` (e.g., `123-Main-JustListed-IG`)

## The five listing stages (used for social posts and SmartPlans)

`Coming Soon → Just Listed → Open House → Under Contract → Just Sold`

## Non-negotiable service standards

1. Every new lead gets a human response within **5 minutes** during 8am–8pm, and a first-thing-next-morning response otherwise. Automation sends the instant acknowledgment; a human sends the real reply.
2. Every active seller gets a **written update every Monday** (traffic, feedback, showings, market movement, next step).
3. Every active buyer gets a **showing itinerary the night before** and a **recap the same evening**.
4. Every listing launches with: pro photos, drone, video walkthrough, 3D tour, floor plan, single-property page, 5-stage social sequence, and an email blast to the database.
5. Every closed client enters `SP-Past Client Program` the day of closing.

## Placeholders used across docs

`[MARKET]` `[BROKERAGE OFFICE]` `[PHONE]` `[EMAIL]` `[CALENDLY LINK]` `[ADDRESS]` `[PRICE]` `[BEDS]` `[BATHS]` `[SQFT]` `[NEIGHBORHOOD]` `[VA NAME]`
