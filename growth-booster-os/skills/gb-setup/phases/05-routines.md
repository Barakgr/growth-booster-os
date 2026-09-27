# Phase 5 — Routines (10 minutes)

Replace [customers] with the word captured in Phase 2 (the "What we call the people we serve" line in `about-me/business.md`).

## Goal
Write `about-me/brief-preferences.md` and set up two scheduled tasks: the daily brief and the weekly checkup.
After this phase the system works without the owner starting it.

## Reads first
- `_gb/state.md`
- `about-me/connections.md` (which tools are live decides what the brief can include)
- `templates/brief-preferences.md`
- `about-me/memory.md`

## Steps
One question at a time. Defaults are given in each question; the owner only has to speak up to change one.

1. Open.
   > About 10 minutes. Six quick questions about your daily brief, then we set two scheduled tasks so it runs on its own.

2. Question 1 — fire time.
   > What time on weekdays should the brief be ready? Default is 7:00 AM. Type a time or **default**.

3. Question 2 — weekends.
   > Weekends too? Default is no. Type **yes** or **no**.

4. Question 3 — always-matter senders.
   > Which senders always matter, no matter what? Names or email addresses. [Customers], a key supplier, your bookkeeper, your spouse.

5. Question 4 — never-matter senders.
   > Which senders never matter for the brief? Newsletters, notifications, anything I should skip.

6. Question 5 — never-draft topics.
   > What should I never draft a reply to, even as a draft? Default: pricing, complaints, anything legal. Type **default** or add to the list.

7. Question 6 — length.
   > How long should the brief be? Default is under 300 words: one screen on your phone. Type **default** or a number.

8. Write `about-me/brief-preferences.md` from `templates/brief-preferences.md` with the six answers. Fill the two sections you did not ask about with defaults: Calendar rules (show 2 days; flag events with no address; ignore nothing) and Leads & follow-ups (take "CRM", "people/", or "none" from connections.md Bucket 3; a lead counts as waiting after 2 hours). Time zone: the owner's, from business.md. Show it, defaults included, so the owner can change any line. Gate:
   > Here's your brief rules file. Type **looks good** or **change [what]**.

   Save it.

9. Create the daily brief scheduled task, one step at a time; wait for **done** after each. Barak decides on the call whether it runs while Cowork is open or in the cloud; follow his call.
   > Step 1: In Cowork, open Scheduled tasks and click New. Say **done**.

   > Step 2: Name it **Daily brief**. Set it to run every weekday at [fire time] (add weekends if you said yes). Say **done**.

   > Step 3: Paste this exactly as the task's instructions, then save. Say **done**.

   ```
   Run /gb-brief. Read about-me/ for context and voice. Save the brief to outputs/daily-brief/YYYY-MM-DD-brief.md. Draft replies only where brief-preferences.md allows. Do not send anything. Append one entry to about-me/memory.md. If nobody is here, do not ask questions — save and stop.
   ```

   Test-fire:
   > Step 4: Click **Run now** on the task. Wait for it to finish, then say **done**.

   Check `outputs/daily-brief/` for today's file. Open it and read it aloud in two lines. Pass: a real brief under the word limit, nothing sent. Fail: no file, or it asked a question and stopped. Fix the task's instructions or the connection it needed, then run again.

10. Create the weekly checkup scheduled task, same pattern.
    > Same steps for the second one. Name it **Weekly checkup**. Set it to run once a week; Monday at 8:00 AM works for most people. Paste this as the instructions and save. Say **done**.

    ```
    Run /gb-checkup. Score the setup, write the result to about-me/memory.md, and propose one fix. If nobody is here to approve, save the proposal and stop — I'll say 'continue checkup' when I'm back.
    ```

    Test-fire:
    > Click **Run now**, wait for it to finish, then say **done**.

    Check `about-me/memory.md` for a new checkup entry with a score. Pass: a score and one proposed fix. The score will be low right now; say so before they see it:
    > The first score is always low because we haven't used anything yet. Phase 6 sets the real baseline.

11. Optional third routine. Ask once, no pressure:
    > Is there one more thing you'd want done on a schedule? A Friday review-request list, a Monday look at quiet quotes? Type it, or **skip**.

    If they name one, write it under Open loops for a later session. Do not build it today.

## Files written
- `<workspace>/about-me/brief-preferences.md`
- `<workspace>/outputs/daily-brief/YYYY-MM-DD-brief.md` (from the test run)
- `<workspace>/_gb/state.md`
- `<workspace>/about-me/memory.md` (entries from both test runs plus the close-out entry)

## Verify in a fresh task
> Open a brand-new task and type exactly this: **Read my brief preferences and tell me what time my brief runs, who always matters, and what you'll never draft a reply to.**

Pass: it reads back the six answers correctly. Fail: it guesses or cannot find the file. Check it saved under `about-me/`, fix, verify again.

## Close-out
1. Update `_gb/state.md`: phase 5 `status: complete`, `completed: <today>`, `next_phase: 6`, `last_session: <today>`.
2. Append one entry to `about-me/memory.md`:
   ```
   ### YYYY-MM-DD — Phase 5 routines scheduled
   - What we did: wrote about-me/brief-preferences.md; created Daily brief ([time], [weekdays/every day]) and Weekly checkup ([day/time]); test-fired both
   - Files touched: about-me/brief-preferences.md, outputs/daily-brief/, _gb/state.md
   - Decisions the owner made: [fire time; never-draft list; runs while Cowork is open or in the cloud — Barak's call]
   - Open loops: [third routine they named; any test-fire that failed]
   - Next time: Phase 6 — verify
   ```
3. Say:
   > Phase 5 done. Continue to Phase 6 — verify, or pause? (Type **continue** or **pause**.)
