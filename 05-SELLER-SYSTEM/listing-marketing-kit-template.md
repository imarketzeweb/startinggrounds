# Listing Marketing Kit Template

This is the exact deliverable `CB Listing Marketer` produces from the Seller Intake Form. The VA pastes the completed Intake Form into the GPT, the GPT returns every asset below in the fixed order in section 3, Charles approves, the VA loads it into MLS, Command, Canva, and the social schedule.

Rule: ChatGPT drafts, a human approves, Command sends. The Fair Housing checklist in section 4 is run on every kit before Charles sees it.

File: `[Address]-Marketing-Kit.md` in `Listings/[YYYY-MM] [Street Address]/04-Marketing-Kit/`.

## 1. How to run it (VA)

1. Open `CB Listing Marketer`.
2. Paste the full Seller Intake Form. Add: list price, launch date, open house date and time, property page URL, 3D tour URL, video URL, Charles's [PHONE] and [EMAIL], [CALENDLY LINK].
3. Say: "Produce the full Listing Marketing Kit in the fixed output order. Use placeholders for anything missing. Flag any Fair Housing risk in the last section."
4. Save the output to `04-Marketing-Kit`. Run the Fair Housing checklist. Send to Charles in `#listings` for approval.
5. After approval, load each asset into its destination (table in section 5).

## 2. Asset definitions

Every asset has a format, a length limit, and required placeholders. The GPT must respect the limits. The VA checks the counts.

### 2.1 MLS public remarks
- Format: one paragraph, plain text, no bullets, no emojis, no ALL CAPS words.
- Length: check local MLS limit, default 1,000 characters. Provide a 1,000-character version and a 500-character version.
- Must include: property type, standout feature first, key upgrades with years, layout, outdoor space, location anchors (commute, parks, shopping), showing or open house line if allowed.
- Must not include: anything on the Fair Housing list, "motivated," "must sell," price history, seller's reason for moving, school quality claims (name the district and say "buyer to verify").
- Placeholders: [ADDRESS], [BEDS], [BATHS], [SQFT], [NEIGHBORHOOD].

### 2.2 Headline options
- Format: 3 options, each under 60 characters.
- One feature-led, one location-led, one lifestyle-led.
- Example shape: "Renovated Craftsman with Detached Studio in [NEIGHBORHOOD]".

### 2.3 Short blurb
- Format: one sentence, under 250 characters, Zillow-style. Describes the property, ends with the strongest hook.

### 2.4 Feature bullets
- Format: 8 to 12 bullets, each under 12 words. Fact first, benefit second.
- Order: kitchen, primary suite, living spaces, outdoor, systems and upgrades (with year), garage and parking, location.
- Example: "New roof (2023) and HVAC (2022): the expensive stuff is done."

### 2.5 Neighborhood paragraph
- Format: 80 to 120 words. Names the neighborhood, three specific places (park, coffee, grocery or trail), commute anchors with approximate drive times, and one thing residents like. School district named only with "buyer to verify." No demographic language, no "safe," no "family-friendly," no "quiet" as a code word.

### 2.6 Lifestyle story paragraph
- Format: 100 to 150 words, second person ("you"), present tense. Built from the seller's favorite things and favorite room. Walks the reader through a day in the home. Describes the property and the experience, never the kind of person who lives there.

### 2.7 Walkthrough video script (60 to 90 seconds, vertical)
Format: shot list table with three columns: seconds, shot, on-screen text or voiceover.

Required structure:
| Section | Seconds | Content |
|---|---|---|
| Hook | 0 to 3 | Drone reveal or the single best interior shot. On-screen: the headline or a question. No address yet if Coming Soon |
| Tour | 3 to 70 | Front exterior → entry → living → kitchen → primary → one more feature → backyard. One line of voiceover per shot, feature plus benefit |
| CTA | 70 to 90 | Price (if Just Listed), open house date, "Link in bio for the 3D tour," Charles on camera or voiceover with [PHONE] |

Deliver: shot list, voiceover script (under 180 words), on-screen text per shot, caption for the 16:9 export.

### 2.8 15-second Reel script
- Format: 5 shots, 3 seconds each. Hook text on shot 1. Address or "Coming Soon to [NEIGHBORHOOD]" on shot 5. Suggested trending-audio type (no specific track, VA picks in CapCut).

### 2.9 Database email blast
- Format: 3 subject lines (under 50 characters each), preview text (under 90 characters), body 150 to 200 words, one button CTA to the property page, secondary text link to the 3D tour, sign-off with [PHONE] and [CALENDLY LINK].
- Provide three versions: general database, Buyer-tagged contacts ("does this fit your search?"), Investor-tagged contacts (rent estimate placeholder, cap rate placeholder, "reply for the numbers").
- Loaded into `SP-Seller Listing Launch` by the VA.

### 2.10 Agent-to-agent email
- Format: subject line under 50 characters, body under 120 words. Price, beds, baths, sqft, one standout, showing instructions summary, broker open date, link to MLS and property page, commission line only if compliant with local rules and the agreement. Professional, no hype.

