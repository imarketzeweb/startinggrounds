# charlesbrewer.guru: Funnel Architecture

Read `/00-START-HERE/conventions.md` first.

Platform note: the site platform is unknown. Everything here assumes any site builder or form tool that can post form submissions to Zapier or a webhook. Where the platform has a native Zapier integration, use it. Where it does not, use the webhook. Where neither exists, embed a form tool that does.

## 1. Funnel overview

```
Traffic sources                      Site                          Automation                    Human
------------------                   ----------------------        --------------------------    -------------------
Instagram / Facebook / TikTok /  ->  Home (router)             ->  Zap: form -> Command       -> 5-minute reply
LinkedIn / Google Business       ->  Sell / Buy / Invest       ->  tags + SP-Speed to Lead    -> consult / call
Yard signs + flyers (QR)         ->  Listings + property pages ->  Slack #leads alert         -> Charles or VA
Referrals / sphere               ->  Contact / About / Reviews ->  Thank-you page + Calendly  -> pipeline stage
```

Three entry paths:

| Path | Primary offer | Secondary offer | Booking |
|---|---|---|---|
| Seller | "What's my home worth" (instant home value request) | `[MARKET] Home Seller's Guide` + Pre-Listing Checklist | Listing consultation |
| Buyer | `[MARKET] Home Buyer's Guide` | Search alerts + First-Time Buyer Roadmap | Buyer consultation |
| Capital partner (Investor) | Capital Partner program application | Sample Deal Memo + "How the Capital Partner Program works" one-pager | Intro call |

Every path ends in the same three things: a contact in Command with the right tags, `SP-Speed to Lead` running, and a Slack `#leads` alert so a human replies within 5 minutes.

## 2. Page list

| Page | URL | Goal | Primary CTA |
|---|---|---|---|
| Home | `/` | Route the visitor to Sell, Buy, or Invest within 5 seconds | Three path buttons + "Book a call" |
| Sell | `/sell` | Capture home value request or guide download | "Get my home value" |
| Buy | `/buy` | Capture guide download or consult booking | "Get the Buyer's Guide" / "Book a buyer consult" |
| Invest | `/invest` | Capture capital partner applications to fund vetted, fully underwritten fix and flip deals | "Apply to partner" |
| Listings | `/listings` | Show active and recently sold listings; each links to its own property page | Per listing: "See this home" |
| Single-property page | `/listings/[address-slug]` | Convert interest in one home into a showing request or open house RSVP | "Schedule a showing" |
| About | `/about` | Trust: who Charles is, how he works, the white glove promise | "Book a call" |
| Reviews | `/reviews` | Proof: Google and Zillow reviews, client stories | "Book a call" |
| Blog / Resources | `/resources` | Search traffic and nurture content; every post links to one lead magnet | Contextual lead magnet CTA |
| Contact | `/contact` | Catch-all for anyone who does not fit a path | Form + click-to-call + Calendly |
| Thank-you pages | `/thanks-seller`, `/thanks-buyer`, `/thanks-investor`, `/thanks-contact` | Set the next step; book the call now | Calendly embed |

Navigation: Sell, Buy, Invest, Listings, About, Reviews, Resources, Contact. Phone number `[PHONE]` in the header on every page as click-to-call. Sticky "Book a call" button on mobile.

## 3. Landing page specs

### Home (`/`)

