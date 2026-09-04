# Z-11  New Google Review → Thank-you + Social Task

## Name
`Z-11 New Google Review → Thank-you + Social Task`

## Purpose
Every Google Business Profile review gets a reply within 24 hours, gets turned into social proof, and gets logged in the testimonials sheet that feeds the website and listing presentations. Reviews are the compounding asset of the Past Client Program.

## Trigger
- **Google Business Profile: New Review** (Zapier has a Google My Business / Business Profile trigger; verify it connects to Charles's profile). Fallback: **Email Parser by Zapier** on the "You have a new review" notification email, or **RSS by Zapier** on a review aggregator feed if one is used.

## Steps

1. **Formatter:** extract reviewer name, star rating, review text, review date, review URL.
2. **Google Sheets: Create Row** in `Testimonials` (date, name, stars, text, URL, source = Google, used_on_social = No, used_on_site = No).
3. **KW Command: Find Contact** by name (verify search action). If found, **Add Note** "Left {stars}-star Google review on {date}" and add tag `Reviewed` (create this tag once; it is a status helper, not a type tag).
4. **ChatGPT (OpenAI) by Zapier** reply draft and social caption (prompt below).
5. **Paths:** 4 or 5 stars → normal flow. 3 stars or below → skip social, alert Charles by SMS: `Low review ({stars}) from {name}. Call them before replying.` No automated reply draft is posted publicly.
6. **Slack: Send Channel Message** to `#ops` (template below).
7. **KW Command: Create Task** for VA: "Post review reply on Google after Charles approves; schedule social proof post `Review-{name}-IG` and `-FB`" due +1 day (fallback: Google Tasks).
8. **KW Command: Create Task** for Charles: "Personal thank-you text to {name} for the review" due today.

## Field mapping

| Source field | Destination field |
|---|---|
| reviewer name | Testimonials sheet Name; Command note |
| star rating | Testimonials sheet Stars; path condition |
| review text | Testimonials sheet Text; GPT input |
| review URL | Testimonials sheet URL; Slack |

## ChatGPT step

Prompt (System: "You are CB Ops Manager writing on behalf of Charles Brewer, KW, [MARKET]. Gracious, specific, short. Never mention the transaction price, address, or anything private. Fair Housing safe. Output JSON only."):

```
A client left this Google review.
Name: {name}
Stars: {stars}
Review: {review_text}

Produce:
- reply: a public reply under 60 words, thanks them by first name, references one specific thing they said, no sales pitch, signed Charles.
- caption: an Instagram/Facebook caption under 80 words that quotes up to 25 words of the review in quotation marks, credits "{first name}, [MARKET] {buyer/seller if obvious}", and ends with one line inviting referrals with [PHONE]. Include 3 hashtags for [MARKET].
- card_text: the quote (max 25 words) and attribution for a Command Designs testimonial card.
Return: {"reply":"","caption":"","card_text":""}
```

Expected output:
```json
{"reply":"Thank you, Priya. Getting you keys two days early made my month too. Grateful you trusted us with the move. -Charles","caption":"\"Charles kept us calm and two steps ahead the whole way.\" Priya, [MARKET] buyer. ... Know someone moving? [PHONE]. #[MARKET]RealEstate ...","card_text":"\"Charles kept us calm and two steps ahead the whole way.\" Priya, [MARKET] buyer"}
```

## Alert message template (Slack `#ops`)
```
:star: NEW GOOGLE REVIEW  |  {stars} stars  |  {name}
"{review_text}"
{review_url}
Reply draft: {reply}
Social caption draft: {caption}
Charles: :white_check_mark: to approve reply and caption. VA posts reply on Google, builds the card in Command Designs, schedules Review-{name}-IG/FB.
Testimonials sheet updated. DRAFT for human review. Not sent.
```

## Error handling / fallback
- Trigger unavailable: VA checks Google Business Profile every Monday and Thursday (weekly checklist) and pastes new reviews into the Testimonials sheet; a **Google Sheets: New Row** trigger then runs steps 3 to 8.
- Reviewer name does not match a contact: note is skipped; VA links manually if they recognize the client.
- Never auto-post the reply. Google replies are public and permanent.

## Test checklist
- [ ] Simulate with a test row in Testimonials (sheet-trigger version) or a test email to the parser.
- [ ] Reply and caption drafts appear in `#ops` with correct name.
- [ ] 2-star test sends SMS to Charles and no caption.
- [ ] Tasks created for VA and Charles.
- [ ] Reply contains no address or price.

## Build time estimate
2 hours.
