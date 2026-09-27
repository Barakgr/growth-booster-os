---
name: gb-brief
description: Produces the owner's daily brief from Google Calendar, Gmail, and the Growth Booster CRM or people/ notes. One priority line, today's calendar, leads and follow-ups waiting, urgent inbox, quick wins, and any drafts ready in Gmail Drafts. Under 300 words, saved to outputs/daily-brief/. Triggers when the owner says "daily brief", "morning brief", "what's on today", "what's on my plate", or types /gb-brief. Also runs unattended as the scheduled daily task.
---

# gb-brief — the daily brief

The owner reads this before the first coffee is done. Make it short, specific, and worth reading.

## Reads first

Read these before touching any tool. If `about-me/` does not exist, say this and stop:

> Setup hasn't run yet. Say **start setup** and we'll get your business, voice, and tools in place first.

1. `about-me/business.md` — what the business does, the owner's word for customers (use it from here on), how leads arrive, who answers the phone, hours.
2. `about-me/voice.md` — Part 2 is the kill list. Every draft gets scanned against it.
3. `about-me/brief-preferences.md` — overrides every default in this file: which calendars, how many inbox items, whether drafting is allowed, who counts as a real person, the "Never draft a reply to" list. If it disagrees with this skill, brief-preferences wins.
4. `about-me/memory.md` — last entry only. Look for open loops and anything "Next time" says to watch.

## Live data (read-only)

Reads, searches, and lists: go ahead without asking. Do not create, update, send, or delete anything while gathering. The only write this skill makes to a tool is a Gmail draft, under the rules below.

If a tool is not connected or a read fails, skip that section and add one line at the end of the brief: "Calendar not connected — say **connect calendar** to fix." Never invent a placeholder entry.

**Google Calendar**
- Pull today's events from the calendars brief-preferences names (default: primary).
- Before 10 AM, also pull tomorrow's first event.
- For each event, write one prep note from what you know: the customer's name from `people/` or the CRM, the last thing memory.md says about them, the address for a site visit. If you have nothing useful, leave the note out.

**Gmail**
- Search unread mail from the last 72 hours.
- Keep the 3–5 most urgent messages from real people: customers, leads, staff, suppliers, partners. Drop newsletters, receipts, notifications, marketing, and anything from a no-reply address.
- Urgent means: someone is waiting on the owner, money is involved, a date is close, or the tone is unhappy. Rank by that, not by recency.

**Leads and follow-ups** — pick the first that applies:
1. The Growth Booster CRM is connected: pull new leads since the last brief (date of the newest file in `outputs/daily-brief/`), plus any contact whose last inbound message has had no reply for 24 hours or more.
2. No CRM but `people/` exists: scan the notes for any open item or "follow up" line dated in the last 7 days.
3. Neither: leave the section out. The one-line note at the end covers it.

## Output structure (exact)

No greeting. No "here's your brief". Start with the heading. Under 300 words total.

```
# Daily brief — [Day], [Month D, YYYY]

**[ONE-LINE PRIORITY]**

## Today
[time] — [what] — [who] — [one prep note]

## Leads and follow-ups waiting
[name] — [source] — [how long waiting] — [suggested next step]

## Urgent inbox
[sender] — [subject] — [why it matters]

## Quick wins (under 15 minutes)
- [one concrete thing]

## Drafts ready for you
[recipient] — [subject] — in Gmail Drafts
```

- **Priority line.** One sentence, specific enough to act on without opening anything else. Good: "Call Mrs. Alvarez back before 10 — she left a voicemail at 6:10 last night and nobody answered." Bad: "Follow up on leads." If nothing stands out, name the oldest lead waiting. If nothing is waiting at all: "Quiet day. Nothing waiting on you."
- **Today.** One line per event, in time order. Skip all-day placeholders unless brief-preferences says otherwise. Tomorrow's first event goes last, labeled "Tomorrow, [time]". Empty calendar: "Nothing on the calendar."
- **Leads and follow-ups waiting.** Oldest first. "How long waiting" is plain: "since yesterday 4:40 PM", "3 days". Next step is one action: "text back", "send the estimate", "call". If the CRM has the name blank, write "no name given". Never guess.
- **Urgent inbox.** Most urgent first. "Why it matters" is five to ten words.
- **Quick wins.** Two or three things under 15 minutes, pulled from what you actually saw: a review to answer, a quote to nudge, a customer to thank.
- **Drafts ready for you.** Only if you saved at least one draft. Otherwise leave the section out.

Leave out any other section that has nothing in it.

## Draft rules

Drafts go to Gmail Drafts. Nothing is ever sent. The owner sends.

Draft only when all of these are true:
1. `brief-preferences.md` allows drafting.
2. The reply is obvious: a confirmation, a quick acknowledgment, or a plain yes/no.
3. The sender is not on the "Never draft a reply to" list.
4. The topic is not pricing, a complaint, a refund, anything legal or contractual, a cancellation, or a dispute. Those go to the owner untouched.

Before saving any draft: write it in the owner's voice from `voice.md` Part 1, matching the incoming message's length. Scan against the kill list (Part 2) and the owner's banned words (Part 1). Rewrite any sentence that trips, then scan again. Never promise a date, price, or result the owner has not already put in writing. Never name the CRM or software vendor.

Maximum three drafts per brief, or fewer if brief-preferences says so.

## Save and log

1. Save to `outputs/daily-brief/YYYY-MM-DD-brief.md`. If today's file exists, overwrite it.
2. Move yesterday's brief and any older ones into `outputs/daily-brief/archive/`. Create the folder if missing. Move, never delete.
3. Append one entry to `about-me/memory.md`:

```
### YYYY-MM-DD — Daily brief
- What we did: Daily brief — calendar N, leads N, urgent N, drafts N
- Files touched: outputs/daily-brief/YYYY-MM-DD-brief.md
- Decisions the owner made: [none if unattended]
- Open loops: [the priority line, plus any lead waiting 3+ days]
- Next time: [one thing to check tomorrow]
```

4. If `memory.md` now has more than 30 entries, move the oldest past 30 to the end of `about-me/memory-log.md`. Silently. Nothing is deleted.

## Scheduled (unattended) mode

Nobody is in the room. Ask no questions; if something is unclear, leave it out. Gather, write, save, log, stop. Do not end with the "act on any of these" line. If a connection has expired, produce the brief from what you can reach and note it in one line at the end.

## Interactive mode

Show the brief in chat exactly as saved, with the Leads, Urgent inbox, and Quick wins lines numbered. End with:

> Want me to act on any of these? Type a number, or **nothing**.

A draft-worthy pick goes to `/gb-write` (email or review) or `/gb-followup` (lead). A calendar pick gets the prep note in full. **nothing** gets "Done." and stop.

## Safety

- Read first, always. Searches and lists happen without asking.
- The only tool write is a Gmail draft under the rules above. Ask before any other create or update.
- Never send. Drafts only. The owner sends.
- Never delete. If the owner asks to remove something, move it to `_review/`.
- Never invent a lead, an email, a name, a number, or a calendar entry. Empty is fine. Made up is not.
- Never promise leads, rankings, or revenue in any draft.
- Never name the CRM or software vendor in anything a customer could read.
