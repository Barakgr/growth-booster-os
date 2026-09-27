# Phase 2 — Business (20 minutes)

## Goal
Write `about-me/business.md`: what the business does, who it serves, how leads arrive and where they leak, who is on the team, and what tools they live in.
This is the file every other skill reads before it drafts anything, so it has to be true, not polished.

## Reads first
- `_gb/state.md`
- `claude.md`
- `templates/business.md`
- `samples/business-sample.md` (only if the owner asks for the example)
- `about-me/memory.md`

## Steps
One question at a time. Short answers are fine. If an answer is thin, ask one follow-up, then move on. Never invent details to fill a gap; leave the `~~` placeholder and note it as an open loop.

1. Open and offer the example.
   > This part takes about 20 minutes and builds the file I read before I draft anything for you. Want to see a filled-in example first? Type **example** or **start**.

   If **example**: paste `samples/business-sample.md` in full, then say:
   > That's a made-up HVAC company. Yours will look like this but with your answers. Type **start** when ready.

2. Question 1 — what the business does.
   > Explain what your business does the way you'd tell a smart friend who's never heard of it.

3. Question 2 — the customer word. This matters: the word they give is used everywhere from now on.
   > What do you call the people you serve? Customers, patients, clients, members, homeowners, something else? One word.

   Fill `~~customer-word` and `~~customer-word-plural` in business.md with it. Use it in every question and file from here on, in this phase and in Phases 3–6.

4. Question 3 — services and prices.
   > What do you sell or do for them, and roughly what does each thing cost? Ranges are fine.

5. Question 4 — service area.
   > Where are your [customers]? A city, a radius, a region, online, everywhere?

6. Question 5 — the ideal customer and the trigger.
   > Who's your ideal [customer], and what's usually going on in their life the moment they decide to call you NOW?

7. Question 6 — pains in their words.
   > What are the top three things a [customer] complains about or worries about, in the words they actually use?

8. Question 7 — how leads arrive.
   > How do new leads reach you? Phone, website form, referral, walk-in, a platform like Google or Facebook? And roughly how many a week?

9. Question 8 — what happens next. This is where most businesses leak; listen closely and write down exactly what they say.
   > When a lead comes in, what happens? Who answers, how fast, and what happens if nobody can?

10. Question 9 — reviews.
    > How do you ask for reviews today? Be honest; "when I remember" is a real answer.

11. Question 10 — the team.
    > Who's on the team, and what does each person handle?

12. Question 11 — daily tools.
    > What tools or apps do you open every day to run the business?

13. Question 12 — off-limits.
    > Anything I should never say or promise on your behalf? Things you can't guarantee, topics you stay away from, words you hate.

14. Draft `about-me/business.md` from `templates/business.md`. Fill every placeholder from the answers. Quote the owner where the wording matters (pains, the after-hours gap, the off-limits list). Show the whole file as a code block. Gate:
    > Here's your business file. Read it over. Type **looks good** or **change [what]**.

    Iterate until they type **looks good**. Save it. If any `~~` placeholder is still there, say so plainly and list it under Open loops in memory.

## Files written
- `<workspace>/about-me/business.md`
- `<workspace>/_gb/state.md`
- `<workspace>/about-me/memory.md`

## Verify in a fresh task
> Open a brand-new task and type exactly this: **Summarize who I am and what my business does in three sentences.**
> Tell me whether it got it right.

Pass: the three sentences name the business, use the owner's customer word, and mention at least one real service. Fail: it is generic, uses "customers" when the owner said something else, or makes something up. If it fails, check that `claude.md` points to `about-me/` and that the file saved to the right folder. Fix, then verify again.

## Close-out
1. Update `_gb/state.md`: phase 2 `status: complete`, `completed: <today>`, `next_phase: 3`, `last_session: <today>`.
2. Append one entry to `about-me/memory.md`:
   ```
   ### YYYY-MM-DD — Phase 2 business file written
   - What we did: twelve questions; wrote about-me/business.md; verified in a fresh task
   - Files touched: about-me/business.md, _gb/state.md
   - Decisions the owner made: customer word is "[word]"; [off-limits list; anything else they ruled on]
   - Open loops: [placeholders still empty; lead-handling gap they named]
   - Next time: Phase 3 — voice; owner to gather 3–5 real writing samples first
   ```
3. Say:
   > Phase 2 done. Continue to Phase 3 — voice, or pause? (Type **continue** or **pause**.)
   > Either way, before Phase 3, dig up 3 to 5 real things you've written to [customers]: texts, emails, a review reply, a Facebook post. Copy-and-paste is all we need.
