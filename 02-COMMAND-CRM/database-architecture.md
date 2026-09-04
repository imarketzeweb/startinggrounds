# Database Architecture in Command

## 1. One contact record, five facts

Every contact must have these five facts set. The VA's `SOP-02` audits this weekly.

| Fact | Where in Command | Allowed values | Set by |
|---|---|---|---|
| **Type** | Tag | `Buyer` `Seller` `Investor` `Past Client` `Sphere` `Vendor` `Agent-Referral` | Zap or VA at creation; Charles may change after a conversation |
| **Relationship** | Tag | `Met` or `Haven't Met` | Charles decides (default `Haven't Met` for web/social leads until a real conversation happens) |
| **Status** | Tag | `New-Lead` `Nurture` `Hot` `Active` `Under-Contract` `Closed` `Dead` | Zap on entry (`New-Lead`), then Charles/VA as it progresses |
| **Source** | Tag + Command's Lead Source field | `Src-Website` `Src-Social` `Src-Referral` `Src-Sphere` `Src-OpenHouse` `Src-Sign` `Src-Paid` `Src-Investor-List` `Src-Event` | Set once at creation, never changed |
| **Temperature** | Tag | `A` (0–30 days) `B` (30–90 days) `C` (90+ / unsure) | Charles after first conversation; `CB Lead Responder` suggests |

Program tags are added and removed by SmartPlans and reported on: `8x8-Active` `33-Touch` `12-Direct` `Seller-Nurture` `Buyer-Nurture` `Investor-Deal-Alerts` `Past-Client-Program`.

## 2. Custom fields to add (verify field types in Command)

| Field | Type | Used by |
|---|---|---|
| Home Anniversary (closing date) | Date | `SP-Past Client Program` anniversary touch |
| Birthday | Date | 33 Touch |
| Property Address (current home) | Text | Seller nurture, home-value updates, 12 Direct |
| Preferred Contact Method | Pick list: Text / Call / Email | Lead Responder drafts, VA |
| Investor Strategy | Pick list: Buy-and-hold / BRRRR / Flip / STR / Multifamily | Investor deal alerts |
| Buy Box Summary | Text (one line: price, areas, type, min CoC) | Investor deal alerts |
| Referral Partner | Text (who referred them) | Referral thank-yous |
| Last Personal Touch | Date | Database hygiene report |

## 3. Met vs. Haven't Met, decided by one question

*"If I called this person right now, would they know who I am and take the call?"* Yes = `Met`. Anything else = `Haven't Met`.

Movement rule: a `Haven't Met` contact becomes `Met` the day Charles has a real two-way conversation (call, meeting, open house chat). The VA swaps the tag and swaps the SmartPlan (`SP-12 Direct` off, `SP-33 Touch` on) within 24 hours. Every new contact runs `SP-8x8 New Contact` first regardless.

## 4. Saved filters (smart views) to create

| Filter name | Criteria | Who uses it |
|---|---|---|
| `Today: New Leads` | Status `New-Lead`, created last 3 days | Charles (lead gen block), VA |
| `Today: Calls Due` | SmartPlan call tasks due today | Charles |
| `Hot A` | Temperature `A`, Status not `Closed`/`Dead` | Charles |
| `Sellers Nurturing` | Type `Seller`, Status `Nurture` | Charles monthly review |
| `Active Sellers` | Type `Seller`, Status `Active` | VA (Monday reports) |
| `Under Contract` | Status `Under-Contract` | VA (milestones) |
| `Investors – Alerts On` | Tag `Investor-Deal-Alerts` | VA (biweekly alert send) |
| `Met – 33 Touch` | Tag `Met` and `33-Touch` | Reporting |
| `Haven't Met – 12 Direct` | Tag `Haven't Met` and `12-Direct` | Mailer export |
| `Hygiene: Missing Facts` | Missing any of the five facts | VA weekly |
| `Hygiene: No Touch 90 Days` | Last activity > 90 days, Status not `Dead` | VA weekly, Charles calls |
| `Past Clients` | Tag `Past Client` | Anniversary, reviews, referrals |

## 5. Lead entry rules

1. **Every** lead enters Command within 5 minutes (automated) or 1 hour (manual) of first contact.
2. Instant enrollment in `SP-Speed to Lead` (web/social/sign) or `SP-8x8 New Contact` (open house, event, referral).
3. A Command Opportunity is created in `Cultivate` for any lead with a stated intent to buy, sell, or invest. Sphere contacts do not get an Opportunity until intent exists.
4. Duplicates: search by phone and email before creating. Zapier "Find or Create" where supported; otherwise the VA dedupes daily.
5. Notes: first note is always the raw lead message plus the `CB Lead Responder` summary line.

## 6. Import and cleanup (one-time, week 1)

1. Export phone contacts, email contacts, past closings (from brokerage), and any spreadsheet lists.
2. Merge in Google Sheets: columns First, Last, Phone, Email, Address, Type, Met/Haven't Met, Source, Notes.
3. `CB Ops Manager` prompt: "Here is my contact list. Flag likely duplicates, standardize phone/email formats, and suggest Type and Met/Haven't Met for each based on the notes." Charles confirms the Met/Haven't Met column personally; nobody else knows.
4. Import to Command with tags. Verify the count.
5. Enroll: all `Met` → `SP-33 Touch (Met)`; all `Haven't Met` with a mailing address → `SP-12 Direct (Haven't Met)`; anyone added in the last 60 days → `SP-8x8 New Contact` first.
6. Send a one-time "I've reorganized my business" reconnect text to the whole Met list (copy in `04-AUTOMATIONS/command-smartplans/SP-33-Touch-Met.md`, touch 1).

## 7. Hygiene standards (VA, weekly, `SOP-02`)

- Zero contacts in `Hygiene: Missing Facts` by Friday.
- Zero duplicates.
- Every `Active` and `Under-Contract` contact has an Opportunity in the right stage.
- `Dead` contacts are removed from all SmartPlans except `SP-12 Direct` if they have a mailing address (MREA: nobody is dead, they are just not ready).
- Growth: +25 contacts per week (scorecard metric).
