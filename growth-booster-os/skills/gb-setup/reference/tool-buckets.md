# The five tool buckets

Phase 4 of setup walks these in order. Each bucket gets one block in `about-me/connections.md`. A bucket counts as connected only when a real read comes back with data; a sign-in that returns nothing is "not yet".

Permission defaults, in plain English, for every bucket: **reading is automatic** (Claude looks without asking), **drafting and creating ask first** (Claude shows you before it saves anything new), **sending is off** (Claude drafts, you send), **deleting is off** (anything you ask to delete moves to `_review/` instead). Change these only on purpose, and write the date next to the change.

## 1. Email

**What it is:** the inbox where leads, quotes, invoices, and complaints land.

**Common tools:** Gmail (must-have for this setup). Outlook works too but takes a separate call.

**Once it's connected, Claude can:**
- Tell you which leads emailed yesterday and got no reply.
- Pull the urgent emails into the daily brief and skip the newsletters.
- Draft a reply in your voice and save it as a draft you send with one tap.
- Find the last thing you said to a customer before you call them back.

**The scripted question:**
> "Which email do you actually read every day? That's the one we connect. Type the address, or **skip**."

**Permissions:** reading automatic / drafting ask-first / sending off / deleting off.

## 2. Calendar

**What it is:** where jobs, visits, and meetings live.

**Common tools:** Google Calendar (must-have). If the CRM has its own calendar, it usually syncs here.

**Once it's connected, Claude can:**
- Put today's and tomorrow's jobs at the top of the brief with times and addresses.
- Flag a job with no address, or two jobs 40 minutes apart booked back to back.
- Draft an appointment confirmation with the right time in it.
- Tell you which day has room when a customer asks.

**The scripted question:**
> "Is your work schedule on Google Calendar? Type **yes**, or tell me where it lives."

**Permissions:** reading automatic / creating events ask-first / deleting off.

## 3. Customers & leads

**What it is:** the list of everyone who has called, texted, or bought. Where a lead's status lives.

**Common tools:** the Growth Booster CRM. If the client isn't on it: a `people/` folder in the workspace with one note per contact, or "none yet".

**Once it's connected, Claude can:**
- List leads that came in this week with no follow-up.
- Pull a customer's history before drafting a follow-up so it doesn't ask what you already know.
- Spot quotes that went quiet for more than a week.
- Draft the SMS and email pair for `/gb-followup` with the real name, job, and date in it.

**The scripted question:**
> "Where does a lead's name go after the first call? The CRM, a notebook, a spreadsheet, or nowhere? Just tell me which."

**Permissions:** reading automatic / adding notes ask-first / sending off / deleting off.

## 4. Files & documents

**What it is:** quotes, invoices, photos, price sheets, the spreadsheet nobody admits to.

**Common tools:** Google Drive, Dropbox, or a folder on the computer.

**Once it's connected, Claude can:**
- Find the last quote you sent a customer and reuse the numbers.
- Read your price sheet so drafts never quote the wrong figure.
- Save its own outputs next to your files instead of somewhere you'll never look.

**The scripted question:**
> "Where do your quotes and price sheets live? Google Drive, Dropbox, or a folder on this computer? Type which one, or **skip**."

**Permissions:** reading automatic / creating files ask-first / deleting off.

## 5. Phone & messages

**What it is:** where calls and texts with customers actually happen. Missed calls, voicemails, text threads.

**Common tools:** the Growth Booster CRM (calls and texts run through it). Otherwise a phone app, a separate texting service, or "nowhere yet".

**Once it's connected, Claude can:**
- List yesterday's missed calls and which ones never got a text back.
- Draft the text back to an after-hours caller, ready for you to send at 7 AM.
- Include voicemail counts in the brief so you know the leak is there before it costs you.

**The scripted question:**
> "When someone calls after hours, where does that call go, and can you see it the next morning? Tell me what happens today."

"Nowhere yet" is a finding, not a failure. Write it down in `connections.md` under "Still missing." It's usually the first thing worth fixing.

**Permissions:** reading automatic / drafting ask-first / sending off / deleting off.

## Growth Booster CRM

When the client is on the Growth Booster CRM, Barak connects it during Phase 4. Once it's live, it becomes the source for buckets 3 and 5 at once: leads, contacts, call log, text threads, and review requests all come from one place. The daily brief pulls leads and missed calls from it, `/gb-followup` reads the contact record before drafting, and review replies can be drafted against the real review text.

Permissions on the CRM match every other bucket: reading automatic, adding notes ask-first, sending off, deleting off. Claude never sends a text or an email from the CRM. It drafts; the owner presses send.

If the client is not on the CRM yet, write "people/ folder" or "none yet" in bucket 3 and "nowhere yet" in bucket 5, and note under "Still missing" that the CRM would fill both. That's the next call.
