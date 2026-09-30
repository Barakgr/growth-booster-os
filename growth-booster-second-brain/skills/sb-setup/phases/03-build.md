# Phase 3 — Build the vault (2 minutes)

Skip this phase (mark `skipped`, reason "connected as-is") for a vault in **as-is** mode. When **add another vault** runs, build only the new vault.

## Goal
The folder layout and the three top files exist in the vault.

## Reads first
- `_sb/state.md` (vault `path`, `mode`, `area`)
- The basics file named in state

## The layout

For `fresh`, build it at the vault `path`. For `on-top`, build it inside `<path>/<area>/`. Everywhere else in this plugin, "the vault root" means that folder.

```
inbox/          raw notes, clips, voice-memo transcripts. Claude files new notes here.
wiki/           one page per topic, written and kept current by Claude.
attachments/    images and PDFs Obsidian saves.
_index.md       every wiki page, with one line on what it covers.
_hot.md         the 10 to 20 facts that matter most right now, under 300 words. Claude reads this first.
_log.md         one dated line each time Claude changes the vault.
```

## Steps

1. Say: "Building your folders now. Nothing in your existing notes gets touched." (For `fresh` with no existing notes, drop the second sentence.)

2. Create the three folders. Never overwrite a file that already exists; if `_index.md`, `_hot.md`, or `_log.md` is already there, leave it and say so.

3. Write the top files:

   `_index.md`
   ```
   # Index
   Every page in the wiki, with one line on what it covers. Claude keeps this current.

   (no pages yet)
   ```

   `_hot.md`: the three most important facts from the basics file, each on its own line, plus a date line. Under 300 words, always.
   ```
   # Cheat sheet
   The facts that matter most right now. Claude reads this first.
   Updated: <today>

   - <fact 1>
   - <fact 2>
   - <fact 3>
   ```

   `_log.md`
   ```
   # Log
   - <today>: vault built by Growth Booster Second Brain setup.
   ```

4. Show the owner the folder list in one line: "Done: inbox, wiki, attachments, and three files (index, cheat sheet, log)."

5. Mark Phase 3 complete. Use the standard end line.
