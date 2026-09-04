# Lead Generation Model

> MREA principle: *"Prospecting and marketing, aimed at a database, systematically."*
> The engine is the database. Leads that are not in Command, tagged, and on a SmartPlan do not exist.

## 1. The database is the business

Every contact in Command is one of two things (tag exactly one):

| Tag | Who | Program | Expected yield (MREA) |
|---|---|---|---|
| `Met` | Knows Charles by name and would take his call | `SP-33 Touch (Met)` | 2 sides per 12 contacts per year |
| `Haven't Met` | Geographic farm, targeted lists, cold web leads | `SP-12 Direct (Haven't Met)` | 1 side per 50 contacts per year |

Every **new** contact, regardless of source, first goes through `SP-8x8 New Contact` (8 touches in 8 weeks) and then graduates to the right annual program.

Targets from `economic-model.md`: **150 Met on 33 Touch**, **400 Haven't Met on 12 Direct**, growing by **25 new contacts per week**.

## 2. Prospecting vs. marketing

MREA splits lead generation into two lanes. Charles owns prospecting (his voice, his relationships). The VA and automations own marketing (consistent, scheduled, measured).

| Lane | Activities we run | Owner | Where documented |
|---|---|---|---|
| **Prospecting** (you go to them) | Daily database calls/texts, 10 neighbor calls per new listing, open house neighbor invites, past client calls, investor criteria calls, agent-to-agent referral calls | Charles | `05-SELLER-SYSTEM/open-house-system.md`, `04-AUTOMATIONS/command-smartplans` |
| **Marketing** (they come to you) | charlesbrewer.guru funnel, 5-stage listing social sequence, weekly non-listing content, 12 Direct mailers, 33 Touch emails, Google Business Profile, Just Listed/Just Sold, reviews | VA + Zapier + ChatGPT | `08-WEBSITE-FUNNEL`, `05-SELLER-SYSTEM/social-media-listing-templates.md`, `04-AUTOMATIONS` |

## 3. Lead sources we run (and the tag for each)

| # | Source | Tag | How the lead enters Command | SmartPlan on entry | Primary type |
|---|---|---|---|---|---|
| 1 | Sphere / past clients | `Src-Sphere` | Charles adds manually or imports phone contacts | `SP-33 Touch (Met)` | All |
| 2 | Referrals (client, agent, vendor) | `Src-Referral` | Manual add within 1 hour | `SP-Speed to Lead` → 8x8 | All |
| 3 | charlesbrewer.guru forms | `Src-Website` | Z-01 | `SP-Speed to Lead` | By page |
| 4 | Social (DMs, lead ads, comments) | `Src-Social` | Z-03 or VA manual | `SP-Speed to Lead` | Buyer/Seller |
| 5 | Open houses | `Src-OpenHouse` | Z-04 | `SP-8x8 New Contact` | Buyer + neighbors (future sellers) |
| 6 | Yard sign / QR / property page | `Src-Sign` | Z-05 | `SP-Speed to Lead` | Buyer |
| 7 | Investor lists / meetups / BiggerPockets | `Src-Investor-List` | VA import | `SP-Investor Deal Alerts` | Investor |
| 8 | Paid (Google/Meta ads) – later | `Src-Paid` | Z-03 | `SP-Speed to Lead` | Buyer/Seller |
| 9 | Events / community | `Src-Event` | VA import | `SP-8x8 New Contact` | All |

Rule: the **Source tag is set once at creation and never changed**. That is how we know what works.

## 4. Leading with listings

MREA: *"Lead with listings."* One listing produces sign calls, open-house buyers, neighbor conversations, social content for 5 stages, and a Just Sold that markets you to the whole street. That is why the seller system (`05-SELLER-SYSTEM`) is the most detailed part of this repo, and why every listing must be **maximally viewable** (see `listing-launch-playbook.md`).

Seller-specific lead generation, in priority order:

1. **Home-value funnel** on charlesbrewer.guru (Sell page) with monthly "what's your home worth" social posts.
2. **12 Direct farm**: pick one geographic farm of ~400 homes with turnover ≥ 6%/year. Mail monthly. Door-knock or call around every listing and open house in it.
3. **Circle prospecting** around every listing: 10 neighbor calls at Coming Soon, an invite at Open House, a Just Sold call after closing.
4. **Past client & sphere asks**: the 33 Touch includes 8 calls per year; each call ends with "who do you know who is thinking about a move this year?"
5. **Investor sellers**: investors who bought through you will sell or 1031 through you. Quarterly portfolio reviews surface those.

## 5. The touch programs at a glance

Full step-by-step copy for each lives in `04-AUTOMATIONS/command-smartplans/`.

| Program | Who | Cadence | Mix |
|---|---|---|---|
| **8x8** | Every new contact | 8 touches, 8 weeks | Intro text + email, item of value, market snapshot, call, personal video, handwritten note, call, "what's next" email |
| **33 Touch** | `Met` | 33 per year | ~18 emails/mailers, 8 calls/texts, 3 items of value, 2 personal notes, 2 holiday cards, birthday + home anniversary |
| **12 Direct** | `Haven't Met` | 12 mailers per year | Just Listed/Sold, market stats, home-value offer, seasonal home tips, community events |
| **Speed to Lead** | Web/social/sign leads | 10 days | Instant ack + human call in 5 min, then day 1, 2, 3, 5, 7, 10 |
| **Past Client Program** | Closed clients | Ongoing | Closing gift, 7-day review ask, 30/90-day check-in, annual home anniversary, then 33 Touch |

## 6. Weekly lead generation scorecard (feeds `10-SCORECARD`)

| Metric | Target | Source of truth |
|---|---|---|
| New contacts added to Command | 25 | Command contact count by created date |
| Database conversations (calls/texts logged) | 50 | Command activity log |
| Handwritten notes sent | 15 | VA tally |
| Web leads (Src-Website) | 5 | Command tag count |
| Social leads (Src-Social) | 5 | Command tag count |
| Open house sign-ins | 10 per open house | Command Open House app |
| Appointments set | 2 | Command Opportunities moved to "Appointment Set" / "Consult Set" |
| Speed-to-lead median response time | < 5 min (8am–8pm) | Command activity timestamps |
| 33 Touch / 12 Direct steps completed on time | 100% | Command SmartPlan task completion |