- Goal: route. Not a lead capture page, though it has one form at the bottom.
- Hero: photo of Charles, headline, one-sentence promise, three buttons (I'm selling / I'm buying / I'm investing).
- Below the fold: three path cards with one-line offers, review strip (3 reviews), featured listings (3), About teaser with video, footer form ("Not sure where to start?").
- Footer form fields: Name, Phone, Email, "I am a... (Seller / Buyer / Investor / Not sure)". Hidden: source=website, page=home, utm_source, utm_medium, utm_campaign, utm_content.
- After submit: `Z-01` creates or updates the Command contact with type tag from the dropdown (`Not sure` becomes `Sphere` and the VA re-tags after the first call), `Src-Website`, `New-Lead`, `Haven't Met`, note "Home page footer form", starts `SP-Speed to Lead`, posts to `#leads`. Redirect to `/thanks-contact`.

### Sell (`/sell`)

- Goal: home value request (primary), Seller's Guide download (secondary).
- Sections: hero with form, "What you get" bullets, how the white glove listing process works (5 steps), maximum exposure standard (photos, drone, 3D, floor plan, social sequence), reviews from sellers, Pre-Listing Checklist secondary offer, FAQ, final CTA.
- Primary form ("Get my home value"): Property address (address autocomplete if available), Name, Email, Phone. Optional: "When are you thinking of selling?" (0 to 3 months / 3 to 6 / 6 to 12 / Just curious). Hidden: source=website, page=sell, form=home-value, utm fields.
- Secondary form ("Send me the Seller's Guide"): Name, Email. Optional: Phone. Hidden: source=website, page=sell, form=seller-guide, utm fields.
- After submit (primary): `Z-03 Home Value Request → Command Contact + Seller Alert` creates or updates the contact: `Seller`, `Src-Website`, `New-Lead`, `Haven't Met`, address in the property field, note with timeline answer, starts `SP-Speed to Lead`, posts to `#leads` with the address and timeline, creates a Command task for the VA "Prepare home value estimate for [ADDRESS] within 4 hours" (Command home valuation or the tool chosen in lead-magnets.md). Redirect to `/thanks-seller`.
- After submit (secondary): `Z-01` with the same tags, note "Seller guide download", email with the guide PDF from Command (or the form tool's auto-responder), starts `SP-Speed to Lead`, `#leads` alert. Redirect to `/thanks-seller`.
- Thank-you page `/thanks-seller`: "Your estimate is on the way within 4 business hours. Want it faster and more accurate? Book a 15-minute call." Calendly embed. Guide download link. Video of Charles explaining what happens next (60 seconds).

### Buy (`/buy`)

- Goal: Buyer's Guide download (primary), consult booking (secondary, higher value).
- Sections: hero with form, "What you get" bullets, how the white glove buyer process works (consult, search, itinerary night before, recap same evening, milestone touches), lender partners note, First-Time Buyer Roadmap secondary offer, reviews from buyers, "Book a buyer consult" Calendly section, FAQ, final CTA.
- Primary form ("Get the Buyer's Guide"): Name, Email, Phone. Optional: "When do you want to move?" (0 to 3 months / 3 to 6 / 6 to 12 / Just looking), "Areas you are considering" (free text). Hidden: source=website, page=buy, form=buyer-guide, utm fields.
- Secondary: Calendly embed for the buyer consultation. UTM parameters passed into Calendly as hidden fields where supported.
- After submit: `Z-01` creates or updates the contact: `Buyer`, `Src-Website`, `New-Lead`, `Haven't Met`, note with timeline and areas, `A`/`B`/`C` set from the timeline answer (0 to 3 months = `A`, 3 to 6 = `B`, otherwise `C`), starts `SP-Speed to Lead`, guide emailed, `#leads` alert. Redirect to `/thanks-buyer`.
- Calendly booking: `Z-02 Calendly Consult Booked → Command Stage + Slack` creates or updates the contact, creates a Buyer Opportunity at `Consult Set`, stops `SP-Speed to Lead` if running, status `Hot`, `#leads` alert.
- Thank-you page `/thanks-buyer`: "Check your inbox for the guide. The fastest next step is a 30-minute consult." Calendly embed. Short video.

### Invest (`/invest`): the Capital Partner page

- Model: Charles sources fix and flip deals in `[MARKET]`, underwrites them, and brings them to capital partners who fund them. Charles project-manages the rehab and lists and sells the finished flip under the maximum exposure standard. The partner brings capital; Charles brings the deal, the management, and the exit. Terms for every project are set by attorney-drafted agreements. No return is promised anywhere on the page.
- Goal: Capital Partner program application (primary), Sample Deal Memo download (secondary, offered on the thank-you page and in the confirmation email).
- Sections: hero with form, "How the Capital Partner Program works" (7 steps), "What you receive on every deal" (the Deal Memo contents), the three structures explained in one line each (buy the deal outright / joint venture / private lender), what Charles does versus what the partner does, weekly project update sample, a sold-flip case study with before and after photos (anonymized address, actual numbers), reviews from partners and sellers, FAQ, compliance and disclaimer block, final CTA.
- Primary form ("Apply to partner"): Name, Email, Phone, Capital available (pick list: Under $[X] / $[X] to $[Y] / $[Y] to $[Z] / Over $[Z]; the VA sets bands for `[MARKET]` flip price points), Preferred structure (Buy the deal outright / Joint venture / Private lender / Not sure yet), Timeline (Ready now / Next 90 days / Exploring). Hidden: source=website, page=invest, form=capital-partner, utm fields. Consent line under the button.
- After submit: `Z-04 Capital Partner Form → Command Contact + Investor Alert` creates or updates the contact: `Investor`, `Src-Website`, `New-Lead`, `Haven't Met`, note with capital band, structure, and timeline, `A`/`B`/`C` from the timeline answer (Ready now = `A`, Next 90 days = `B`, Exploring = `C`), starts `SP-Speed to Lead`, `#leads` alert ("New capital partner lead: [name], [capital band], [structure], [timeline]. Reply within 5 minutes."), Command task "Book capital partner intro call." Confirmation email from Command carries the Sample Deal Memo PDF and the one-pager. Redirect to `/thanks-investor`.
- Thank-you page `/thanks-investor`: "Got it. Your Sample Deal Memo is on its way." Download button for the Sample Deal Memo PDF (secondary form not required; the email already captured the lead). Calendly embed for the 20-minute intro call. 60-second video of Charles walking through one closed flip. Line: "Terms on every project are set by attorney-drafted agreements. Nothing here is an offer of securities or a promise of any return."
- Compliance block (bottom of page and in the footer of the Deal Memo): "Charles Brewer is a licensed real estate agent with Keller Williams `[BROKERAGE OFFICE]`. Capital partner arrangements are private agreements drafted by an attorney and reviewed by each party's own counsel and CPA. Past project results are actuals from one project and do not predict future results. Nothing on this page is investment, legal, or tax advice, an offer of securities, or a guarantee of any outcome." Charles has his attorney review this block before publish.
- Follow-up after the intro call belongs to 07-INVESTOR-SYSTEM.

### Listings (`/listings`) and single-property pages

- Listings page: active listings first, then "Under Contract", then "Just Sold" (last 12 months). Each card: hero photo, `[ADDRESS]`, `[PRICE]`, `[BEDS]`/`[BATHS]`/`[SQFT]`, status badge, link.
- Single-property page per listing, built by the VA from the `CB Listing Marketer` kit within 24 hours of listing signed (Coming Soon version) and updated at each listing stage:
  - URL: `/listings/123-main-st`
  - Sections: photo gallery, video walkthrough, 3D tour embed, floor plan, price and facts, description, neighborhood highlights (business and amenity facts only), open house dates, map, "Schedule a showing" form, "Ask a question" click-to-call, share buttons.
  - Form: Name, Email, Phone, "Preferred showing time" (optional). Hidden: source=website, page=listing, listing_address=[ADDRESS], utm fields.
  - After submit: `Z-01` creates or updates the contact: `Buyer`, `Src-Website` (or `Src-Sign` when the form was reached via the sign QR code, determined by `utm_source=sign`), note "Showing request: [ADDRESS]", `SP-Speed to Lead`, `#leads` alert with the address, Command task for the VA "Book showing." Redirect to a thank-you section on the same page with Calendly.
  - At Just Sold: page stays live with a "Sold" badge, sale stats if permitted, and a CTA "Want to know what your home would sell for?" linking to `/sell` with `utm_campaign=[address]-justsold`.

### About, Reviews, Resources, Contact

- About: photo, 90-second video, the white glove promise in Charles's words, how the team works (Charles + [VA NAME]), Keller Williams `[BROKERAGE OFFICE]` affiliation, license number, community involvement. CTA: Book a call.
- Reviews: embedded Google reviews widget (or a manually maintained list with names and dates), Zillow reviews link, 3 short client stories (one per path). CTA on every third review.
- Resources: blog posts, each ending with the lead magnet CTA that matches its topic. Categories: Selling, Buying, Investing, `[MARKET]` market updates. Monthly cadence minimum.
- Contact: form (Name, Email, Phone, Message, "I am a..."), click-to-call, email `[EMAIL]`, office address `[BROKERAGE OFFICE]`, Calendly embed, social links. Same `Z-01` routing.

## 4. Hidden fields and Zap mapping

Every form carries these hidden fields. The VA verifies them in the Zap test each Monday.

| Hidden field | Value | Command destination |
|---|---|---|
| `source` | `website` | Tag `Src-Website` (or `Src-Sign` / `Src-Social` when `utm_source` says otherwise, per the routing rule below) |
| `page` | `home`, `sell`, `buy`, `invest`, `listing`, `contact` | Note on the contact |
| `form` | `home-value`, `seller-guide`, `buyer-guide`, `capital-partner`, `deal-memo`, `showing`, `contact` | Note on the contact; drives the follow-up task |
| `listing_address` | `[ADDRESS]` when on a property page | Note and Opportunity name |
| `utm_source` | `instagram`, `facebook`, `tiktok`, `linkedin`, `google`, `gbp`, `sign`, `flyer`, `email`, `qr` | Custom field or note |
| `utm_medium` | `social`, `signage`, `print`, `email`, `organic`, `paid` | Custom field or note |
| `utm_campaign` | `[address]-justlisted`, `buyer-guide-q3`, etc. | Custom field or note |
| `utm_content` | post or placement identifier | Custom field or note |

Source tag routing rule (set once at creation, never changed):
- `utm_source` in (`sign`, `qr` on a sign) becomes `Src-Sign`
- `utm_source` in (`instagram`, `facebook`, `tiktok`, `linkedin`) becomes `Src-Social`
- `utm_medium=paid` becomes `Src-Paid`
- Everything else becomes `Src-Website`

Zap skeleton for `Z-01 Website Form → Command Contact + Speed to Lead`:
1. Trigger: form submission (native app or Webhooks by Zapier, Catch Hook).
2. Formatter: split name, normalize phone to E.164, lowercase email, map `utm_source` to the `Src-*` tag.
3. Find or create Command contact by email (verify the Command action available in your Zapier account; if not available, use Command's lead import email or a Google Sheet that the VA imports daily).
4. Add tags: type tag, `Src-*`, `New-Lead`, `Haven't Met`.
5. Add note: page, form, timeline, areas, listing address, full UTM string.
6. Apply SmartPlan `SP-Speed to Lead` (or create a Command task "Start SP-Speed to Lead" for the VA if the action is not available).
7. Slack `#leads`: "New [type] lead: [name], [phone], [page]/[form], [utm_campaign]. Reply within 5 minutes."
8. Optional: send the lead magnet email from the form tool or Command.

Testing standard: every Monday the VA submits one test lead per form with a `TEST-` name prefix, verifies every step above in Command and Slack, then deletes the test contact.

## 5. Social-to-site traffic plan

### Link-in-bio structure

One link-in-bio page (the platform's own or a simple site page at `/links`) with this order:

1. "What's my home worth?" -> `/sell?utm_source=[platform]&utm_medium=social&utm_campaign=linkinbio-sell`
2. "Free [MARKET] Buyer's Guide" -> `/buy?utm_source=[platform]&utm_medium=social&utm_campaign=linkinbio-buy`
3. "Fund vetted fix and flip deals" -> `/invest?utm_source=[platform]&utm_medium=social&utm_campaign=linkinbio-invest`
4. "Current listings" -> `/listings?utm_source=[platform]&utm_medium=social&utm_campaign=linkinbio-listings`
5. "Book a call" -> `[CALENDLY LINK]?utm_source=[platform]&utm_medium=social&utm_campaign=linkinbio-call`
6. Featured listing of the week (rotates) -> property page with the listing campaign UTM

Replace `[platform]` per network: `instagram`, `tiktok`, `facebook`, `linkedin`.

### UTM naming convention

Format: `utm_source=[platform]&utm_medium=[medium]&utm_campaign=[campaign]&utm_content=[optional]`

| Use | Example |
|---|---|
| Listing post | `utm_source=instagram&utm_medium=social&utm_campaign=123-main-justlisted` |
| Open house post | `utm_source=facebook&utm_medium=social&utm_campaign=123-main-openhouse` |
| Just sold post | `utm_source=instagram&utm_medium=social&utm_campaign=123-main-justsold` |
| Guide promo | `utm_source=tiktok&utm_medium=social&utm_campaign=buyer-guide-q3` |
| Yard sign QR | `utm_source=sign&utm_medium=signage&utm_campaign=123-main-sign` |
| Flyer QR | `utm_source=flyer&utm_medium=print&utm_campaign=123-main-flyer` |
| Google Business Profile post | `utm_source=gbp&utm_medium=organic&utm_campaign=[topic]` |
| Email blast | `utm_source=email&utm_medium=email&utm_campaign=123-main-justlisted` |

Rules: all lowercase; address slug is street number and street name only; campaign stage matches the five listing stages (`comingsoon`, `justlisted`, `openhouse`, `undercontract`, `justsold`). The VA keeps a UTM log sheet in Drive: date, link, platform, campaign, post name (`[Address]-[Stage]-[Platform]`).

### QR codes on signs and flyers

- Every listing gets two QR codes generated by the VA (any QR generator that outputs SVG): one for the sign rider, one for flyers. Each encodes the property page URL with its own UTM.
- Sign rider text: "Scan for photos, video, and 3D tour." The rider is standard on every sign.
- Flyer QR goes on the front bottom-right with the same call to action.
- Open house sign-in tablet links to the property page with `utm_source=openhouse` so sign-ins get `Src-OpenHouse` (see 05-SELLER-SYSTEM/open-house-system.md).
- Test every QR code on a phone before it goes to print.

### Google Business Profile

- Website field: `https://charlesbrewer.guru/?utm_source=gbp&utm_medium=organic&utm_campaign=profile`
- Appointment link: `[CALENDLY LINK]` with `utm_source=gbp`
- Weekly GBP post (VA, Wednesday) linking to a site page: rotate listing, blog post, guide, review.
- Products or services entries: "Home valuation" -> `/sell`, "Buyer consultation" -> `/buy`, "Capital partner program" -> `/invest`.
- Review link from GBP is the one used in `SP-Past Client Program`; the same reviews are embedded on `/reviews`.

### Retargeting pixel note

Install the Meta pixel and Google tag on every page from day one, even before any paid spend, so the audience builds. Fire a custom event on each thank-you page (`lead_seller`, `lead_buyer`, `lead_investor`). When paid retargeting starts, audiences are: visited `/sell` without converting, visited a property page, visited `/invest`. Set `utm_medium=paid` on every paid link so those leads get `Src-Paid`.

## 6. Conversion checklist (VA runs monthly, Charles reviews)

- [ ] Mobile load under 3 seconds on every landing page (test with PageSpeed Insights or the platform's tool); compress images, lazy-load video and 3D embeds
- [ ] Click-to-call phone number in the header and footer on every page, tested on a phone
- [ ] Calendly embed on every thank-you page and on Buy, Invest, About, Contact; correct event type per page
- [ ] Reviews visible on every landing page (at least 3), dated within the last 12 months, refreshed monthly
- [ ] Proof on every landing page: number of homes sold, years in `[MARKET]`, average days on market for listings, or a recent client story
- [ ] Photo of Charles above the fold on Home and About, and on each landing page hero or sidebar
- [ ] One clear primary CTA per page; secondary CTA visually smaller; no competing links in the hero
- [ ] Forms ask for the minimum (Name, Email, Phone plus one qualifying question at most); every form tested end to end in Command
- [ ] Hidden fields populated and visible in the Command note on the test lead
- [ ] Every thank-you page tells the visitor exactly what happens next and when
- [ ] Fair Housing: no language about who lives in a neighborhood or who a home is "perfect for"; equal housing logo in the footer
- [ ] Brokerage compliance: Keller Williams `[BROKERAGE OFFICE]` name, license number, and required disclosures in the footer
- [ ] Single-property pages current: no "Coming Soon" on active listings, sold listings marked
- [ ] Link-in-bio links resolve with UTMs; QR codes on current signs resolve
- [ ] Pixel and tag fire on every page and every thank-you event
- [ ] Privacy policy and consent language on forms (text messaging consent checkbox where required)
- [ ] Site search (if any) and 404 page point back to Sell / Buy / Invest
