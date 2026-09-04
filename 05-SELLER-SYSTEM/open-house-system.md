# Open House System (Mega Open House)

An open house is a lead event that happens to sell the listing. Run it like an event: promote for 7 days, invite the neighbors three ways, capture every visitor, follow up the same day.

Every mega open house produces three things: showings for the seller, sign-ins tagged `Src-OpenHouse` in Command, and neighbors who now know Charles.

Owners: Charles hosts and makes the calls. The VA runs promotion, materials, sign-in processing, and follow-up scheduling.

## 1. When to hold one

- First weekend after every launch (Day +5 to +7). Both days if the market supports it.
- After any price change.
- Day 30 relaunch.
- Time: Saturday or Sunday, 2 hours, 12pm to 2pm or 1pm to 3pm. Broker open on a weekday 11am to 1pm in the first week.

Seller prep (Charles tells the seller at the launch welcome call): they leave with pets, valuables and medications put away, all lights on, blinds open, temperature set, no cooking that morning.

## 2. 7-day promotion timeline

| Day | Task | Owner | Done when |
|---|---|---|---|
| OH -7 | Open house date and time in MLS and on the property page. FB event created. Dates added to `SP-Seller Listing Launch` email | VA | Live in MLS |
| OH -6 | Neighbor list built: 50 closest addresses from the county record or MLS tax export. Phone numbers appended where available and compliant | VA | List in `05-Docs/OH-Neighbors.csv` |
| OH -5 | Door hangers or mailers printed (Canva `OpenHouse-DoorHanger-Print`), 50 pieces, QR to property page | VA orders | In hand by OH -3 |
| OH -4 | Static invite post on IG, FB, LinkedIn (if used), GBP post, Nextdoor post from Charles's profile. Open house email to database (Buyer-tagged and local Sphere) | VA | Posted, email sent from Command |
| OH -3 | Door knock and hang: Charles walks the 50 neighbors, 60 to 90 minutes. Script in section 3. Non-answers get the hanger | Charles | 50 doors done, conversations logged |
| OH -3 | Story poll (which room first?) | VA | Posted |
| OH -2 | Neighbor calls: the 10 closest plus anyone who was interested at the door. Agent-to-agent reminder email with the open house | Charles, VA | Calls logged in Command |
| OH -2 | Q&A story with Charles | VA posts, Charles records | Posted |
| OH -1 | Countdown story, "what to see tomorrow" Reel. Directional signs staged in the car (check local sign ordinances). Sign-in method tested. Materials packed (section 5) | VA | Checklist complete |
| OH -1 | Reminder text to everyone who RSVP'd or asked a question, and to any active buyer clients whose search matches | Charles | Sent from Command |
| OH day | Run of show, section 5. Live stories | Charles, VA | Sign-ins processed by 6pm |
| OH +1 | Follow-up sequence (section 6). Recap story and Reel. Attendance and feedback in the Monday seller update | Charles, VA | Every sign-in called |

## 3. Neighbor invites (three ways)

MREA rule: the neighbors are the best source of the next buyer and the next listing. Invite them three ways: door, mail, phone.

### Door knock script (Charles, OH -3)

```
"Hi, I'm Charles Brewer with Keller Williams. I'm the agent selling [ADDRESS], the [color/type]
house [direction] of you. We're holding an open house [day] from [time], and I like the
neighbors to see it first, before the buyers. You get to pick your new neighbor.

[Hand the door hanger.]

Quick question while I'm here: do you know anyone who's been wanting to move into
[NEIGHBORHOOD]? Friends, family, coworkers?

[If yes: get the name and permission to reach out, or ask them to pass along the hanger.]

One more: when this sells, it's going to set the number for the street. If you'd ever like to
know what that means for your place, I'll send it over, no strings. What's the best email?"
```

Log every conversation in Command the same evening: new contact, `Sphere` or `Seller` type, `Haven't Met`, `Src-OpenHouse` (source is the open house campaign even if the sign-in was at the door), temperature, note. Start `SP-12 Direct (Haven't Met)` for anyone who gave an email and did not opt out.

### Mailer or door hanger (VA, OH -5)

Copy from the marketing kit section 15. Contents: hero photo, "Neighbors first" headline, date, time, address, QR to the property page with a UTM (`?utm_source=doorhanger&utm_campaign=[address-slug]`), Charles's photo, [PHONE], EHO logo, brokerage line. Print 50, hand out at the door knock, mail the rest to non-answers if time allows.

