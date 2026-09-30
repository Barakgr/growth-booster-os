# Phase 0 — Welcome (3 minutes)

## Goal
Explain the second brain in the owner's terms, find out whether Growth Booster OS is already set up, and make sure Claude knows the three or four business basics the vault needs.

## Reads first
- `_sb/state.md`
- `claude.md` and `about-me/business.md`, if they exist

## Steps

1. **Check for Growth Booster OS.** If both `claude.md` and `about-me/business.md` exist, set `uses_gb_os: true`, `basics_file: about-me/business.md`, and copy the customer word from its "What we call the people we serve" line (or the closest equivalent) into `customer_word`. Skip to step 3.

2. **No Growth Booster OS.** Set `uses_gb_os: false` and `basics_file: _sb/basics.md`. Say:
   > "Before we build it, I need four quick facts so your second brain is about *your* business. One at a time."

   Ask, one at a time, waiting for each answer:
   1. "What's the business called, and what do you do, in one sentence?"
   2. "What do you call the people you serve: customers, clients, patients, homeowners, something else?"
   3. "What are the two or three things you get asked about most?"
   4. "Anything that changes often and you'd want me to always have right? Prices, service area, hours, current offers. Say **skip** if nothing comes to mind."

   Write `_sb/basics.md`:
   ```
   # Business basics
   Business: <answer 1>
   What we call the people we serve: <answer 2>
   Asked about most: <answer 3>
   Keep current: <answer 4, or (not known yet)>
   Last updated: <today>
   ```
   Set `customer_word` from answer 2. Use the owner's exact words. Don't polish them.

3. **Explain it in three sentences, using their business.** Example for a plumber:
   > "Your second brain is a folder of notes that I keep organized for you. Whenever something comes up (a [customer]'s odd request, a price change, how a tricky job got solved) you tell me or jot it down, and once a week I fold it into a small wiki: one clean page per topic. Then when you or I need the answer, it's there, in your words."

4. **Say what's ahead.**
   > "Here's the plan: we pick where the notes live, you install Obsidian (free), I build the folders, we test that I can read and write them, set a few settings, make your first two pages together, and set up a weekly sort. About 40 minutes. Nothing gets deleted, ever."

5. Mark Phase 0 complete. Use the standard end line.
