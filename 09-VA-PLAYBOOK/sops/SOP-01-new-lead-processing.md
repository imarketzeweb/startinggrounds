# SOP-01  New Lead Processing

## Purpose
Every new lead, from any source, is in Command with the right tags, the right SmartPlan, and an Opportunity, and has a human response within 5 minutes (8am to 8pm) or first thing the next morning. This SOP is the human half of the 5-minute standard; Zapier (Z-01, Z-03, Z-04, Z-05, Z-13) does the mechanical half.

## Trigger
- A new alert in Slack `#leads` (`NEW ... LEAD`, `SIGN LEAD`, `OPEN HOUSE SIGN-IN`, `MISSED CALL`), or
- A lead that arrived by any other route: a text to Charles, an email, a DM, a phone call, a referral mentioned in conversation, a business card.

## Steps
1. **Claim the lead.** Reply in the `#leads` thread with "on it" if Charles has not already replied. If Charles replies "mine", stop at step 6 and do only steps 7 to 10.
2. **Read the Z-02 drafts** in the thread (SMS, email, call opener, three questions). If Z-02 failed or the lead came outside Zapier, open `CB Lead Responder`, paste the lead details in the format `Name / Phone / Email / Source / Page or property / Timeline / Message`, and post the output in the thread.
3. **Respond within 5 minutes.** Order of preference: call, then text, then email. Use the call opener and the three questions. If no answer, send the SMS draft (edit for anything wrong), then the email draft. A leads (0 to 30 days): Charles calls if he is free; text him "A LEAD, calling now unless you want it" and wait 60 seconds before you call.
4. **Log the human response** in the thread with one word first: "called", "texted", or "replied", then one line of outcome. Z-14 reads this word; without it the escalation fires. Also fill `Human Response At` in `Lead Log`.
5. **Fix Command.** Open the contact. Confirm: exactly one type tag (`Buyer`, `Seller`, `Investor`, `Sphere`), exactly one relationship tag (`Haven't Met` for web/social/sign, `Met` for open house/referral/sphere), exactly one `Src-*` tag (correct it if a mailer QR lead came through as `Src-Website`: the campaign UTM tells you), status `New-Lead`, temperature `A`/`B`/`C` from the GPT output (adjust from your call). Contact created by Z-13 as "Unknown 1234": replace with the real name and source.
6. **SmartPlan and Opportunity.** Confirm `SP-Speed to Lead` is running (web, social, sign, paid) or `SP-8x8 New Contact` (open house, referral, sphere, event). If Zapier could not add it, add it now. Confirm an Opportunity exists at `Cultivate` on the right pipeline (Seller, Buyer, or Investor for capital partner prospects); create it if missing, named `[Last Name] - [Type] - [Address or Range]`.
7. **Note the conversation** in Command: what they want, timeline, next step, and the temperature reason.
8. **Book the next step.** A or B leads: offer a consult or listing appointment; send the Calendly link; when booked, move the Opportunity to `Appointment Set` / `Consult Set` / `Criteria Call` and note the date. C leads: tell them what they will receive and when.
9. **Manual entry route.** If the lead came outside Zapier, create the contact in Command by hand (or send to Command's "add contact via email" address if enabled), then add a `Lead Log` row so the scorecard counts it, then post a `#leads` alert in the shared format so Z-02 and Z-14 run.
10. **Day 10 exit.** When `SP-Speed to Lead` creates the exit task: set `Hot` (appointment set or clearly imminent), `Nurture` (real but not ready; start `SP-Seller Nurture` / `SP-Buyer Nurture`; capital partner prospects with a Criteria Call done go to `SP-Capital Partner Program`), or `Dead` (wrong number, not a lead, asked to stop; note why). Haven't Met contacts going to Nurture also enter `SP-12 Direct (Haven't Met)`.

## Done-when
- Human response logged in the thread and Lead Log within 5 minutes (business hours) or by 8:15am (after hours).
- Contact has one type, one relationship, one source, one status, one temperature tag.
- Correct SmartPlan running; Opportunity at Cultivate or beyond; conversation note saved.
- Next step booked or the nurture path set.

## Time
- 8 to 12 minutes per lead when Zapier and Z-02 worked; 20 minutes for a fully manual lead.

## Tools
- Slack `#leads`, KW Command, `CB Lead Responder`, `Lead Log` sheet, Calendly, phone.

## Escalate-if
- Lead asks for a price opinion, a home value, offer advice, or anything about commission: "Charles will call you about that today," then tell Charles immediately.
- Lead is angry, mentions a complaint, an attorney, or another agent's contract.
- Lead is a capital partner prospect who wants to talk numbers: book the Criteria Call with Charles; do not discuss returns.
- Lead is a client already under contract (tag `Under-Contract`): Charles handles it.
- You cannot reach a human response within 5 minutes for any A lead: text Charles directly, not just Slack.
