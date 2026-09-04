# SOP-02  Command Contact Hygiene

## Purpose
The database is the business. MREA's 33 Touch and 12 Direct only work if every contact has exactly one type tag, one relationship tag (`Met` / `Haven't Met`), one source tag, a current status, and is in the right SmartPlan. This SOP keeps that true every day and audits it every month.

## Trigger
- Daily 1:00pm hygiene block (yesterday's new and edited contacts).
- Any time a contact is created manually, imported, or changes relationship (a Haven't Met becomes Met after a real conversation or meeting).
- Monthly audit on the first three business days.
- A CSV import (event list, purchased list, old database).

## Steps
1. **Daily: pull yesterday's contacts.** In Command, filter contacts created or modified yesterday. For each:
   - Type: exactly one of `Buyer`, `Seller`, `Investor`, `Past Client`, `Sphere`, `Vendor`, `Agent-Referral`. A past client who is now buying again keeps `Past Client` and gets a Buyer Opportunity; the Opportunity, not a second tag, tracks the transaction. Capital partners: type `Investor` plus program tag `Capital-Partner`.
   - Relationship: exactly one of `Met`, `Haven't Met`. Rule: `Met` means they would recognize Charles's name and take his call. Web and social leads start `Haven't Met` and flip to `Met` after a real two-way conversation (phone or in person; a text exchange counts if it was a real conversation, note it).
   - Source: exactly one `Src-*`, set at creation, never changed after the first day. Fix only same-day mistakes (e.g. mailer QR lead tagged `Src-Website`).
   - Status: exactly one of `New-Lead`, `Nurture`, `Hot`, `Active`, `Under-Contract`, `Closed`, `Dead`.
   - Temperature `A`/`B`/`C` on any lead not yet Active.
2. **Fields.** Mobile phone in E.164, email lowercase, address for anyone Met, birthday and home anniversary when known, spouse or partner name linked as a related contact (Command supports relationships; if not, note it).
3. **Dedupe.** Search by phone, then email, then last name + street. Merge in Command (keep the older record's ID, the newer record's contact details, all notes, all tags after re-applying the one-of-each rule). Log merges in the monthly audit sheet.
4. **SmartPlan membership.** Every `Met` contact not in a transaction plan must be in `SP-33 Touch (Met)` (or `SP-8x8 New Contact` if less than 8 weeks old, or `SP-Past Client Program` if closed less than a year ago). Every `Haven't Met` must be in `SP-12 Direct (Haven't Met)` or `SP-Speed to Lead` or a nurture plan. No contact is in two nurture plans at once. Program tags (`33-Touch`, `12-Direct`, `8x8-Active`, `Seller-Nurture`, `Buyer-Nurture`, `Capital-Partner-Program`, `Past-Client-Program`) must match the plans actually running.
5. **Relationship change.** When a Haven't Met becomes Met: remove `Haven't Met`, add `Met`, remove from `SP-12 Direct (Haven't Met)`, start `SP-8x8 New Contact`, note the date and how you met. When a contact dies, moves away, or asks to stop: `Dead`, remove from all plans, note why; never delete.
6. **Imports.** Clean the CSV first (split names, format phones, one row per person). Add columns for the four tags. Import in Command; if the importer does not accept tags, import then bulk-tag by the import date filter. New imports are `Haven't Met` + `Src-*` matching the list origin (`Src-Event`, `Src-Investor-List`, `Src-Sphere`) + `Nurture`, and go to `SP-12 Direct (Haven't Met)` unless Charles marks specific names as `Met`.
7. **Monthly audit.** Export all contacts. In Sheets, count contacts with 0 or 2+ type tags, relationship tags, source tags; list them; fix in Command. Run Command's duplicate finder. Record the % clean in the scorecard (target 98%+). Report in the first-Friday monthly meeting with the count of Met, Haven't Met, Past Client, Capital-Partner.
8. **Do Not Text.** Anyone who replies STOP, any vendor, any agent on the other side, any family member: add to the `Do Not Text` sheet so Z-13 skips them.

## Done-when
- Every contact touched yesterday passes the one-of-each rule and is in the right SmartPlan.
- No unmerged duplicates among yesterday's contacts.
- Monthly audit % recorded on the scorecard.

## Time
- 30 minutes daily; 3 hours for the monthly audit; 2 hours per 500-row import.

## Tools
- KW Command (contacts, tags, SmartPlans, duplicate finder, import), Google Sheets, `Do Not Text` sheet.

## Escalate-if
- You are unsure whether a contact is Met: ask Charles in `#ops` with the name; do not guess.
- A merge would combine two different people with the same name and phone (family members): ask.
- An import list's source is unclear or may not have consent for texting: ask Charles before importing or texting.
- Command's tag or SmartPlan limits block the rule (e.g. plan capacity): tell Charles; do not work around it by removing tags.