### Neighbor calls (Charles, OH -2, 10 to 25 calls)

```
"Hi [Name], Charles Brewer with Keller Williams. I'm the agent on [ADDRESS], just down the
street from you. We've got an open house [day] at [time] and I'm inviting the neighbors to
come through before the buyers do. Would you like to stop by?

And do you know anyone who'd want to be your neighbor? I'd love to get them in first.

[Close:] Great, I'll text you the details. If you ever want a number on your own place,
I'm happy to do that too."
```

Voicemail version, under 25 seconds: name, brokerage, the open house day and time, "text me at [PHONE] if you want details," done.

## 4. Sign-in method

Every visitor signs in. No exceptions, including neighbors and other agents. Two options, pick one per event and test it the day before.

| Option | How | Notes |
|---|---|---|
| Command Open House app (preferred) | Tablet at the entry with the KW Command Open House app. Visitor enters name, phone, email, "working with an agent?", "how did you hear?" Contact lands in Command automatically | VA verifies the listing is selected in the app and the auto-tag is set to `Src-OpenHouse` if the app supports it. If not, VA tags by hand after |
| Digital form → Zap (backup) | Tablet or QR to a charlesbrewer.guru form: name, phone, email, agent status, timeline, notes. Zap `Z-05 Open House Form → Command Contact + Src-OpenHouse + SP-8x8 New Contact` creates the contact | Test submission deleted the morning of |
| Paper (emergency) | Clipboard with the same fields | VA enters within 2 hours of close |

Fields captured on every sign-in:
- Name, phone, email
- Working with an agent? (yes/no, who)
- Timeline to buy or sell (0 to 3 months / 3 to 6 / 6+ / just looking)
- Own or rent
- Live nearby? (neighbor flag)
- How did you hear? (sign, social, neighbor invite, portal, other)
- Notes (Charles adds after the conversation)

Charles's job at the door: "Come on in. We ask everyone to sign in so the sellers know who's been through, it takes ten seconds." Then a real conversation: what are they looking for, what's their timeline, are they a neighbor.

## 5. Day-of checklist

