# 06 Buyer System: Map

Read `/00-START-HERE/conventions.md` first. Every tag, stage, SmartPlan, and GPT name in this folder comes from that file.

## The promise

White glove: every buyer knows what happens next, before they have to ask. On the buyer side that means four things on every client, every time:

1. A human response within 5 minutes (8am to 8pm), first thing next morning otherwise. Automation acknowledges; Charles or the VA replies.
2. A real consultation before the first showing. Needs analysis, agency and buyer agreement, financing, the process, and the showing plan. No "let's just go look at a few."
3. A showing itinerary the night before and a recap the same evening. Every showing day, no exceptions.
4. A milestone-by-milestone under-contract experience. EMD, inspection, appraisal, insurance, utilities, walk-through, closing: the buyer hears from us before each one, not after.

If a buyer is not getting those four things, the system is broken and the fix goes to the top of the list.

## The buyer pipeline

`Cultivate → Consult Set → Consult Met → Buyer Agreement Signed → Showing → Offer Written → Under Contract → Closed`

| Pipeline stage | What it means | SmartPlan running | Status tag | Main doc |
|---|---|---|---|---|
| Cultivate | Lead exists, no consult booked yet | `SP-Speed to Lead` (days 1 to 10), then `SP-Buyer Nurture` | `New-Lead` then `Nurture` | buyer-journey-white-glove.md |
| Consult Set | Consult on the calendar | `SP-Buyer Nurture` paused; pre-consult packet sent | `Hot` | buyer-journey-white-glove.md |
| Consult Met | Consultation happened, Buyer Needs Analysis completed | none (manual touches) | `Hot` | buyer-consultation.md |
| Buyer Agreement Signed | Buyer agreement signed via DocuSign in Command | none (manual touches) | `Active` | buyer-consultation.md |
| Showing | Actively touring; itinerary and recap rhythm running | none (manual touches, Command tasks) | `Active` | buyer-consultation.md |
| Offer Written | Offer strategy call done, offer submitted | none | `Active` | buyer-consultation.md |
| Under Contract | Accepted offer; milestone tracker active | `SP-Buyer Under Contract` | `Under-Contract` | buyer-journey-white-glove.md |
| Closed | Keys delivered | `SP-Past Client Program` then `SP-33 Touch (Met)` | `Closed` | buyer-journey-white-glove.md |

Tag rules for every buyer contact: type `Buyer`, exactly one `Src-*` tag set at creation, relationship `Haven't Met` until the consult is met and then `Met`, temperature `A`, `B`, or `C` set by `CB Lead Responder` and confirmed by the VA.

## Who does what

| Role | Owns | Never does |
|---|---|---|
| Charles | The 5-minute human reply when he is available, the buyer consultation, every showing, offer strategy and negotiation, every phone call that carries news (offer accepted, inspection findings, appraisal result), final approval of anything client-facing | Data entry, building itineraries from scratch, chasing vendors, pulling comps into a worksheet |
| VA ([VA NAME]) | 5-minute reply when Charles is unavailable, consult booking, pre-consult packet, Buyer Needs Analysis entry into Command, running `CB Buyer Concierge`, drafting itineraries and recaps, milestone tracker upkeep, vendor and utility coordination, closing gift order, tags and stages | Advice on price or offer terms, negotiation, sending anything Charles has not approved |
| Command SmartPlans | `SP-Speed to Lead` acknowledgment and follow-up cadence, `SP-Buyer Nurture` drip, `SP-Buyer Under Contract` milestone emails and tasks, `SP-Past Client Program` | Anything requiring judgment |
| Zapier | Website and social forms into Command with tags, Slack `#leads` alert, Calendly booking into Command stage change, Drive folder for the transaction | Client communication |
| ChatGPT (`CB Lead Responder`, `CB Buyer Concierge`) | First-touch reply drafts and A/B/C qualification, consult prep brief, showing itineraries, showing recaps, offer strategy notes, milestone update narratives | Sending anything. Rule: ChatGPT drafts, a human approves, Command sends. |

## Files in this folder

| File | Use it when |
|---|---|
| `buyer-journey-white-glove.md` | You want the whole buyer experience, touch by touch, lead to home anniversary, mapped to stages and SmartPlans. Start here. |
| `buyer-consultation.md` | A consult is booked. The consult script, the Buyer Needs Analysis form, showing itinerary and recap templates, offer strategy worksheet, under-contract milestone tracker. |

## The buyer weekly rhythm

| Day | Charles | VA |
|---|---|---|
| Daily | Reply to every new buyer lead within 5 minutes when available; return every buyer call same day | Watch `#leads`; reply within 5 minutes when Charles is unavailable; log every reply in Command |
| Evening before showings | Approve itinerary by 7pm | Draft itinerary via `CB Buyer Concierge` by 5pm, send after approval |
| Evening after showings | Give VA voice notes or bullet feedback within 1 hour of last showing | Draft recap via `CB Buyer Concierge`, send after approval, log in Command |
| Monday | Review Buyer pipeline in Command: every `Active` buyer has a next showing or a next call scheduled | Update milestone trackers for every `Under-Contract` buyer; confirm this week's deadlines with lender, title, inspector |
| Wednesday | Call every `Hot` buyer without a consult set | Audit `SP-Speed to Lead` and `SP-Buyer Nurture` for stalled contacts; flag `Nurture` contacts with no touch in 30 days |
| Friday | Review offers written this week and lessons | Send weekend showing availability to all `Active` buyers; confirm lender pre-approval letters are current |

## Numbers Charles watches (MREA style)

| Metric | Source in Command | Target |
|---|---|---|
| New buyer leads this week | Contacts created with `Buyer` + `New-Lead` | tracked, not targeted |
| Lead to consult set rate | Consult Set / Cultivate | 20% or better on web and social leads |
| Consult met to agreement signed | Buyer Agreement Signed / Consult Met | 80% or better |
| Showings per closed buyer | Showing notes count / Closed | under 12 |
| Offer to contract rate | Under Contract / Offer Written | 50% or better |
| Contract to close rate | Closed / Under Contract | 90% or better |
| Days from consult to contract | Opportunity dates | under 45 for `A` buyers |
