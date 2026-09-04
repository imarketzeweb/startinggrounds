# Listing Launch Playbook

The job: get the property as viewable as possible, by as many of the right buyers as possible, in the first 14 days. Everything here is in service of that.

Pipeline stages covered: Listing Signed → Coming Soon → Active. SmartPlan running: `SP-Seller Listing Launch`. Listing stages: Coming Soon, Just Listed, Open House.

## 1. The Maximum Exposure Standard

Every listing gets every item below. Price point and property size do not change the list. If an item is impossible for a specific property (no drone in restricted airspace, for example), the VA notes why in the Opportunity and Charles signs off.

### Media (delivered to `Listings/[YYYY-MM] [Street Address]/`)

| Asset | Spec | Folder |
|---|---|---|
| Pro photos | 25 to 40 edited stills. Wide, bright, straight verticals. Every room, front and back exterior, street view, key details. Ordered for MLS (front, living, kitchen, primary, baths, other beds, extras, backyard, floor plan last) | `01-Photos` |
| Twilight shot | 1 to 2, front exterior at dusk with all lights on. Composite is fine. Use as hero when the exterior is strong | `01-Photos` |
| Drone stills | 5 to 10. Roof, lot lines, backyard, proximity to parks/water/amenities. Verify airspace and local rules | `01-Photos` |
| Drone video | 30 to 60s, orbit plus reveal. Used in the walkthrough edit and the Coming Soon Reel | `02-Video` |
| Walkthrough video | 60 to 90s vertical (9:16), plus a 16:9 export for the property page and MLS. Hook, tour, CTA structure from the marketing kit script. Captioned | `02-Video` |
| 3D tour | Matterport or Zillow 3D Home. Whole home including garage if finished. Link live by Day -3 | `03-3D-FloorPlan` |
| 2D floor plan | Every level, room dimensions, total sqft, north arrow. Branded and unbranded versions | `03-3D-FloorPlan` |
| Virtual staging | Vacant homes only: 5 to 8 key rooms. Must be labeled "virtually staged" in MLS and on the property page. Keep the unstaged photo in the set too | `01-Photos` |

### Places the listing must appear