Pack list (VA, OH -1)
- [ ] Tablet charged, sign-in app or form open, backup paper sheets
- [ ] Directional signs (6 to 8), open house sign for the yard, balloons or flags if used and allowed
- [ ] Printed property flyers (25) with QR, floor plan on the back
- [ ] Printed "about the neighborhood" one-pager (from the kit's neighborhood paragraph plus a map)
- [ ] Charles's business cards, buyer consultation one-pager, home value offer card
- [ ] Shoe covers or a shoe mat, hand sanitizer
- [ ] Refreshments (water, something simple, no strong smells)
- [ ] Phone charger, portable speaker for low background music
- [ ] Lockbox code and alarm code (from Opportunity notes)

Run of show (Charles)

| Time | Task |
|---|---|
| -60 min | Arrive. Directional signs out at every turn from the main road. Yard sign rider swapped to "Open House Today" |
| -45 min | Walk the house: lights on, blinds open, doors open, toilet lids down, temperature, music low, valuables check |
| -30 min | Sign-in station at the entry. Flyers on the kitchen island. Refreshments out |
| -15 min | Arrival story posted. Text the seller "All set, doors open at [time]" |
| 0 | Doors open. Stand near the entry, greet everyone, sign in everyone |
| Every 30 min | Story update. Note traffic count in the Opportunity |
| Ongoing | Conversations: what they're looking for, timeline, agent status. Neighbors: "what would you want to know about your own value?" |
| Close | Last visitors walked to the door. Lights, locks, lockbox, alarm. Directional signs collected. Seller texted with the group count and initial reactions |
| +30 min | Charles voice-notes the VA in `#listings`: total groups, hottest 3 leads, neighbor conversations, feedback themes |

Safety: Charles keeps his phone on him, never goes into a basement or closed room with a visitor alone, and the VA knows the start and end time.

## 6. Follow-up sequence

Speed matters. Every sign-in hears from Charles the same day.

| When | Touch | Channel | Owner | Script |
|---|---|---|---|---|
| Same day, within 2 hours of close | VA processes sign-ins (section 7) | Command | VA | n/a |
| Same day, by 7pm | Personal text to every sign-in | SMS | Charles (VA drafts in Command, Charles sends) | "Hi [Name], Charles Brewer. Thanks for coming through [ADDRESS] today. What did you think? If you'd like a private look or want to see anything else in [NEIGHBORHOOD], I'm around this week." |
| Same day | Email with the property page, 3D tour, floor plan | Email | SmartPlan `SP-8x8 New Contact` step 1 (open house variant) | Kit email, shortened |
| Next day | Call every sign-in who is not working with an agent. Two attempts, then voicemail | Phone | Charles | "Following up on yesterday. Where are you in your search? What would make a house the one?" Book a buyer consult or a home value visit |
| Next day | Agents who signed in: email asking for their buyer's feedback | Email | VA | "Thanks for stopping by. Any feedback from your buyer I can pass to the seller?" |
| Day 2 to Day 56 | 8x8 continues: `SP-8x8 New Contact` runs the remaining 7 touches (video, market snapshot, neighborhood guide, call task, invitation, home value offer, handoff) | Mixed | SmartPlan + Charles call tasks | 8x8 sequence (see 02-DATABASE) |
| Day 56 | Handoff: `Met` contacts (Charles spoke with them) → `SP-33 Touch (Met)`. `Haven't Met` → `SP-12 Direct (Haven't Met)` | Command | SmartPlan last step creates VA task | n/a |
| Neighbors specifically | Home value offer email within 48 hours, then quarterly neighborhood update | Email | Charles approves, VA sends | "Here's what [ADDRESS] means for your value" |
| Seller | Attendance count, feedback themes, and hot leads in the Monday update | Email | Charles | weekly-seller-report-template.md |

Temperature after the call:
- `A` (0 to 30 days, no agent): buyer consult booked, Buyer pipeline Consult Set, `Hot`
- `B` (30 to 90): `Buyer-Nurture` via `SP-Buyer Nurture`, `Nurture`
- `C` (90+ or just looking): 8x8 continues, then 12 Direct or 33 Touch
- Neighbor with selling interest: `Seller` type, Seller pipeline Cultivate, `SP-Seller Nurture`

## 7. How the VA processes sign-ins (same day, within 2 hours)

1. Export or review the sign-in list (app, form, or paper).
2. For each visitor, in Command:
   - [ ] Contact exists? Search by phone and email first. Merge duplicates. Never create a second record.
   - [ ] New contact: type `Buyer` (or `Seller` if a neighbor with selling interest, `Agent-Referral` if an agent), relationship `Haven't Met` (or `Met` if Charles says he had a real conversation), status `New-Lead`, source `Src-OpenHouse` (never changed later).
   - [ ] Existing contact: add a note "Attended open house [ADDRESS] [date]," do not change the source tag.
   - [ ] Temperature from the sign-in timeline field: `A`, `B`, or `C`.
   - [ ] Notes: agent status, what they said they wanted, neighbor flag, Charles's voice-note comments.
   - [ ] Start `SP-8x8 New Contact`. Tag `8x8-Active`.
   - [ ] Agents: type `Agent-Referral`, no SmartPlan, task to Charles to send the feedback ask.
   - [ ] Working with another agent: still create the contact, note the agent's name, no 8x8, add to `SP-12 Direct (Haven't Met)` only if they opted in.
3. Add each new contact to the listing's Opportunity as a related contact or in the notes (so showing and open house traffic is visible from the listing).
4. Draft the same-day text for each sign-in in Command and message Charles in `#listings`: "[N] sign-ins processed, texts drafted, [N] flagged A."
5. Log the event in `05-Docs/OpenHouse-[date].md`: total groups, sign-in count, neighbors, agents, A/B/C split, feedback themes, what to do differently.
6. Update the Monday seller report data sheet with attendance and feedback.

## 8. Metrics per open house

| Metric | Target | Where it goes |
|---|---|---|
| Groups through | 10+ first weekend | Monday seller report |
| Sign-in rate | 100 percent | VA log |
| Neighbors attended | 5+ | VA log |
| A leads | 1 to 2 | `#leads` |
| Buyer consults booked | 1 | Buyer pipeline |
| Home value requests from neighbors | 2+ | Seller pipeline Cultivate |
| Same-day text sent to every sign-in | 100 percent by 7pm | Command timeline |
| Next-day calls completed | 100 percent attempted | Command tasks |
