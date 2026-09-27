---
name: gb-followup
description: Drafts a lead follow-up in the owner's voice — one SMS, one email, and a timing sequence — for a missed call, an unanswered inquiry, a quote that went quiet, a no-show, a finished job with no review, a past customer to win back, or a referral. Reads the Growth Booster CRM contact or a people/ note when one exists. Never sends. Trigger when the owner says "follow up with", "missed call from", "the quote went quiet", "haven't heard back from", "win back", "reactivate", or types /gb-followup.
---

# gb-followup — draft the follow-up, the owner sends it

Every lead the owner doesn't answer fast is water out of the bucket. This skill gets a reply drafted in minutes, in the owner's words, with a plan for what to send next. Read everything first. Draft second. Never send.

## Read before drafting

1. `about-me/business.md` — services, prices, the customer word, off-limits, and "What happens after a lead comes in" (that section tells you what the lead already went through).
2. `about-me/voice.md` — Part 1 (phrases, banned words, sign-off, formatting habits), Part 2 (the kill list), Part 3 (exceptions).
3. `references/playbook.md` — the timing sequence and stop rule for each situation.

Then look up the person, in this order. Stop at the first one that returns something.

1. **Growth Booster CRM** (read-only, if connected): search the contact by name or phone. Pull last contact date, notes, service asked about, any quote amount already on file.
2. **`people/<name>.md`** (if the folder and the file exist): read it in full.
3. **Ask one question**, then draft:
   > What do you know about them, and what happened last?

If business.md or voice.md still has `~~` placeholders, say so in one line and keep going with what's there. Do not stop the owner from getting a draft.

## Step 1 — name the situation

Read the owner's words and pick one:

| Situation | The owner says things like |
|---|---|
| Missed call | "missed call from", "went to voicemail" |
| Form or web inquiry not answered | "filled out the form", "emailed us Tuesday" |
| Quote or estimate sent, gone quiet | "sent the quote", "haven't heard back" |
| Appointment no-show | "didn't show", "wasn't home" |
| Job done, no review | "finished the job", "ask for a review" |
| Past customer to reactivate | "win back", "haven't used us in a year", "reactivate" |
| Referral introduced | "so-and-so referred", "got passed our name" |

If it fits none, or two equally, ask one question:
> Quick one — did they reach out and we missed it, or did we reach out and they went quiet?

Never ask two questions in a row.

## Step 2 — draft the pair and the sequence

Write both pieces in the owner's voice. Use the customer word from business.md. Use the person's first name.

**SMS** — under 320 characters. Sounds like a person typing on a phone, not a company. First name in it. One clear next step (call back, pick a time, reply yes, click nothing). Sign-off exactly as voice.md says.

**Email** — a subject line plus 3–6 sentences. Same voice. Same one next step. Sign-off per voice.md.

**Sequence** — pull the touches, spacing, and channel for this situation from `references/playbook.md`, and write them as plain instructions the owner can follow from their phone:

> Send the text now. If no reply by tomorrow 10 AM, send the email. If still nothing in 3 days, one last text: "[text]." Then stop and mark them no response.

Write the last-touch text out in full. Adjust the clock to the owner's hours if business.md gives them.

Hard rules for every draft:
- Only quote a price that appears in business.md. If the owner mentions a number that isn't there, use "the number we talked about" instead and flag it.
- No guarantees, no "you'll love it", no "best in town".
- No pressure. No fake deadlines, no "last chance", no "slots are filling up" unless business.md says it's true.
- Nothing from the off-limits list.
- Never name the CRM or any software in customer-facing text.
- Never invent a detail about the person. If you don't know what they asked about, write around it ("about the work at your place").

## Step 3 — scan and rewrite

Run every line of the SMS, the email, and the last-touch text against:
- voice.md Part 2 (the kill list)
- voice.md Part 1, "Words I never use"
- the formatting habits (exclamation points, emoji, length, sign-off)

Rewrite any sentence that trips. Rewrite again until nothing trips. The owner's own phrases from Part 1 win over the list. Do this silently; the owner sees the clean version only.

## Step 4 — show, gate, save

Show, in this order, with headers:

```
**SMS** (NNN characters)
[text]

**Email**
Subject: [subject]
[body]

**Sequence**
1. Now — text
2. [when] — email
3. [when] — last text: "[text]"
Then stop; mark no response.
```

Then say exactly:
> Type **good**, or tell me what to change. I'll save it — you send.

On **good**:
1. Save the whole thing to `outputs/followups/YYYY-MM-DD-<first-last>-<situation>.md` (situation slug: `missed-call`, `inquiry`, `quote`, `no-show`, `review`, `reactivate`, `referral`).
2. If `people/<name>.md` exists, append one line: `YYYY-MM-DD — Follow-up drafted: <situation>`.
3. Append a memory entry to `about-me/memory.md`:

```
### YYYY-MM-DD — Follow-up drafted for <name> (<situation>)
- What we did:
- Files touched:
- Decisions the owner made:
- Open loops:
- Next time:
```

Then tell the owner where the file is, in one line. Do not send. Do not offer to send. Do not create a CRM task, note, or message unless the owner asks, and then ask first.

On a change request: revise, re-scan, re-show, gate again.

## Several leads at once

When the owner says something like "follow up with everyone who called yesterday and got voicemail":

1. Pull the list from the Growth Booster CRM, read-only. If no CRM is connected, ask for the names in one question.
2. Name each person's situation (most will share one).
3. Draft one SMS per person. Skip the emails unless asked.
4. Show a table:

```
| Name | Situation | SMS |
|---|---|---|
```

5. Add one sequence line that covers the whole batch.
6. Gate:
   > Type **good** to save all of these, or name the ones to change.
7. On **good**, save one file per person as above, one memory entry for the batch.

Cap a batch at 15. Above that, say so and ask which 15 to do first.

## Safety

- Read first. Searches and lookups: do them without asking.
- Creates and updates (saving the file, the people/ line, the memory entry): only after **good**.
- Sends: blocked. This skill never sends a text, an email, or a CRM message, and never schedules one. The owner sends.
- Deletes: never. If the owner wants a draft gone, move it to `_review/`.
- Never invent a customer fact, a quote amount, a past conversation, a review, or a number.
- Never promise leads, rankings, results, or revenue.
- Never name the CRM or software vendor in anything a customer could read.

## Sounds like

Owner: "Missed call from Maria Lopez at 6:40 last night, no voicemail."

You look her up, find nothing, ask the one question, learn she's new. Then:

> **SMS** (148 characters)
> Hi Maria, it's Dave from Suncoast Comfort Air — sorry we missed you last night. What's going on with the AC? Call or text back anytime today. — Dave

Followed by the email, the sequence, and the gate. Short. Human. One next step.
