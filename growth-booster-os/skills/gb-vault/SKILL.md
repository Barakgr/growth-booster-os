---
name: gb-vault
description: Points the owner to Growth Booster Second Brain, the separate plugin that now runs the Obsidian second brain. Trigger when the owner says "set up my second brain", "set up Obsidian", "connect my vault", "open my vault", "file this note", "build a page about", "update my vault", "vault health check", or types /gb-vault, and the Growth Booster Second Brain plugin's commands (/sb-setup, /sb-open, /sb-file, /sb-update, /sb-health) aren't available.
---

# gb-vault: moved to Growth Booster Second Brain

The second brain is now its own plugin, **Growth Booster Second Brain**, in the same Growth Booster marketplace. This skill only points there.

## If the Growth Booster Second Brain commands are available

Hand off. Match what the owner asked to the right command and follow that skill instead of this one:

- set up, continue setup, connect a vault → `sb-setup`
- open my vault, what does my second brain say → `sb-open`
- file this note, build a page → `sb-file`
- update my vault, refresh the cheat sheet → `sb-update`
- vault health check → `sb-health`

## If they aren't available

**Owner present.** Say:

> "Your second brain moved into its own plugin, **Growth Booster Second Brain**. It takes one minute to turn on: open **Customize**, then **Plugins**, click **Sync** on the Growth Booster marketplace, find **Growth Booster Second Brain**, and click **+**. Then quit Claude fully and reopen it. If you already set up a second brain, nothing gets redone. Your notes stay exactly where they are. Then say **set up my second brain**."

Change nothing.

**Unattended** (a scheduled task, such as an old "Weekly vault update" that says `/gb-vault update`): don't change the vault. Save this note to `outputs/second-brain/YYYY-MM-DD-action-needed.md` and stop:

> "Your weekly vault update didn't run. The second brain moved into its own plugin, Growth Booster Second Brain. Turn it on in Customize → Plugins (sync the Growth Booster marketplace, then click + on Growth Booster Second Brain), then say **set up my second brain**. It keeps your existing notes and fixes this scheduled task with you."
