---
name: sb-health
description: Monthly health check for the Growth Booster Second Brain vault — reports stale wiki pages, contradictions, unfiled inbox notes, and pages without sources, then proposes the one fix that matters most. Reports only; changes nothing until the owner says go. Runs by hand or as the monthly scheduled task. Trigger when the owner says "vault health check", "check my vault", "is my second brain up to date", "what's stale in my vault", or types /sb-health.
---

# sb-health — the monthly health check

Report, don't fix. Nothing in the vault changes unless the owner is present and says **go** to the one proposed fix.

## Find the vaults

1. Read `_sb/state.md` and check every vault in `vaults:` (by hand: the default vault unless the owner names another). For `on-top` vaults, the vault root is `<path>/<area>/`; otherwise it's `<path>/`.
2. If `_sb/state.md` doesn't exist but `_gb/state.md` has a `vault:` section, use that one vault.
3. If neither exists, say the second brain isn't set up yet ("say **set up my second brain**") and stop.
4. Read the basics file named in state.

## The check

For each vault, list:

1. **Stale pages**: wiki pages not changed in 60 days, oldest first. Flag the ones about prices, offers, hours, or staff first; those go wrong fastest.
2. **Contradictions**: two pages that disagree, or a page that disagrees with the basics file or `_hot.md`. Quote both sides in one line each.
3. **Unfiled notes**: inbox notes older than 14 days that no wiki page lists under `Sources:`.
4. **Pages with no sources**: wiki pages with no `Sources:` line, or one that links to a note that doesn't exist.
5. **Cheat sheet size**: `_hot.md` over 300 words, or older than 30 days.
6. **Setup gaps**: the weekly update hasn't logged a line in 10+ days (the scheduled task may not be running); any core phase in `_sb/state.md` still pending.

In an **as-is** vault, check only items 1 (any note not changed in 60 days that looks like a reference page), 2, and 6.

## The report

- Unattended (scheduled task): save to `outputs/second-brain/YYYY-MM-DD-health-check.md`. Ask nothing.
- Owner present: show it in chat, under 200 words, and save the same file.

End with **one** proposed fix, the one that matters most, in one line: "Biggest fix: your drain-cleaning price disagrees between two pages. Say **go** and I'll make both say $95, from your Sept 22 note."

On **go** (owner present only): make exactly that fix, following the rules in `sb-update`, add one line to `_log.md`, and stop. Offer the next fix as a single line; do nothing more without another **go**.

## Rules

- Never delete, rename, or move a note or page. Pages the owner wants gone move to `_review/` in the workspace, on their say-so.
- Never touch `.obsidian/`.
- Never invent the "right" answer to a contradiction. The newer dated note wins; if neither is dated, ask the owner.
