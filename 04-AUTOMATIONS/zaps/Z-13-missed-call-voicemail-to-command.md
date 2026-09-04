# Z-13  Missed Call / Voicemail → Command Note + Ack + VA Task

## Name
`Z-13 Missed Call / Voicemail → Command Note + Ack + VA Task`

## Purpose
A missed call is a lead nobody logged. This Zap logs it in Command, sends a short acknowledgment text so the caller knows they reached the right person, and gives the VA a callback task with the voicemail transcript. It closes the gap between the phone and the CRM without pretending to be a human reply.

## Trigger
- **Google Voice** has no native Zapier trigger. Use **Email Parser by Zapier** (or **Gmail: New Email Matching Search** `from:voice-noreply@google.com`) on the missed-call and voicemail notification emails, which include caller number and the voicemail transcript.
- If Charles uses a business phone system (OpenPhone, Dialpad, RingCentral, Aircall, KW's Command phone if enabled): use that app's **Missed Call** and **New Voicemail** triggers directly; they are cleaner.

## Steps

1. **Formatter: Text: Extract Pattern** caller number, timestamp, transcript (if voicemail).
2. **Formatter: Numbers: Format Phone Number** to E.164.
3. **Filter:** skip if number is in the `Do Not Text` sheet (vendors, spam, family) or has called more than 3 times today.
4. **KW Command: Find Contact** by phone (verify search action).
5. **Paths:**
   - **Known contact:** **KW Command: Add Note** "Missed call {timestamp}. Voicemail: {transcript or none}". No new contact.
   - **Unknown number:** **KW Command: Create Contact** with First Name "Unknown", Last Name "{last 4 digits}", phone, tags `Sphere`, `New-Lead`, `Haven't Met`, `Src-Website` is wrong here, so use `Src-Sphere` until the VA learns the real source (SOP-01 step: correct the source tag on first conversation). Note as above.
6. **SMS by Zapier / Twilio / phone system: Send SMS** to the caller during 8am to 8pm only (Filter on hour): text below. Outside those hours, send the after-hours version.
7. **KW Command: Create Task** for VA (or Charles if the caller is tagged `Active` or `Under-Contract`): "Return missed call: {name or number}. VM: {transcript first 200 chars}" due within 30 minutes (fallback: Google Task + Slack).
8. **Slack: Send Channel Message** to `#leads` (template below).
9. **Google Sheets: Create Row** `Lead Log` only when a new contact was created (Source = Sphere, Note = "missed call, source TBD").

## Field mapping

| Source field | Destination field |
|---|---|
| caller number | Command Mobile Phone; SMS recipient |
| timestamp | Command note; task title |
| transcript | Command note; task description; Slack |
| contact tags (if found) | Task assignee logic |

## Acknowledgment SMS (the only automated client-facing text in this Zap)

Business hours:
```
Hi, this is Charles Brewer with Keller Williams. Sorry I missed your call. I'm with a client and will call you back within the hour. If it's quicker, reply here with what you need. -Charles
```
After hours:
```
Hi, this is Charles Brewer with Keller Williams. Thanks for calling. I'm away from the phone tonight and will call you back first thing tomorrow morning. Reply here anytime. -Charles
```
Both texts are pre-approved by Charles once; they are acknowledgments, not replies, consistent with service standard 1.

## Alert message template (Slack `#leads`)
```
:telephone_receiver: MISSED CALL  |  {name or "Unknown " + number}  |  {timestamp}
Voicemail: "{transcript or none}"
Command: {contact_link}  |  Tags: {tags or "new: Sphere, New-Lead"}
Ack text sent: {yes/no, after-hours version?}
Callback task: {assignee}, due {due}. If a client under contract, Charles calls.
```

## Error handling / fallback
- Parser misses a field: Slack alert still posts with raw email body; VA logs manually.
- Caller texts back: the reply lands in Command's inbox or the phone; the VA monitors `#leads` and the phone inbox every 30 minutes (daily checklist).
- Repeated spam numbers: VA adds to `Do Not Text` sheet.
- Never send the ack text to numbers marked as vendors or agents on the other side of a transaction; they are in `Do Not Text`.

## Test checklist
- [ ] Forward a real Google Voice missed-call email to the parser; number and transcript extract correctly.
- [ ] Known contact test adds a note, no duplicate contact.
- [ ] Unknown number creates "Unknown 1234" with correct tags.
- [ ] Ack text arrives; after-hours version at 9pm.
- [ ] Task assigned to Charles when caller is `Under-Contract`.
- [ ] `Do Not Text` number is skipped.

## Build time estimate
2.5 hours with Google Voice email parsing; 1.5 hours with a phone system that has native triggers.
