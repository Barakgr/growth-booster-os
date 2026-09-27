# Phase 3 — Voice (15 minutes)

Replace [customers] with the word captured in Phase 2 (the "What we call the people we serve" line in `about-me/business.md`).

## Goal
Write `about-me/voice.md`: how the owner actually writes, what they refuse to sound like, real samples, and the kill list.
Every draft `/gb-write`, `/gb-followup`, and `/gb-brief` produces is checked against this file before the owner sees it.

## Reads first
- `_gb/state.md`
- `about-me/business.md` (for the customer word and the off-limits list)
- `templates/voice.md`
- `reference/kill-list.md`
- `about-me/memory.md`

## Steps
One question at a time. The samples matter more than the answers; if the owner has to choose between the two, take the samples.

1. Open and check for samples.
   > This part takes about 15 minutes and teaches me to write like you, not like a robot. Do you have 3 to 5 real things you've written to [customers] handy? Texts, emails, a review reply, a Facebook post. Type **yes** or **not yet**.

   If **not yet**: ask them to open their phone or inbox now and grab three. Wait. Do not proceed without at least three real samples; if they truly cannot find any, proceed with what they have and note it under Open loops (fewer than three samples caps the Know score).

2. Question 1 — voice in one sentence.
   > Describe how you sound when you write to a [customer], in one sentence.

3. Question 2 — do and do-not words.
   > Give me 3 to 5 words for how you DO sound, and 3 to 5 for how you do NOT sound.

4. Question 3 — phrases and refused words.
   > What phrases do you say all the time? And what words do you refuse to use?

   Add the refused words to voice.md Part 1 under the owner's banned words. Merge in the off-limits list from business.md.

5. Question 4 — formatting habits.
   > Formatting habits: exclamation points, yes or no? How do you sign off? Emoji ever? Long sentences or short ones?

6. Question 5 — what bugs them about AI writing.
   > What bugs you about AI-written stuff? Be specific if you can.

7. Collect the samples.
   > Paste your samples now, one at a time or all at once. Tell me what each one was: a text, an email, a review reply, a post.

   Store each sample verbatim under "Samples" in voice.md Part 1, labeled by type and where it was sent. Do not clean them up. Typos and all; that is the voice.

8. Build `about-me/voice.md` from `templates/voice.md`:
   - Part 1: the five answers, the owner's banned words merged with the off-limits list from business.md, and the samples verbatim. Under "Formatting habits", add one or two things you noticed in the samples that they did not mention (sentence length, greeting pattern). Say they are observations so the owner can strike them.
   - Part 2: copy `reference/kill-list.md` in verbatim. Do not edit, shorten, or reorder it.
   - Part 3: exceptions. Ask once: "Any time it's fine to break these rules? A holiday post, echoing a [customer]'s own words?" Fill it, or leave the two lines empty if they say none.

   Show the whole file as a code block. Gate:
   > Here's your voice file. Part 2 is a standard list of words I'll never use; your rules in Part 1 win over it. Type **looks good** or **change [what]**.

   Iterate until they type **looks good**. Save it.

## Files written
- `<workspace>/about-me/voice.md`
- `<workspace>/_gb/state.md`
- `<workspace>/about-me/memory.md`

## Verify in a fresh task
> Open a brand-new task and type exactly this: **Write a two-sentence text to a customer confirming tomorrow's 9 AM appointment, in my voice.**
> Paste the result here, or tell me: does that sound like you?

Pass: two sentences, the owner's sign-off if they have one, none of their refused words, nothing from the kill list, and the owner says "yes, that's me" or close to it. Fail: it sounds like a form letter. If it fails, check that voice.md saved under `about-me/` and that Part 1 has real samples. Fix, then verify again.

## Close-out
1. Update `_gb/state.md`: phase 3 `status: complete`, `completed: <today>`, `next_phase: 4`, `last_session: <today>`.
2. Append one entry to `about-me/memory.md`:
   ```
   ### YYYY-MM-DD — Phase 3 voice file written
   - What we did: five voice questions; [N] real samples collected; wrote about-me/voice.md with the kill list; verified with a test text
   - Files touched: about-me/voice.md, _gb/state.md
   - Decisions the owner made: [refused words; sign-off; exclamation-point rule — quote them]
   - Open loops: [fewer than 3 samples if so; anything they wanted to add later]
   - Next time: Phase 4 — connect
   ```
3. Say:
   > Phase 3 done. Continue to Phase 4 — connect, or pause? (Type **continue** or **pause**.)