### 2.11 Social captions, 5 stages × 4 platforms
For each stage (Coming Soon, Just Listed, Open House, Under Contract, Just Sold) produce a caption for IG, FB, LinkedIn, TikTok.

| Platform | Length | Hashtag rule | CTA |
|---|---|---|---|
| Instagram | Under 150 words, first line is the hook, line breaks between thoughts | 15 to 20 hashtags in the first comment: 5 branded, 5 to 8 local, 5 property-type. From the sets in social-media-listing-templates.md | "Link in bio" or "DM me [keyword]" |
| Facebook | Under 120 words, conversational, link in the post | 3 to 5 hashtags max, local only | Direct link to property page |
| LinkedIn | Under 150 words, professional angle (market, process, result), no emojis beyond one | 3 to 5 hashtags, professional and local | Link in first comment |
| TikTok | Under 100 characters on-screen plus caption under 150 characters | 4 to 6 hashtags, mix of broad (#realestate) and local | "Comment TOUR for the link" |

Under Contract and Just Sold captions: no sale price unless Charles confirms it is permitted by the seller and MLS rules. Just Sold uses "[N] days on market" and "[N] offers" when true.

### 2.12 Google Business Profile post
- Format: under 300 words per stage, but 80 to 120 is the target. Photo suggestion. Button: "Learn more" to the property page. One post per stage.

### 2.13 Nextdoor post
- Format: Coming Soon and Just Listed versions plus open house. Under 100 words, neighborly tone, posted from Charles's personal profile. Invite neighbors to the open house, ask them to share with anyone who wants to move nearby. No hashtags.

### 2.14 Text message to sphere
- Format: under 300 characters, personal, from Charles. "Just listed [ADDRESS] in [NEIGHBORHOOD], [BEDS]/[BATHS], [PRICE]. Know anyone looking there? [link]". Provide a Coming Soon and a Just Listed version. Sent from Command to `Sphere` and `Past Client` tagged contacts only after Charles approves.

### 2.15 Open house invite
- Format: three pieces. (a) Door hanger or mailer copy: under 60 words, date, time, address, QR placeholder. (b) Email invite: subject under 50 characters, body under 100 words. (c) Story text: under 20 words.

### 2.16 10 neighbor call script
- Format: under 120 words, MREA "just listed" style. Opens with the listing, asks "Do you know anyone who'd want to be your neighbor?", invites to the open house preview, ends with a soft home value offer. Include the voicemail version (under 30 seconds).

### 2.17 Single-property page copy
- Format: sections in order: hero headline (from 2.2), subheadline (from 2.3), intro paragraph (from 2.6), features (from 2.4), neighborhood (from 2.5), video and 3D section labels, open house block, showing request form intro line, agent block with [PHONE] [EMAIL] [CALENDLY LINK]. Meta title under 60 characters, meta description under 155 characters.

### 2.18 Seller-facing marketing summary
- Format: one page, seller as the audience. "Here is everything we are doing to sell [ADDRESS]." Sections: media produced, where the listing appears (full list from the launch playbook), the social sequence with dates, email blasts with send dates, open house dates, what the seller can expect each Monday, who to contact for what ([VA NAME] for logistics, Charles for decisions). Warm, specific, no jargon.

### 2.19 Fair Housing flags
- Format: the GPT lists any phrase in its own output that could be a Fair Housing concern and offers the replacement. If none, it says "No flags found. Human review still required."

## 3. Fixed output structure

The GPT returns exactly this structure, in this order, with these headings. The VA rejects any output that skips or reorders a section.

```
# LISTING MARKETING KIT: [ADDRESS]
Generated: [date] | Price: [PRICE] | Launch: [date] | Open House: [date/time]

## 01 MLS PUBLIC REMARKS
### 1,000-character version
### 500-character version

## 02 HEADLINES
1. (feature-led)
2. (location-led)
3. (lifestyle-led)

## 03 SHORT BLURB (under 250 chars)

## 04 FEATURE BULLETS (8 to 12)

## 05 NEIGHBORHOOD PARAGRAPH

## 06 LIFESTYLE STORY

## 07 WALKTHROUGH VIDEO SCRIPT (60 to 90s)
### Shot list (table)
### Voiceover
### On-screen text
### 16:9 caption

## 08 15-SECOND REEL SCRIPT

## 09 DATABASE EMAIL
### Subject lines (3)
### Preview text
### Body: General
### Body: Buyers
### Body: Investors

## 10 AGENT-TO-AGENT EMAIL

## 11 SOCIAL CAPTIONS
### Coming Soon: IG / FB / LinkedIn / TikTok
### Just Listed: IG / FB / LinkedIn / TikTok
### Open House: IG / FB / LinkedIn / TikTok
### Under Contract: IG / FB / LinkedIn / TikTok
### Just Sold: IG / FB / LinkedIn / TikTok
### Hashtag sets used (branded / local / property)

## 12 GOOGLE BUSINESS PROFILE POSTS (5 stages)

## 13 NEXTDOOR POSTS (Coming Soon / Just Listed / Open House)

## 14 SPHERE TEXT (Coming Soon / Just Listed)

## 15 OPEN HOUSE INVITE (door hanger / email / story)

## 16 NEIGHBOR CALL SCRIPT (live / voicemail)

## 17 SINGLE-PROPERTY PAGE COPY
### Meta title / meta description
### Page sections in order

## 18 SELLER-FACING MARKETING SUMMARY

## 19 FAIR HOUSING FLAGS
```

Equivalent JSON shape if the GPT is asked for machine-readable output (used if a Zap ever loads assets automatically):

```
{
  "address": "", "price": "", "launch_date": "", "open_house": "",
  "mls_remarks": {"long": "", "short": ""},
  "headlines": ["", "", ""],
  "blurb": "",
  "features": [],
  "neighborhood": "",
  "lifestyle_story": "",
  "video_script": {"shots": [], "voiceover": "", "on_screen": [], "caption_16x9": ""},
  "reel_15s": {"shots": []},
  "email_database": {"subjects": [], "preview": "", "general": "", "buyers": "", "investors": ""},
  "email_agents": {"subject": "", "body": ""},
  "social": {"coming_soon": {"ig": "", "fb": "", "li": "", "tt": ""}, "just_listed": {}, "open_house": {}, "under_contract": {}, "just_sold": {}},
  "hashtags": {"branded": [], "local": [], "property": []},
  "gbp": {"coming_soon": "", "just_listed": "", "open_house": "", "under_contract": "", "just_sold": ""},
  "nextdoor": {"coming_soon": "", "just_listed": "", "open_house": ""},
  "sphere_text": {"coming_soon": "", "just_listed": ""},
  "open_house_invite": {"door_hanger": "", "email": "", "story": ""},
  "neighbor_call": {"live": "", "voicemail": ""},
  "property_page": {"meta_title": "", "meta_description": "", "sections": []},
  "seller_summary": "",
  "fair_housing_flags": []
}
```

## 4. Fair Housing checklist (VA runs on every kit, Charles confirms)

Describe the property, never the people. If a phrase describes who should live there or who lives nearby, cut it.

Protected classes under the federal Fair Housing Act: race, color, religion, national origin, sex, familial status, disability. [MARKET] and state law may add more (source of income, age, marital status, sexual orientation, gender identity, military status, and others). Verify the local list annually.

- [ ] No mention of race, color, religion, national origin, sex, familial status, or disability, directly or by implication
- [ ] No "family-friendly," "perfect for families," "great for kids," "empty nesters," "bachelor pad," "adult community" (unless legally qualified 55+), "mother-in-law suite" (use "attached suite" or "in-law suite" only where locally accepted; prefer "guest suite with kitchenette")
- [ ] No "walking distance to [church/temple/mosque]" or naming a religious institution as a feature. Naming a public park or shopping center is fine
- [ ] No "safe," "secure neighborhood," "good neighborhood," "exclusive," "prestigious," "desirable area" as code words
- [ ] No "quiet" used to imply who lives nearby. "Cul-de-sac location" or "no through traffic" are fine
- [ ] No school quality claims ("great schools," "top-rated"). District name plus "buyer to verify" only
- [ ] No "handicap accessible" or "not suitable for" anyone. Describe features: "zero-step entry," "first-floor primary suite," "36-inch doorways"
- [ ] No "his and hers." Use "dual" or "two"
- [ ] No "master" if the local MLS or brokerage has moved to "primary." Use "primary suite"
- [ ] No description of the ideal buyer's demographics anywhere in public copy. "Ideal buyer" from the Intake Form is internal only
- [ ] No photos of people, family photos, religious items, or anything identifying the occupants
- [ ] Equal Housing Opportunity logo or statement on the property page, email blasts, and printed pieces
- [ ] Brokerage name and license disclosures per state rules on every public piece
- [ ] Virtual staging labeled
- [ ] Sale price on Just Sold only with seller permission and MLS compliance

If unsure, rewrite to describe the feature. "Near the park" replaces "great for kids." "Attached suite with private entrance" replaces "in-law suite."

## 5. Where each asset goes (VA loading map)

| Asset | Destination | Folder / tool |
|---|---|---|
| MLS remarks, headlines, features | MLS input | MLS |
| Blurb, property page copy, meta | charlesbrewer.guru property page | Site builder |
| Video script, Reel script | CapCut project | `02-Video` |
| Database emails | `SP-Seller Listing Launch` email steps | Command SmartPlans |
| Agent-to-agent email | Command Campaigns, agent list | Command |
| Social captions | Scheduler, one post per `[Address]-[Stage]-[Platform]` design | Command Designs / Canva |
| GBP posts | Google Business Profile | GBP |
| Nextdoor posts | Charles's Nextdoor profile | Charles posts |
| Sphere text | Command text to `Sphere` and `Past Client` | Command |
| Open house invite | Canva door hanger, Command email, IG story | Multiple |
| Neighbor call script | Charles's call list, Command task | Command Tasks |
| Seller-facing summary | Email to seller from Command, Day -3 | Command |
| Fair Housing flags | Fixed before anything above is loaded | n/a |