| Channel | What | Owner | Deadline |
|---|---|---|---|
| MLS | Every field completed (not just required ones), all photos in order, video link, 3D link, floor plan uploaded, showing instructions, open house dates. Public remarks from the kit, Fair Housing checked | VA enters, Charles approves | Day -1 draft, Day 0 live |
| Syndication check | Zillow, Realtor.com, Redfin, Homes.com. Confirm photos, price, description, video, and 3D all pulled through. Claim the Zillow listing so the video shows | VA | Day +1 by noon |
| Single-property landing page | charlesbrewer.guru/[address-slug]: hero, video, 3D, gallery, floor plan, features, neighborhood, open house, showing request form → Command with `Src-Website` | VA builds from kit copy | Day -4 |
| KW Command Sites listing page | Auto-populates from MLS. Verify it renders and links back to the property page | VA | Day +1 |
| KW app | Confirm the listing appears and the Charles Brewer agent profile is attached | VA | Day +1 |
| Google Business Profile | Post per stage (Coming Soon, Just Listed, Open House, Under Contract, Just Sold) with photo and link | VA | Each stage |
| Nextdoor | Coming Soon and Just Listed posts from Charles's profile in the listing's neighborhood, plus open house | VA drafts, Charles posts (personal profile) | Day -3, Day 0, open house week |
| Facebook Marketplace | Real estate listing type, all photos, link to property page | VA | Day 0 |
| Instagram, Facebook, TikTok, LinkedIn | 5-stage sequence, social-media-listing-templates.md | VA | Per stage |
| Coming Soon status | If the local MLS allows Coming Soon: use it, Day -3 to Day 0. Verify local MLS rules on showings, marketing, and duration before using. If not allowed, Coming Soon is social and email only and no showings occur | VA verifies rules quarterly, Charles decides | Day -3 |
| Database email blast | Just Listed email to the full Command database (all `Met` and `Haven't Met`), plus a Buyer-only and Investor-only version if relevant | SmartPlan `SP-Seller Listing Launch` sends, VA loads the kit copy | Day 0 |
| Agent-to-agent email | To every agent who has sold or shown in [NEIGHBORHOOD] in 12 months (MLS reverse prospecting export) and the [BROKERAGE OFFICE] roster. Broker open invite included | VA sends from Command Campaigns | Day 0 |
| MLS reverse prospecting | Run it on Day 0 and again Day 3. Email the matching agents directly: "Your buyer's search matches [ADDRESS]" | VA | Day 0, Day 3 |
| Broker open | Weekday, 11am to 1pm, lunch. First week | Charles hosts | Day 2 to 4 |
| Mega open house | First weekend, both days if possible. open-house-system.md | Charles hosts, VA runs promo | Day 5 to 7 |
| 10 neighbor calls | MREA "just listed" calls to the 10 closest neighbors: "Do you know anyone who'd want to be your neighbor?" Script in the kit | Charles | Day 0 to 1 |
| Circle prospecting | Beyond the 10 calls: 25 to 50 more neighbors by phone across the first week. Just Listed and open house invite. Ringless voicemail only if compliant in [MARKET] and only to numbers with prior consent | Charles (VA builds the list) | Days 1 to 5 |
| Sign | Brokerage sign, Charles rider, QR rider pointing to the property page (QR tracked with a UTM). "Coming Soon" rider Day -2, swap to "Open House" and "Under Contract" riders | VA orders | Day -2 |
| Showing instructions | ShowingTime or equivalent. Restrictions, lockbox, notes, auto feedback request on, seller notifications on, Charles and VA both on the notification list | VA | Day -3 |

## 2. Launch timeline, Day -14 to Day +14

| Day | Task | Owner | Done when |
|---|---|---|---|
| -14 | Listing signed. Command setup, Drive folder, title opened, vendors booked, launch date fixed | VA | `SP-Seller Listing Launch` running, all vendors confirmed |
| -14 | Seller welcome call | Charles | Seller knows the 14-day plan |
| -13 | Disclosures sent via DocuSign, vendor schedule texted to seller | VA | Seller has every date |
| -12 | Seller prep call | Charles | Prep checklist in seller's hands |
| -10 | Stager walk, handyman punch list | VA schedules | Punch list in `05-Docs` |
| -9 | HOA docs ordered, tax and utility data pulled, MLS input sheet started | VA | MLS input sheet 80 percent done |
| -8 | Staging install if vacant | Stager | Photos of staged rooms in `#listings` |
| -7 | Clean, landscape. Photo day prep text | VA, SmartPlan | Seller confirms ready |
| -6 | Photo, drone, video, 3D, floor plan shoot | Photographer, VA | Shoot complete, delivery date confirmed |
| -5 | Media delivered and sorted into folders. `CB Listing Marketer` run. Kit reviewed by Charles | VA, Charles | Kit approved and saved to `04-Marketing-Kit` |
| -5 | MLS draft: every field, remarks, showing instructions, no photos yet | VA | Draft saved, Charles has reviewed remarks |
| -4 | Seller approval of remarks and hero photo. Property page built. Video edited in CapCut (9:16 and 16:9). Social assets built in Command Designs or Canva | VA | Seller approval logged in Opportunity notes |
| -3 | Stage → Coming Soon. MLS Coming Soon if allowed. Coming Soon posts (IG, FB, TikTok, LinkedIn, GBP, Nextdoor). Seller marketing summary sent. ShowingTime configured | VA | Coming Soon live everywhere on the list |
| -2 | Sign and lockbox installed. Agent-to-agent email scheduled. Database blast loaded in SmartPlan. Broker open and open house dates in MLS draft | VA | Sign photo in `#listings` |
| -1 | Listing QA checklist (section 4). Photos uploaded to MLS in order. Links tested. "Tomorrow we go live" text | VA, Charles | QA signed off by Charles in `#listings` |
| 0 | Active in MLS at [time, typically Thursday 8am or per local convention]. Just Listed posts. Database blast. Agent-to-agent email. Reverse prospecting. Facebook Marketplace. 10 neighbor calls. "We are live" text to seller with links | VA, Charles | All Day 0 items checked in `#listings` |
| +1 | Syndication check with screenshots to seller. Command Sites and KW app verified. Zillow listing claimed. Circle prospecting begins | VA, Charles | Syndication screenshot email sent |
| +2 | Broker open. Showing feedback relayed as it arrives (24h max) | Charles, VA | Broker open attendee list in Opportunity notes |
| +3 | Reverse prospecting round 2. Open house promo push begins (open-house-system.md) | VA | Open house RSVPs tracking |
| +4 | Neighbor invites for open house (door knock, mailer, calls) | Charles, VA | 50 neighbors invited |
| +5 to +7 | Mega open house. Open House posts and stories | Charles, VA | Sign-ins processed same day |
| +7 | First Monday update to seller (weekly-seller-report-template.md) | VA, Charles | Sent by 12pm |
| +8 | Review week-one numbers internally: showings, views, saves, feedback themes | Charles, VA | Adjustments logged |
| +10 | Second-week content: neighborhood spotlight post, feature Reel, 3D tour post | VA | Posted |
| +12 | Second open house decision | Charles | Yes/no in `#listings` |
| +14 | Second Monday update. If no offers: price and marketing review meeting (section 5) | Charles | Meeting held, decision logged |

