---
name: gb-vault
description: Sets up and runs the owner's second brain, an Obsidian vault inside the Cowork workspace that Claude reads and keeps organized. Six-step resumable setup (new vault or an existing one), then open, capture, build a page, weekly update, refresh the cheat sheet, ask, and monthly health check. Trigger when the owner says "set up my second brain", "set up Obsidian", "connect my vault", "continue vault setup", "open my vault", "what's new in my vault", "file this note", "build a page about", "make a wiki page for", "update my vault", "update my wiki", "update my cheat sheet", "refresh hot", "what does my second brain say about", "vault health check", or types /gb-vault.
---

# gb-vault: the second brain

A second brain is a folder of plain notes the owner keeps and Claude organizes. The owner dumps things in whenever they come up: a customer's odd request, a price change, how a tricky job got solved, an idea from a podcast. Once a week Claude folds those notes into a small wiki: one clean page per topic that Claude and the owner can both look things up in. Obsidian is just the app the owner uses to read and write those notes. The notes are ordinary files, so nothing is locked in.

Be plain and brief. The owner is busy and not technical. One question at a time.

## Prerequisites

Before anything else, check that `claude.md` and `about-me/business.md` exist in the workspace. If either is missing, say:

> "The second brain builds on your basic setup, and that isn't finished yet. Type **start setup** first, then come back and say **set up my second brain**."

Stop there.

## Read first, every time this skill fires

