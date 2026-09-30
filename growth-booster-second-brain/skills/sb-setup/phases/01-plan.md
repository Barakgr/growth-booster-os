# Phase 1 — Plan (3 minutes)

## Goal
Decide where the vault lives, whether it's new or existing, how Claude treats an existing one, and whether the owner needs more than one vault. Record it all in `vaults:` in `_sb/state.md`.

## Reads first
- `_sb/state.md`
- `reference/obsidian-guide.md`, section "Copy a folder path"

## Steps

1. Ask:
   > "Do you already use Obsidian for notes? (Type **yes** or **no**.)"

2. **No →** the vault is new. Set the first vault to `name: Business`, `mode: fresh`, `path: <workspace>/SecondBrain`. Tell the owner in one line where it will live:
   > "Your notes will live in a folder called **SecondBrain** inside your Claude Cowork folder. That way I can always reach them."
   Go to step 5.

3. **Yes →** ask for the vault's full path and teach them to copy it (reference file, "Copy a folder path"). Don't try to detect it yourself. Obsidian's own settings live outside the workspace, so you usually can't see them, and that's normal.

   - **The path is outside the workspace** (it doesn't sit inside the Claude Cowork folder): say in one line that Claude can only reach what's inside the workspace, and offer the move:
     > "I can only reach folders inside your Claude Cowork folder. The fix takes two minutes: close Obsidian, then in Finder or File Explorer drag your whole vault folder into the Claude Cowork folder. Reopen it in Obsidian with **Open folder as vault**, then paste me the new path."
     The owner moves it. Claude never does. If they won't move it, say the second brain can't work from outside the workspace, mark Phase 1 `in_progress`, and pause.
   - **A path that sits *next to* the workspace** (like `/Users/name/SecondBrain` beside `/Users/name/Claude Cowork`) is also outside. Say so and ask again.

4. **Once the existing vault is inside**, offer three ways to work with it, one line each:
   > "How should I treat your existing notes?
   > 1. **Add folders on top** (best for most people): I add an inbox and a wiki inside one sub-folder you pick. Everything else stays untouched.
   > 2. **Connect as-is**: I read everything and write only to files you name. No folders added.
   > 3. **Start fresh**: for a vault with nothing worth keeping.
   > Type **1**, **2**, or **3**."

   - **1 →** `mode: on-top`. Ask which sub-folder should hold the inbox and wiki; suggest `Business`. Record it as `area`.
   - **2 →** `mode: as-is`.
   - **3 →** `mode: fresh`.

   Record `path` and `mode`. Name the vault after the folder unless the owner says otherwise.

5. **One vault or more.** Ask:
   > "Most owners need one vault, for the business. Some keep a second for personal stuff (home, family, health, hobbies) so it never mixes with work. One is plenty to start. Want just the one? (Type **one** or **two**.)"

   - **one →** go on.
   - **two →** run "Another vault" below, then go on.

6. Mark Phase 1 complete. If the owner said **yes** in step 1, also mark Phase 2 `skipped` ("already uses Obsidian"), but still run Phase 2's "Wrong folder check" at the start of Phase 4. If mode is `as-is`, mark Phase 3 `skipped` ("connected as-is") too. Use the standard end line, naming the next phase that isn't skipped.

## Another vault

Used here and by the **add another vault** command.

1. Ask for a short name ("Personal", "Side projects").
2. Default path: `<workspace>/SecondBrain-<Name>`. If the owner already has an Obsidian vault for it, use steps 3–4 above for that path instead.
3. Append a new entry to `vaults:` with `default: false`.
4. Say: "Whenever you don't name a vault, I'll use **[default vault name]**. To use the other, just say its name: 'file this in Personal: …'."
