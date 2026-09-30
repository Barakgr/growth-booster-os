# Phase 4 — Connect Claude to the vault (5 minutes)

## Goal
Obsidian is open on the right folder, `claude.md` tells every future Claude session where the vault is and what it may touch, and two live tests prove Claude can read and write it.

## Reads first
- `_sb/state.md` (all vaults)
- `claude.md`, if it exists
- `reference/obsidian-guide.md`, sections "Open the vault" and "Wrong folder check"

## Steps

1. **Open the vault in Obsidian.** For a new vault, walk through "Open the vault" in the reference file one step at a time, waiting for **done** after each. For an existing vault, ask them to open it in Obsidian as usual and run the "Wrong folder check".

2. **Write the `## My second brain` block into `claude.md`.** If `claude.md` doesn't exist, create it with only this block. If the block already exists, replace just that block; leave everything else in the file alone.

   For a `fresh` or `on-top` vault (replace `<vault root>` with the real folder, relative to the workspace, e.g. `SecondBrain/` or `Notes/Business/`):
   ```
   ## My second brain
   My notes live in <vault root> inside this folder. When a question is about my business, my [customers], or how we do things, read <vault root>_hot.md first, then _index.md, then the wiki page you need.
   You may write only to <vault root>inbox/, <vault root>wiki/, and the _index, _hot, and _log files there. Never touch any .obsidian/ folder. Never delete a note; move it to _review/.
   Never rewrite my words in inbox/. File them and link them.
   The second brain commands come from the Growth Booster Second Brain plugin; its setup state is in _sb/state.md.
   ```

   For an `as-is` vault, replace the second and third lines with:
   ```
   You may read everything in it except .obsidian/. Write only to files I name. Never delete a note; move it to _review/.
   ```

   With more than one vault, list each on its own line under the heading ("Business: SecondBrain/ (default)", "Personal: SecondBrain-Personal/") and keep the rules once.

3. **Read test.** Read `_hot.md` (for `as-is`, the most recently changed note) and quote its first real line back. Ask:
   > "Is that from your vault? (Type **yes** or **no**.)"
   A **no** means Claude is pointed at the wrong folder. Stop, re-check the path with the owner, fix it in state and in `claude.md`, and run the test again. Record `read_test: passed` or `failed`.

4. **Write test.** Write `inbox/hello-from-claude.md` containing one line: "If you can read this in Obsidian, we're connected." (For `as-is`, ask the owner which folder to use for the test and write there.) Ask:
   > "Look at Obsidian's left sidebar. Do you see **hello-from-claude**? (yes / no)"
   Then move the file to `_review/` in the workspace and say so: "I moved the test note to _review. Nothing was deleted." Record `write_test: passed` or `failed`.

   On a **no**: most often Obsidian is showing a different folder. Run the "Wrong folder check" again, then retest.

5. Both tests must pass before this phase completes. If one keeps failing, mark the phase `in_progress`, say plainly what failed, and pause. Growth Booster can help on the next call.

6. Mark Phase 4 complete. Use the standard end line.
