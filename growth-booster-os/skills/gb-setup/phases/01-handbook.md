# Phase 1 — Handbook (10 minutes)

## Goal
Write `claude.md`, the short handbook that tells Claude who the owner is and how to behave, and get it pasted into Cowork's Global instructions.
This is the one file Claude reads on every message, so keep it short and make every line earn its place.

## Reads first
- `_gb/state.md` (create it from `state.md` in this skill folder if it does not exist; set `started` to today and `operator_present` after Step 1)
- `templates/claude-md.md`
- `about-me/memory.md` if it exists (skip if this is the first session)

## Steps
Ask one question at a time. Wait for the answer before the next one. If the owner hesitates for more than a few seconds, ask "what's making you hesitate?" and simplify.

1. Open with the operator check.
   > Before we start: is Barak or someone from Growth Booster on this call with you? (yes/no)

   Set `operator_present` in `_gb/state.md` to `true` or `false`. If yes, Barak may answer for the owner, but still say each question aloud so the owner hears it.

2. Set expectations in two lines.
   > This first part takes about 10 minutes. I'll ask four questions, then write a short handbook that tells me how to work with you.

3. Question 1 — who they are.
   > What's your name, your business name, your role, and one sentence on what the business does?

4. Question 2 — how they want Claude to talk to them.
   > How do you want me to talk to you? Tone, how long my answers should be, and two things AI tools do that annoy you.

5. Question 3 — the never list.
   > Three things I should never do. Anything at all.

6. Question 4 — the ask-first list.
   > Is there anything I must never send, post, or change without asking you first?

   If they say "everything", write it that way. That is a fine answer.

7. Generate `claude.md` from `templates/claude-md.md`. Fill every `~~` placeholder from the four answers. Bake in the safety defaults (read without asking; ask before creating or changing; never send; never delete, move to `_review/` instead). Include the on-demand identity line, in these words or close to them:
   > The folder `about-me/` holds my business, my voice, my tools, and my session memory. Load those files when a skill needs them, not on every message.

   Show the finished handbook as a code block. Then gate:
   > Read it over. Type **looks good** or **change [what]**.

   Iterate until they type **looks good**. Save to `<workspace>/claude.md`.

8. Walk them through the paste, one step at a time, waiting for "done" after each.
   > Step 1: Copy the whole code block above. Say **done** when you have it.

   > Step 2: In Cowork, open Settings, then Global instructions. Say **done** when you see the text box.

   > Step 3: Paste it in and save. Say **done**.

   If they already have text in Global instructions, ask before replacing it:
   > There's already something in there. Should I keep it above my handbook, or replace it? (Type **keep** or **replace**.)

## Files written
- `<workspace>/claude.md`
- `<workspace>/_gb/state.md` (created if missing; `operator_present`, `started`, phase 1 status)
- `<workspace>/about-me/` and `<workspace>/outputs/`, `projects/`, `_review/` created empty if missing

## Verify in a fresh task
> Open a brand-new task in Cowork and type exactly this: **Summarize how I want you to work with me.**
> Paste what it says back here, or just tell me whether it sounded right.

Pass: the answer names the owner, the tone they asked for, and at least one item from the never list. Fail: it answers generically. If it fails, the paste did not stick. Redo Step 8 and verify again. Do not move on until it passes.

## Close-out
1. Update `_gb/state.md`: phase 1 `status: complete`, `completed: <today>`, `next_phase: 2`, `last_session: <today>`.
2. Append one entry to `about-me/memory.md` (create the file if missing):
   ```
   ### YYYY-MM-DD — Phase 1 handbook written and pasted
   - What we did: wrote claude.md from four answers; pasted into Global instructions; verified in a fresh task
   - Files touched: claude.md, _gb/state.md
   - Decisions the owner made: [tone, never list, ask-first list — quote the owner]
   - Open loops: [anything they wanted to change later]
   - Next time: Phase 2 — business
   ```
3. Say:
   > Phase 1 done. Continue to Phase 2 — business, or pause? (Type **continue** or **pause**.)
