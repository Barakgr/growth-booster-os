# Growth Booster Second Brain

A second brain for an owner-operated business, set up by Claude, step by step. The owner drops notes in whenever something comes up: a customer's odd request, a price change, how a tricky job got solved. Once a week Claude folds those notes into a small wiki, one clean page per topic, that the owner and Claude can both look things up in. The notes live in Obsidian, a free app, as ordinary files inside the Cowork workspace. Nothing is locked in.

Works on its own. If Growth Booster OS is already set up, it uses that business profile; if not, it asks four quick questions.

Built by Barak Granot, Growth Booster. https://growthboostercrm.com

## Install

1. In Claude Desktop, open **Customize**, then the **Plugins** tab.
2. If the Growth Booster marketplace is already added, click **Sync**. If not: **Add → Add marketplace → Add from a repository**, paste the repository path (the part after github.com/), and click **Sync**.
3. Find **Growth Booster Second Brain** and click **+**.
4. Open a new Cowork task and type **set up my second brain**.

## Commands

| Command | Say this | What it does |
|---|---|---|
| `/sb-setup` | "set up my second brain", "continue second brain setup" | The step-by-step setup. Stop after any phase and pick up later. Also "add another vault" and "show second brain progress". |
| `/sb-open` | "open my vault", "what does my second brain say about…" | What's new in five lines, or an answer from your notes with the pages it used. Changes nothing. |
| `/sb-file` | "file this note: …", "build a page about…" | Saves a note in your words, or makes a wiki page right now. |
| `/sb-update` | "update my vault", "update my cheat sheet" | The weekly sort: new notes into the right pages, index and cheat sheet refreshed. Runs as a scheduled task. |
| `/sb-health` | "vault health check" | Monthly report: stale pages, contradictions, unfiled notes. Fixes nothing until you say go. |

## The setup, phase by phase

| # | Phase | Minutes | What happens |
|---|---|---|---|
| 0 | Welcome | 3 | Uses the Growth Booster OS profile, or asks four business basics. |
| 1 | Plan | 3 | New or existing Obsidian vault, where it lives, one vault or two. |
| 2 | Obsidian | 5 | The owner installs Obsidian (skipped if they already use it). |
| 3 | Build | 2 | Claude builds the inbox, wiki, and three top files. |
| 4 | Connect | 5 | Opens the vault in Obsidian, tells Claude where it is, and proves Claude can read and write it. |
| 5 | Settings | 10 | Four Obsidian settings and up to three optional add-ons. |
| 6 | First pages | 10 | Two or three real notes, two wiki pages, one live weekly update. |
| 7 | Routines | 5 | A weekly update task and a monthly health check task. |
| 8 | Sync *(optional)* | 5–10 | Notes on a phone or second computer, done safely. |
| 9 | Claude chat *(optional)* | 5 | Regular Claude chats on the computer can read the vault too. |

Core setup: about 40 minutes. Progress is saved after every phase.

## What it creates in the workspace

```
SecondBrain/          (or inside an existing Obsidian vault)
  inbox/              your raw notes. Claude never changes them.
  wiki/               one page per topic, kept current by Claude.
  attachments/
  _index.md           every page, one line each
  _hot.md             the cheat sheet: 10 to 20 facts that matter most, under 300 words
  _log.md             one line each time Claude changes the vault
_sb/
  state.md            setup progress and vault locations
  basics.md           only when Growth Booster OS isn't set up
claude.md             gets a "My second brain" section
outputs/second-brain/ weekly update and health check reports
```

## Safety

Claude reads the vault and writes only to the inbox, the wiki, and the three top files. It never touches Obsidian's settings folder, never rewrites the owner's notes, and never deletes anything; unwanted files move to `_review/`. The owner installs apps and clicks buttons; Claude never installs software or moves the vault. The vault always stays inside the Cowork workspace, never in iCloud, OneDrive, Dropbox, or Google Drive.

## Coming from /gb-vault

Owners who set up a second brain with `/gb-vault` in Growth Booster OS 0.2.x don't redo anything. The first time `/sb-setup` runs, it carries over the existing vault and marks the finished steps as done.