## 3. The 5-stage social sequence (high level)

Details, captions, and specs are in social-media-listing-templates.md.

| Stage | When | Lead asset | Goal |
|---|---|---|---|
| Coming Soon | Day -3 to Day -1 | Teaser Reel (drone reveal, no address on day one, then reveal), story countdown | Build a waitlist of DMs and property page sign-ups |
| Just Listed | Day 0 to Day 4 | Walkthrough Reel, photo carousel, feature highlights | Showings booked in the first 72 hours |
| Open House | Day +3 to open house day | Invite static, story poll, countdown sticker, live story from the house | Foot traffic and neighbor sign-ins |
| Under Contract | Contract day | Static or short Reel, "under contract in [N] days" | Social proof for future sellers |
| Just Sold | Closing day | Static, seller testimonial clip if available | Social proof and referral ask |

Each video is repurposed: one edit → IG Reel, TikTok, FB Reel, YouTube Short (parked but post anyway), IG and FB Story, LinkedIn native video.

## 4. Listing QA checklist (VA runs on Day -1, Charles signs off in `#listings`)

Nothing goes Active until every box is checked.

MLS
- [ ] Address, unit, city, zip, county, parcel number match the tax record
- [ ] Price matches the listing agreement
- [ ] Beds, baths, sqft, lot, year built match the Intake Form and the tax record (note the sqft source)
- [ ] Every optional field completed: HOA, dues, schools, garage, parking, HVAC, roof, appliances included, exclusions, utilities, showing instructions, lockbox type
- [ ] Public remarks: proofread twice, no typos, no abbreviations a buyer would not understand, no Fair Housing violations (checklist in the kit), no references to price cuts or motivation
- [ ] Private agent remarks: showing instructions, lockbox, offer instructions, commission per agreement, seller preferences on closing and possession
- [ ] Photos: 25 to 40 uploaded, hero photo first, order follows the standard, no duplicates, no photos of the seller's personal items or family photos, no photos of people, virtual staging labeled
- [ ] Video link resolves (unbranded version for MLS if required by local rules)
- [ ] 3D tour link resolves (unbranded if required)
- [ ] Floor plan uploaded as the last photo and as a document
- [ ] Open house and broker open dates entered
- [ ] Listing date and expiration match the agreement
- [ ] Coming Soon rules followed if used (no showings before Active, marketing limits per MLS)

