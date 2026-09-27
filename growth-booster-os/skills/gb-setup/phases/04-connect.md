# Phase 4 — Connect (15 minutes)

Replace [customers] with the word captured in Phase 2 (the "What we call the people we serve" line in `about-me/business.md`).

## Goal
Connect Gmail and Google Calendar so Claude can read them, set the CRM or `people/` folder as the source of [customer] context, and write `about-me/connections.md`.
Read-first everywhere. Sending stays off. The owner sends.

## Reads first
- `_gb/state.md`
- `about-me/business.md` (the daily-tools answer from Question 11 fills most of the buckets)
- `templates/connections.md`
- `about-me/memory.md`

## Steps
One bucket at a time. Pre-fill from business.md and confirm rather than ask from scratch. A bucket that is empty is a finding, not a failure; write it down and move on.

1. Open.
   > This part takes about 15 minutes. First I'll ask which tools you use, then we'll connect your email and calendar so I can read them. I won't send anything; that stays with you.

2. Bucket 1 — Email.
   > Bucket 1 — Email: what do you use? If nothing, say **none**.

3. Bucket 2 — Calendar.
   > Bucket 2 — Calendar: what do you use? If nothing, say **none**.

4. Bucket 3 — Customers and leads.
   > Bucket 3 — [Customers] and leads: where do their names, numbers, and history live? The Growth Booster CRM, a spreadsheet, your phone, nowhere? If nothing, say **none**.

5. Bucket 4 — Files and documents.
   > Bucket 4 — Files and documents: Google Drive, Dropbox, a folder on your computer, or **none**?

6. Bucket 5 — Phone and messages.
   > Bucket 5 — Phone and messages: where do calls and texts with [customers] live? The CRM, your cell, a phone system, or **nowhere yet**?

   "Nowhere yet" is common. Say so:
   > That's normal, and it's the gap the daily brief and follow-ups help close. Noted.

7. Connect Gmail, one step at a time; wait for **done** after each.
   > Step 1: In Cowork, open Settings, then Connectors. Say **done**.

   > Step 2: Find Gmail and click Add. Say **done**.

   > Step 3: Sign in with the Google account you use for the business, and click Allow. Say **done**.

   Then set permissions, in plain English. Describe each by what it does, not by a button name:
   > Now the rules for what I can do in your email. Here's the default I recommend:
   > - Reading and searching your email: automatic, no asking.
   > - Writing a draft: I ask first.
   > - Sending: off. You send.
   > - Deleting: off.
   > Type **go** to keep these, or tell me what to change.

   Test read:
   > Let's prove it works. Type this in a new task: **List my 5 most recent unread emails, read-only.**

   Pass: five real subjects come back. Fail: an error or "not connected"; redo the sign-in and test again. Record `live: yes` or `live: no`; a connection counts only when a read returns data.

8. Connect Google Calendar, same pattern.
   > Same three steps for Google Calendar: Settings, Connectors, add Google Calendar, sign in, Allow. Say **done** when it's added.

   > Rules for the calendar: reading is automatic; adding or changing an event, I ask first; deleting is off. Type **go** or tell me what to change.

   Test read:
   > In a new task, type: **What's on my calendar today and tomorrow?**

   Pass: real events (or an honest "nothing scheduled"). Record `live: yes/no`.

9. CRM or `people/` folder.
   If the client is a Growth Booster CRM client:
   > Connecting the CRM is Barak's step. Barak handles this step; if he's not here, mark it 'next call'.

   If Barak is present, let him connect it, then test with a read-only lookup of one [customer] by name. Record the result. If he is not here, write `crm: next call` in connections.md and add it to Open loops.

   If the client is not on the CRM:
   > For [customer] context, I'll use a folder called `people/`: one short note per [customer] when you want me to know something about them. I'll create it empty now. Type **go**.

   Create `<workspace>/people/` empty. Skills read it when a note exists and ignore it otherwise.

10. Reality check on scheduled tasks. Say it once:
    > One thing to know before the next phase: scheduled tasks run when Cowork is open, or in the cloud when the task is set up that way. Barak decides which on the call.

11. Write `about-me/connections.md` from `templates/connections.md`: the five buckets with the owner's answer for each, what is connected and `live: yes/no`, the permission rules in the plain-English form above, and a short "still missing" list. Show it. Gate:
    > Here's your connections file. Type **looks good** or **change [what]**.

    Save it.

## Files written
- `<workspace>/about-me/connections.md`
- `<workspace>/people/` (created empty when not on the CRM)
- `<workspace>/_gb/state.md`
- `<workspace>/about-me/memory.md`

## Verify in a fresh task
> Open a brand-new task and type exactly this: **Which tools can you reach right now, and what are you allowed to do in each?**

Pass: it names Gmail and Calendar as live (when they are), says sending is off, and names what is still missing. Fail: it guesses. Check connections.md saved under `about-me/`, rerun the test reads, verify again.

## Close-out
1. Update `_gb/state.md`: phase 4 `status: complete` (or `skipped` if neither tool could be connected today), `completed: <today>`, `next_phase: 5`, `last_session: <today>`.
2. Append one entry to `about-me/memory.md`:
   ```
   ### YYYY-MM-DD — Phase 4 tools connected
   - What we did: five buckets answered; Gmail live [yes/no]; Calendar live [yes/no]; CRM [connected / next call / not a CRM client, people/ created]
   - Files touched: about-me/connections.md, people/, _gb/state.md
   - Decisions the owner made: [permission rules kept or changed — quote them]
   - Open loops: [CRM next call; buckets marked none or nowhere yet]
   - Next time: Phase 5 — routines
   ```
3. Say:
   > Phase 4 done. Continue to Phase 5 — routines, or pause? (Type **continue** or **pause**.)
