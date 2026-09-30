---
name: sb-update
description: The Growth Booster Second Brain weekly update — folds new inbox notes into the right wiki pages, keeps the index current, and rebuilds the cheat sheet (_hot.md). Runs unattended as the weekly scheduled task, or on demand with the owner watching. Trigger when the owner says "update my vault", "update my wiki", "sort my notes", "fold in my notes", "update my cheat sheet", "refresh hot", "refresh my cheat sheet", or types /sb-update.
---

# sb-update — weekly update and cheat sheet

## Find the vaults

1. Read `_sb/state.md`. The scheduled task updates **every** vault in `vaults:`. When the owner asks by hand, update the default vault unless they name another. For `on-top` vaults, the vault root is `<path>/<area>/`; otherwise it's `<path>/`.
2. If `_sb/state.md` doesn't exist but `_gb/state.md` has a `vault:` section, use that one vault.
3. If neither exists: when the owner is present, say "Your second brain isn't set up yet. Say **set up my second brain**." When running unattended, write that line to `outputs/second-brain/YYYY-MM-DD-update.md` and stop.
4. Skip any vault in **as-is** mode unless the owner named files to write to in `claude.md`; list it as skipped.
5. Read the basics file named in state.

## Unattended or present?

- **Unattended** (scheduled task, or the prompt says nobody is here): ask nothing. Make the changes, save, and write a short report to `outputs/second-brain/YYYY-MM-DD-update.md`: notes folded in, pages created or changed, cheat-sheet changes, anything skipped and why.
- **Owner present**: show a short list of what will change ("2 pages updated, 1 new page, cheat sheet: price for drain cleaning") and save on **go**.

## update (weekly)

For each vault:

1. Read `_hot.md`, `_index.md`, and the last entry in `_log.md`.
2. Find every note in `inbox/` added or changed since that last entry. If there are none, add a line to `_log.md` ("no new notes") and move on.
3. For each new note, decide where it belongs:
   - **Fits an existing page** → add the fact to that page in the right section and add the note to its `Sources:` line.
   - **Contradicts an existing page** → the newer note wins. Update the fact and add a line under the page's summary: `Changed <date>: was <old>, now <new> ([[note]])`.
   - **New topic with 2 or more notes** → create a page with the page shape from `sb-file` (summary, sections, `Related:`, `Sources:`).
   - **New topic with only 1 note** → leave it in the inbox for now. Don't create a page.
   - **Unclear** → leave it in the inbox and list it in the report.
4. Update `_index.md` for new pages.
5. Run **refresh hot** (below).
6. Add one dated line to `_log.md`: `- 2026-10-02: weekly update — 5 notes, 2 pages updated, 1 new page (warranty-policy).`

## refresh hot ("update my cheat sheet")

Rebuild `_hot.md` only.

1. Read `_index.md`, the wiki pages changed in the last 30 days, and the basics file.
2. Keep the 10 to 20 facts the owner would want Claude to know first: current prices, current offers, what changed recently, the rules that are easy to get wrong. Each fact links to its page. Under 300 words. Top line: `Updated: <date>`.
3. Owner present: show the new version next to the old one and save on **go**. Unattended: save it and list the changes in the report.

## Rules

- Never change, rename, move, or delete the notes in `inbox/`. Pages link to them; they stay as the owner wrote them.
- Write only to `wiki/`, `_index.md`, `_hot.md`, `_log.md`, and the report in `outputs/second-brain/`. Never touch `.obsidian/`.
- Never invent facts. A page only says what its sources say. Keep `(not known yet)` gaps as they are.
- Never delete a wiki page. A page that's no longer needed gets flagged in the report for the owner to decide.
