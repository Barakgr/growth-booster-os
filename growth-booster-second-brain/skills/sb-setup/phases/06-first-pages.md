# Phase 6 — First notes and first pages (10 minutes)

## Goal
The owner sees the whole loop work once, live: messy notes go in, Claude builds clean wiki pages from them, and a first **update** runs. This phase is the owner's proof that the second brain is worth using.

In an **as-is** vault, ask the owner which file to use for the notes and which for the page, and write only there. Skip the `_index.md` / `_hot.md` steps unless the owner names equivalents.

## Reads first
- The basics file named in state
- The default vault's `_index.md` and `_hot.md`
- `../sb-file/SKILL.md` (the **file** and **build** rules) and `../sb-update/SKILL.md` (the **update** rules). Follow those rules exactly here.

## Steps

1. **Capture.** Say:
   > "Give me two or three messy notes, the way you'd jot them on a napkin. A [customer] question you answer all the time, a price, how you handle a tricky situation. Type or paste them one at a time."

   Save each as its own file, `inbox/YYYY-MM-DD-short-title.md`, in the owner's words, untouched. Confirm each in one line.

2. **Build two pages.** Pick the two pages that best fit the notes plus the basics file. Good first pages for a local business:
   - `wiki/services-and-prices.md`
   - `wiki/common-questions.md` (what [customers] ask, and the answers the owner actually gives)
   - `wiki/how-we-handle-<the most common tricky situation>.md`

   Build each with the **build** rules in `sb-file`: one-line summary on top, short sections, a `Related:` line, a `Sources:` line linking the notes (`[[2026-09-28-price-change]]`). Ask at most three gap questions per page. Mark anything unknown `(not known yet)`. Never fill a gap yourself.

   Show each page in full. Save it on **looks good**.

3. **Index and cheat sheet.** Add both pages to `_index.md`. Update `_hot.md` if the new pages change what matters most. Add one line to `_log.md`.

4. **One live update.** Ask the owner for one more note, something new since step 1. File it. Then say:
   > "This is what I'll do every week on my own. Watch."

   Run the **update** routine from `sb-update` with the owner present: show the short list of what changed before saving.

5. **Show them where to look.** Ask them to open `wiki/` in Obsidian's sidebar and click one of the new pages. Ask:
   > "See it? (yes / no)"

6. Mark Phase 6 complete. Use the standard end line.