Property page (charlesbrewer.guru)
- [ ] Page loads on phone and desktop, under 3 seconds
- [ ] Price, beds, baths, sqft match MLS exactly
- [ ] Video plays, 3D loads, gallery in the same order as MLS
- [ ] Showing request form submits to Command with `Src-Website`, test submission done and deleted
- [ ] QR code on the sign rider scans to this page with the UTM
- [ ] Open house date and time correct

Showing setup
- [ ] ShowingTime restrictions match the Intake Form
- [ ] Lockbox installed, code tested, code stored only in Opportunity notes
- [ ] Seller notifications on, Charles and VA on the notification list
- [ ] Auto feedback request on, 2 hours after each showing
- [ ] Sign up, rider correct, QR scanned and verified

Social and email
- [ ] All Just Listed posts scheduled with correct address, price, and link
- [ ] Database blast loaded in `SP-Seller Listing Launch` with correct links, test sent to Charles
- [ ] Agent-to-agent email list built, test sent
- [ ] GBP, Nextdoor, Facebook Marketplace posts drafted

Command
- [ ] Opportunity at Coming Soon, moves to Active on Day 0
- [ ] `SP-Seller Listing Launch` on the correct step
- [ ] Contact tags: `Seller`, `Active`, `Met`

Sign-off: VA posts "QA complete, [ADDRESS], go live [date/time]" in `#listings`. Charles replies "approved."

## 5. Day 14 and Day 30 with no offers

Rule: no listing sits without a documented decision at Day 14 and Day 30. The seller was told at the consultation that these checkpoints exist.

### Day 14 review meeting (Charles, phone or in person, 30 minutes)

Prep (VA, the day before): 14-day report from the Monday template plus the items below.

Agenda
1. The numbers: showings (vs the neighborhood average for the first 14 days), online views and saves by portal (vs comparable listings if visible), open house traffic, feedback themes.
2. Diagnosis, one of three:
   - Low views, low showings: price or hero photo. Buyers are not clicking.
   - High views, low showings: price. Buyers are looking and not coming.
   - Showings but no offers: condition, layout, or price relative to what they saw the same day. Feedback tells you which.
3. What changed in the market since launch: new competing listings, pendings, price reductions nearby.
4. Options, presented with a recommendation:
   - Price adjustment (specific number, based on where the next buyer bracket starts)
   - Marketing refresh: new hero photo, re-edited video, twilight hero, updated remarks, second open house, re-blast to database and agents
   - Condition fix: the one thing feedback keeps mentioning
   - Hold: only if showings are healthy and feedback is neutral
5. Decision, logged in the Opportunity notes and confirmed to the seller in writing the same day.

### Day 30 formal price review (Charles, in person, 45 minutes)

Prep (VA): fresh CMA with solds and pendings from the last 30 days, updated absorption rate, full traffic history, all feedback verbatim, list of every marketing action taken with dates.

Agenda
1. Restate the original plan and the Day 14 decision.
2. The 30-day numbers next to the neighborhood averages.
3. New CMA: what has sold and gone pending since launch, at what price, in how many days.
4. The honest conversation: "The market has told us what it thinks of the price. Here is what I'd do if this were my house."
5. Recommendation with a specific number and a relaunch plan: price change in MLS, new hero photo, "price improved" social and email, agent re-blast, reverse prospecting, second mega open house.
6. If the seller declines: document it, confirm the next checkpoint (Day 45), and continue the Monday updates without fail.

Relaunch checklist after a price change (VA)
- [ ] MLS price updated, remarks refreshed
- [ ] Property page updated
- [ ] "Price improved" posts (do not use "reduced" in seller-facing or public copy)
- [ ] Database email and agent-to-agent email
- [ ] Reverse prospecting rerun at the new price bracket
- [ ] Syndication recheck within 24h
- [ ] Seller receives a confirmation with the new links
