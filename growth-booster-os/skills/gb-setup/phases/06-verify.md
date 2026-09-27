# Phase 6 — Verify (10 minutes)

Replace [customers] with the word captured in Phase 2 (the "What we call the people we serve" line in `about-me/business.md`).

## Goal
Run one live, end-to-end test that matters to an owner: does Claude know them, can it reach their day, can it draft a follow-up and a review reply in their voice.
Then record the baseline checkup score and mark setup complete.

## Reads first
- `_gb/state.md` (confirm phases 1–5 are `complete` or `skipped`; if any is `pending`, go back to it first)
- `claude.md`, `about-me/business.md`, `about-me/voice.md`, `about-me/connections.md`, `about-me/brief-preferences.md`
- `about-me/memory.md`

## Steps
This phase is a test, not an interview. Say what each test is for in one line, run it, ask one yes/no question, move on. Report failures honestly; never smooth one over.

1. Open.
   > Last part, about 10 minutes. We'll test the whole thing the way you'll actually use it, then I'll give you a baseline score.

2. Test A — identity, in a fresh task.
   > Open a brand-new task and type exactly this: **Tell me in three sentences who I am, what I sell, and how I write.**
   > Then answer me one thing: does this sound like you? (**yes** or **no**)

   Pass: yes. Fail: no; note which part was off (who, what, or how). Maps back to Phase 2 (who/what) or Phase 3 (how).

3. Test B — reaching the day. Run this yourself in the current task, read-only.
   > Now I'll pull today's calendar and your three most urgent unread emails. Reading only.

   Show a short list: today's events, then three emails with sender and subject and one line on why each is urgent. Do not draft anything. Ask:
   > Is that your real day? (**yes** or **no**)

   Pass: real events and real emails. Fail: an error or empty results when the owner knows there is mail. Maps back to Phase 4.

4. Test C1 — a lead follow-up. Use a real situation if the owner has one; otherwise use this one, adapted to their business:
   > Let's test a follow-up. Give me a real one, or I'll use this: a [customer] called at 6:10 PM last night and got voicemail. Type a situation or **use that**.

   Run `/gb-followup` on it. Show the text and email pair plus the timing sequence. Confirm nothing was sent. Ask:
   > Would you send that, as-is or with a small edit? (**yes** or **no**)

   Pass: yes. Fail: it sounds wrong or promises something the owner cannot promise. Maps back to Phase 3 (voice) or Phase 2 (off-limits list).

5. Test C2 — a review reply. Use a real review if they have one open; otherwise:
   > One more. Paste a real review you've received, or type **make one up** and I'll invent a plain 4-star review to reply to.

   If you invent a review, say so, and never save it as if it were real. Run `/gb-write` for the reply. Ask:
   > Would you post that? (**yes** or **no**)

6. Honest self-report. One line per test, pass or fail. For each fail, name the phase to redo and the one thing to fix:
   > Here's where we landed:
   > - A. Knows you: [pass/fail]
   > - B. Reaches your day: [pass/fail]
   > - C1. Lead follow-up: [pass/fail]
   > - C2. Review reply: [pass/fail]
   > [For each fail:] That one traces back to Phase [N]. The fix is [one sentence]. We can redo it now or on the next call. Type **now** or **next call**.

   If **now**, run that phase's file, then come back here and rerun only the failed test. If **next call**, write it under Open loops.

7. Baseline score. Run `/gb-checkup` in full. Read the total, the band, and the one recommended fix aloud. Before the number, set expectations:
   > This score is the starting line, not a grade. Most owners land in Patched or Working on day one; the weekly checkup moves it up.

   Write `baseline_score: <total>` into phase 6 of `_gb/state.md`.

8. Mark setup complete. Set `setup_complete: true` in `_gb/state.md`.

9. Closing words. Say it in plain English, no ceremony:
   > That's the setup. I know your business, I write like you, I can read your email and calendar, and every morning at [fire time] there's a brief waiting. Two things to try tomorrow:
   > 1. Say **daily brief** and read what comes back.
   > 2. Say **follow up with [name]** about any [customer] who's gone quiet.
   > When something feels off, say **check my setup** and I'll tell you what to fix.

   Do not recommend other plugins, tools, or add-ons. The next improvement comes from the weekly checkup, not from installing more.

## Files written
- `<workspace>/_gb/state.md` (`baseline_score`, `setup_complete: true`, phase 6 status)
- `<workspace>/about-me/memory.md`
- `<workspace>/outputs/followups/` and `<workspace>/outputs/writing/` (from the C tests, if the drafts ran over 200 words)

## Verify in a fresh task
The tests above are the verification. One last check after close-out:
> Open a brand-new task and type exactly this: **Where am I in setup?**

Pass: it says setup is complete and gives the baseline score. Fail: check that `_gb/state.md` saved.

## Close-out
1. Update `_gb/state.md`: phase 6 `status: complete`, `completed: <today>`, `baseline_score: <total>`, `setup_complete: true`, `next_phase: null`, `last_session: <today>`.
2. Append the final setup entry to `about-me/memory.md`:
   ```
   ### YYYY-MM-DD — Setup complete, baseline score [total] ([band])
   - What we did: four live tests (identity, calendar and inbox, lead follow-up, review reply); ran the first checkup; marked setup complete
   - Files touched: _gb/state.md, outputs/followups/, outputs/writing/
   - Decisions the owner made: [which drafts they'd send as-is; anything they changed — quote them]
   - Open loops: [failed tests deferred to next call; CRM if still 'next call'; third routine if named]
   - Next time: read the first real daily brief together; run the weekly checkup and take its one fix
   ```
3. Say:
   > Phase 6 done. Setup is complete. There's nothing to continue to; the weekly checkup takes it from here. (Type **pause** to close, or **check my setup** any time.)