1. `_gb/state.md`. Look for the `vault:` section. If there is none, this is a first-time vault setup.
2. `about-me/business.md` (for the customer word and the business's topics).
3. `SecondBrain/_hot.md` and `SecondBrain/_index.md` if they exist.
4. `reference/obsidian-setup.md` in this skill folder before walking the owner through anything inside Obsidian.

## The vault layout

The vault always lives **inside** the Cowork workspace folder, never next to it and never in iCloud, OneDrive, Dropbox, Google Drive, Desktop, or Documents.

```
SecondBrain/
  inbox/          the owner's raw notes, clips, voice-memo transcripts. Claude files new notes here.
  wiki/           one page per topic, written and kept up to date by Claude.
  attachments/    images and PDFs Obsidian saves.
  _index.md       a list of every wiki page with one line on what it covers.
  _hot.md         the 10 to 20 facts that matter most right now, under 300 words. Claude reads this first.
  _log.md         one dated line each time Claude changes the vault.
```

## Safe zones

Claude may **read** anything in `SecondBrain/` except `.obsidian/`.
Claude may **write** only to `inbox/`, `wiki/`, `_index.md`, `_hot.md`, and `_log.md`.
Claude never touches `.obsidian/` (that's Obsidian's own settings folder).
Claude never deletes a note. Anything the owner wants gone moves to `_review/` in the workspace.
Claude never rewrites what the owner wrote in `inbox/`. It files and links; the owner's words stay as they are.

## First-time setup: six steps

Add this block to `_gb/state.md` the first time, then run the steps in order. After each step, update its status, append one entry to `about-me/memory.md`, and end with: "Step X done. Continue to Step Y, or pause? (Type **continue** or **pause**.)"

```
vault:
  next_step: 1
  complete: false
  path: null
  mode: null            # fresh | as-is | on-top
  area: null            # only for on-top: the sub-folder that holds inbox/ and wiki/
  update_day: null
  steps:
    1: { name: plan,        status: pending }
    2: { name: folders,     status: pending }
    3: { name: obsidian,    status: pending }
    4: { name: plugins,     status: pending }
    5: { name: first-pages, status: pending }
    6: { name: routine,     status: pending }
```

### Step 1: Plan (2 minutes)

Explain in three sentences what a second brain is and what it's for, using the owner's business. Then ask one question:

> "Do you already use Obsidian for notes? (Type **yes** or **no**.)"

**No:** mode is `fresh`. Go to Step 2.

**Yes:** ask for the vault's full path, and teach them how to copy it (see "Copy a folder path" in `reference/obsidian-setup.md`). Don't try to detect it yourself; Obsidian's own settings live outside the workspace, so you usually can't see them, and that's normal.

- **If the path is outside the workspace folder**, explain in one line that Claude can only reach what's inside the workspace, and offer the move: close Obsidian, copy the whole vault folder into the Claude Cowork folder in Finder or File Explorer, reopen it with **Open folder as vault**, then paste the new path. The owner does the move; Claude never moves it. If they won't move it, stop and say the second brain can't work from outside the workspace.
- **Once it's inside**, offer the three modes, one line each, and let them pick:
  1. **Connect as-is**: Claude reads everything and writes only to files the owner names. No folders added, nothing moved. For owners with a system they like.
  2. **Add folders on top**: Claude adds `inbox/`, `wiki/`, and the three top files inside one sub-folder the owner picks (ask which; suggest `Business`). Everything else stays untouched. The best fit for most owners with an existing vault.
  3. **Start fresh**: for a vault with nothing worth keeping. Treat it like `fresh`.

Record `path`, `mode`, and `area` in state. If Claude ever suggests a path, it must end inside the workspace folder. A path that sits next to it (like `/Users/name/SecondBrain` beside `/Users/name/Claude Cowork`) is wrong; say so and ask again.

For **as-is**, skip Steps 2, 4, and 5: write only the `## My second brain` block to `claude.md` (with "write only to files I name" in place of the folder rules) and go to Step 3's tests, then finish. In as-is mode there is no inbox or wiki, so **file**, **build**, **update**, and **refresh hot** write only where the owner says; **open**, **ask**, and **health check** work as normal.

### Step 2: Folders (1 minute)

Create the layout above (for `on-top`, inside the chosen sub-folder; everywhere below, read `SecondBrain/` as that folder). Write `_index.md` with a one-line intro and an empty list, `_hot.md` with the three most important facts from `about-me/business.md`, and `_log.md` with today's entry. Then append this section to `claude.md` if it isn't there:

```
## My second brain
My notes live in SecondBrain/ inside this folder. Read SecondBrain/_hot.md first when a question is about my business, customers, or how we do things, then _index.md, then the wiki page you need.
You may write only to SecondBrain/inbox/, SecondBrain/wiki/, and the _index, _hot, and _log files. Never touch SecondBrain/.obsidian/. Never delete a note; move it to _review/.
Never rewrite my words in inbox/. File them and link them.
```

Record `path` in state.

### Step 3: Open it in Obsidian (5 minutes)

Walk the owner through `reference/obsidian-setup.md`, section "Install and open the vault", one step at a time, waiting for **done** after each. The owner installs Obsidian themselves from obsidian.md. Claude never downloads or installs anything.

Then run two tests and report each as passed or failed:

1. **Read test.** Read `_hot.md` (or, for `as-is`, the most recently changed note) and quote its first line back. Ask: "Is that from your vault? (yes / no)". A no means Claude is pointed at the wrong folder; stop and fix the path.
2. **Write test.** Write `inbox/hello-from-claude.md` with one line ("If you can read this in Obsidian, we're connected."). Ask whether they see it in Obsidian's left sidebar. Then move it to `_review/` and say so.

Both pass before Step 4.

### Step 4: Plugins and settings (10 minutes)

Walk through `reference/obsidian-setup.md`, sections "Settings to change" and "Plugins". Present the three recommended plugins, one at a time, with a one-line reason each. The owner can say **skip** to any of them. None is required for the second brain to work.

Then mention the optional Obsidian skill pack for Claude (see the reference file). Only offer it; the owner installs it through Customize → Plugins.

### Step 5: First notes and first pages (10 minutes)

Ask the owner to type or paste 2 or 3 messy notes, the way they'd jot them on a napkin. Save each as its own file in `inbox/` named `YYYY-MM-DD-short-title.md`, their words untouched.

Then build the first two wiki pages from `about-me/business.md` plus those notes. Good first pages for a local business:

- `wiki/services-and-prices.md`
- `wiki/common-questions.md` (what customers ask, and the answers the owner actually gives)
- `wiki/how-we-handle-<the most common tricky situation>.md`

Show each page in full before saving. Update `_index.md` and `_hot.md`. Every wiki page ends with a `Sources:` line linking the notes it came from, like `[[2026-09-28-price-change]]`.

### Step 6: The weekly routine (5 minutes)

Set up one scheduled task with the owner. Walk them through it; they click the buttons.

- Name: **Weekly vault update**
- When: ask first: "Which day and time do you want me to sort your notes each week? Friday at 4:00 PM works for most people." Record `update_day`.
- Instructions (paste exactly):

```
Run /gb-vault update. Read SecondBrain/_hot.md and _index.md, then every note in SecondBrain/inbox/ added since the last entry in _log.md. Fold what's new into the right wiki pages, create a new page only when a topic has 2 or more notes, update _index.md and _hot.md, and add one line to _log.md. Never change or delete the notes in inbox/. Nobody is here: do not ask questions. Save and stop.
```

Tell them to click **Run now** once and approve what it asks, so the first approval is saved with the task. Remind them it only runs when Claude is open and the computer is awake.

Set `vault.complete: true`. Close with the habit: "Whenever something comes up, say **file this note:** and tell me. On Fridays I'll sort it. If you need a page right away, say **build a page about** and the topic."

## Everyday commands

**open** ("open my vault", "what's new in my vault"): the daily starter. Read-only. Report in five lines or fewer: how many inbox notes arrived since the last `_log.md` entry (list their titles), when the last weekly update ran, any wiki page the owner asked about recently, and one suggestion ("3 new notes about pricing; say **update my vault** to fold them in now, or leave them for Friday"). Then remind them to open Obsidian if they want to read along. Change nothing.


**file this note** (or "add to my second brain", "remember this in my vault"): save it to `inbox/YYYY-MM-DD-short-title.md` in the owner's words. If it's clearly a correction to a wiki page, say so and ask whether to update that page now or leave it for Friday.

**build** ("build a page about X", "make a wiki page for X"): make one wiki page now instead of waiting for Friday.

1. Check `_index.md`. If a page on X already exists, say so and offer to update it instead.
2. Search `inbox/`, `wiki/`, and `about-me/` for everything on X. List what you found in one line ("3 notes and your business file mention warranties").
3. Ask up to three short questions, one at a time, only for gaps that matter. If the owner says **skip**, leave the gap marked `(not known yet)`. Never fill it in yourself.
4. Write `wiki/<topic-in-kebab-case>.md`: a one-line summary at the top, then short sections in the owner's customer word, then `Related:` links to other wiki pages, then the `Sources:` line. Save the owner's answers from step 3 as a new inbox note first, so the page has a source.
5. Show the whole page before saving. On **looks good**, save it, add it to `_index.md`, update `_hot.md` if it changes what matters most, and add one line to `_log.md`.

**refresh hot** ("update my cheat sheet", "refresh hot"): rebuild `_hot.md` only. Read `_index.md`, the wiki pages changed in the last 30 days, and `about-me/business.md`. Keep the 10 to 20 facts the owner would want Claude to know first: current prices, current offers, what's changed recently, the rules that are easy to get wrong. Under 300 words, each fact linked to its page. Show the new version next to the old one and save on **go**.

**update** (weekly, or when the owner says "update my vault"): the scheduled-task routine above. When the owner is present, show a short list of what changed before saving.

**ask** ("what does my second brain say about X"): read `_hot.md`, then `_index.md`, then the pages that matter. Answer in plain words and name the pages you used. If the vault doesn't cover it, say so. Never fill the gap from general knowledge without saying that's what you're doing.

**health check** (monthly, or "vault health check"): report, don't fix. List wiki pages not updated in 60 days, facts that contradict each other or `about-me/business.md`, inbox notes older than 14 days that were never filed, and pages with no `Sources:` line. Propose the one fix that matters most. Make no changes until the owner says **go**.

## Rules

- Never invent facts, prices, or customer details. A wiki page only says what the notes or the about-me files say.
- Use the owner's customer word everywhere.
- Keep `_hot.md` under 300 words. It's a cheat sheet, not a report.
- Don't recommend more plugins than the three in the reference file. Fewer moving parts beats more features.
- If the owner asks about syncing to a phone, use the "Sync" section of the reference file. Never suggest putting the workspace in a cloud-synced folder.
