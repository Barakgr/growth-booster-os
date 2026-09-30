---
name: sb-file
description: Captures a note into the Growth Booster Second Brain inbox in the owner's own words, or builds one wiki page on a topic right now instead of waiting for the weekly update. Trigger when the owner says "file this note", "add to my second brain", "remember this in my vault", "save this to my vault", "file this in [vault name]", "build a page about", "make a wiki page for", "write up what we know about", or types /sb-file.
---

# sb-file — capture a note, or build a page now

## Find the vault (every time)

1. Read `_sb/state.md`. Use the vault with `default: true`, unless the owner named another vault ("file this in Personal: …"). For `on-top` vaults, the vault root is `<path>/<area>/`; otherwise it's `<path>/`.
2. If `_sb/state.md` doesn't exist but `_gb/state.md` has a `vault:` section, use that path, mode, and area.
3. If neither exists, say: "Your second brain isn't set up yet. Say **set up my second brain** and it takes about 40 minutes." Stop.
4. Read the basics file named in state (`about-me/business.md` or `_sb/basics.md`) for the customer word and business facts.

## file ("file this note: …")

1. Save the note to `inbox/YYYY-MM-DD-short-title.md` in the owner's exact words. Title: three to six words from the note, lowercase, hyphens. If a file with that name exists, add `-2`.
2. If the owner pasted a link or a long clip, save it as-is with a first line `Source: <link>`.
3. Confirm in one line: "Filed: *price change for drain cleaning*."
4. If the note clearly corrects a wiki page, say so and ask: "This changes **services-and-prices**. Update that page now, or leave it for [update day]? (**now** / **later**)". On **now**, update that page with the **build** rules below (show the change first).

In an **as-is** vault there's no inbox: ask which file or folder to save it to, once, and remember the answer in the owner's `claude.md` block ("Put new notes in …").

## build ("build a page about X")

1. Check `_index.md`. If a page on X already exists, say so and offer to update it instead.
2. Search `inbox/`, `wiki/`, and the basics file for everything on X. List what you found in one line: "3 notes and your business file mention warranties."
3. Ask up to three short questions, one at a time, only for gaps that matter. If the owner says **skip**, leave the gap marked `(not known yet)`. Never fill it in yourself.
4. Save the owner's answers from step 3 as a new inbox note first, so the page has a source.
5. Draft `wiki/<topic-in-kebab-case>.md`:
   ```
   # <Topic>
   <One-line summary.>

   ## <Short section>
   …

   Related: [[other-page]], [[another-page]]
   Sources: [[2026-09-28-price-change]], [[2026-09-29-warranty-answers]]
   ```
   Short sections, plain words, the owner's customer word. Every fact must come from a listed source.
6. Show the whole page before saving. On **looks good**, save it, add it to `_index.md` with a one-line description, update `_hot.md` if it changes what matters most (keep it under 300 words), and add one dated line to `_log.md`.

## Rules

- Never rewrite or delete what the owner wrote in `inbox/`. File and link.
- Write only to `inbox/`, `wiki/`, `_index.md`, `_hot.md`, and `_log.md` (in **as-is** mode, only where the owner says). Never touch `.obsidian/`.
- Never delete a note. Anything the owner wants gone moves to `_review/` in the workspace; say so.
- Never invent facts, prices, or customer details.
