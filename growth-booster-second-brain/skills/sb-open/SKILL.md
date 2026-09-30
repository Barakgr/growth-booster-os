---
name: sb-open
description: The owner's daily starter and lookup for Growth Booster Second Brain. Reports what's new in the Obsidian vault in five lines, and answers questions from the vault's wiki with the pages it used. Read-only. Trigger when the owner says "open my vault", "what's new in my vault", "start a vault session", "what does my second brain say about", "check my notes on", "look it up in my vault", or types /sb-open.
---

# sb-open — what's new, and look it up

Read-only. This skill never changes a file.

## Find the vault (every time)

1. Read `_sb/state.md`. Use the vault with `default: true`, unless the owner named another vault ("…in Personal"). For `on-top` vaults, the vault root is `<path>/<area>/`; otherwise it's `<path>/`.
2. If `_sb/state.md` doesn't exist but `_gb/state.md` has a `vault:` section, use that path, mode, and area.
3. If neither exists, say: "Your second brain isn't set up yet. Say **set up my second brain** and it takes about 40 minutes." Stop.
4. If `setup_complete` is false, do the task anyway if the vault folders exist, then add one line: "Setup isn't finished; say **continue second brain setup** when you're ready."

## open ("open my vault", "what's new in my vault")

Read `_log.md`, `_hot.md`, and the list of files in `inbox/`. Report in five lines or fewer:

1. How many inbox notes arrived since the last `_log.md` entry, with their titles.
2. When the last weekly update ran (the last update line in `_log.md`).
3. Any cheat-sheet fact dated more than 30 days ago that looks likely to change (a price, an offer), if there is one.
4. One suggestion: "3 new notes about pricing; say **update my vault** to fold them in now, or leave them for [update day]."
5. "Open Obsidian if you want to read along."

With more than one vault, give one line per vault for item 1 and keep the rest for the default vault.

## ask ("what does my second brain say about X")

1. Read `_hot.md`, then `_index.md`, then the wiki pages that matter. Search `inbox/` too for notes not yet filed.
2. Answer in plain words, in the owner's customer word, and name the pages used: "(from: services-and-prices, 2 inbox notes)".
3. If the vault doesn't cover it, say so plainly. Never fill the gap from general knowledge without saying that's what you're doing ("Your notes don't cover this. Generally, …").
4. If an unfiled inbox note contradicts a wiki page, point it out: "Your note from Tuesday says $95, the wiki says $89. The weekly update will fix the page, or say **update my vault** now."

In an **as-is** vault there's no inbox or wiki: search the whole vault except `.obsidian/`.

## Rules

- Never write, move, or delete anything from this skill.
- Never read `.obsidian/`.
- Use the customer word from `_sb/state.md`.
