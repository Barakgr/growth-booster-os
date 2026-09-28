---
name: gb-vault
description: Sets up and runs the owner's second brain, an Obsidian vault inside the Cowork workspace that Claude reads and keeps organized. Six-step resumable setup, then capture, weekly update, ask, and monthly health check. Trigger when the owner says "set up my second brain", "set up Obsidian", "connect my vault", "continue vault setup", "file this note", "update my vault", "update my wiki", "what does my second brain say about", "vault health check", or types /gb-vault.
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

- **No**: we build a fresh vault. Go to Step 2.
- **Yes**: ask where the existing vault is. If it's already inside the workspace, use it and add only the missing folders. If it's somewhere else, recommend moving it into the workspace (the owner does the move in Finder or File Explorer, Claude never moves it). If they won't move it, stop and explain that Claude can only see what's inside the workspace folder.

### Step 2: Folders (1 minute)

Create the layout above. Write `_index.md` with a one-line intro and an empty list, `_hot.md` with the three most important facts from `about-me/business.md`, and `_log.md` with today's entry. Then append this section to `claude.md` if it isn't there:

```
## My second brain
My notes live in SecondBrain/ inside this folder. Read SecondBrain/_hot.md first when a question is about my business, customers, or how we do things, then _index.md, then the wiki page you need.
You may write only to SecondBrain/inbox/, SecondBrain/wiki/, and the _index, _hot, and _log files. Never touch SecondBrain/.obsidian/. Never delete a note; move it to _review/.
Never rewrite my words in inbox/. File them and link them.
```

Record `path` in state.

### Step 3: Open it in Obsidian (5 minutes)

Walk the owner through `reference/obsidian-setup.md`, section "Install and open the vault", one step at a time, waiting for **done** after each. The owner installs Obsidian themselves from obsidian.md. Claude never downloads or installs anything.

Test: write `inbox/hello-from-claude.md` with one line ("If you can read this in Obsidian, we're connected."). Ask the owner whether they see it in Obsidian's left sidebar. Then move it to `_review/` and say so.

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
- When: once a week. Friday at 4:00 PM works for most people.
- Instructions (paste exactly):

```
Run /gb-vault update. Read SecondBrain/_hot.md and _index.md, then every note in SecondBrain/inbox/ added since the last entry in _log.md. Fold what's new into the right wiki pages, create a new page only when a topic has 2 or more notes, update _index.md and _hot.md, and add one line to _log.md. Never change or delete the notes in inbox/. Nobody is here: do not ask questions. Save and stop.
```

Tell them to click **Run now** once and approve what it asks, so the first approval is saved with the task. Remind them it only runs when Claude is open and the computer is awake.

Set `vault.complete: true`. Close with the habit: "Whenever something comes up, say **file this note:** and tell me. On Fridays I'll sort it."

## Everyday commands

**file this note** (or "add to my second brain", "remember this in my vault"): save it to `inbox/YYYY-MM-DD-short-title.md` in the owner's words. If it's clearly a correction to a wiki page, say so and ask whether to update that page now or leave it for Friday.

**update** (weekly, or when the owner says "update my vault"): the scheduled-task routine above. When the owner is present, show a short list of what changed before saving.

**ask** ("what does my second brain say about X"): read `_hot.md`, then `_index.md`, then the pages that matter. Answer in plain words and name the pages you used. If the vault doesn't cover it, say so. Never fill the gap from general knowledge without saying that's what you're doing.

**health check** (monthly, or "vault health check"): report, don't fix. List wiki pages not updated in 60 days, facts that contradict each other or `about-me/business.md`, inbox notes older than 14 days that were never filed, and pages with no `Sources:` line. Propose the one fix that matters most. Make no changes until the owner says **go**.

## Rules

- Never invent facts, prices, or customer details. A wiki page only says what the notes or the about-me files say.
- Use the owner's customer word everywhere.
- Keep `_hot.md` under 300 words. It's a cheat sheet, not a report.
- Don't recommend more plugins than the three in the reference file. Fewer moving parts beats more features.
- If the owner asks about syncing to a phone, use the "Sync" section of the reference file. Never suggest putting the workspace in a cloud-synced folder.
