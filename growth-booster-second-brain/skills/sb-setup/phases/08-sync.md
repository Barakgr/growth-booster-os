# Phase 8 — Phone sync (optional, 5–10 minutes)

## Goal
If the owner wants their notes on a phone or second computer, get them on one safe sync method. If not, skip it cleanly.

## Reads first
- `reference/obsidian-guide.md`, section "Sync to a phone"

## Steps

1. Ask:
   > "Do you want your notes on your phone or a second computer too? That's handy for jotting notes on a job. (**yes** / **no**)"

   **No →** set `choice: none`, mark the phase `skipped` ("not wanted"), and end with the standard line.

2. Ask:
   > "Would you rather pay a few dollars a month for the easy way that works on iPhone and Android, or do a bit more setup to keep it free? (**easy** / **free**)"

3. Recommend exactly one, using the reference file:
   - **easy →** Obsidian Sync.
   - **free →** Syncthing, unless the owner has an iPhone (Syncthing doesn't officially support iPhone). Then say so plainly and recommend Obsidian Sync anyway, or no sync.
   - Git with a private repository only if the owner says they already use GitHub.

   Record the choice in `choice`.

4. Walk through the chosen method's steps from the reference file, one at a time, waiting for **done**. The owner signs up and pays; Claude never handles payment or passwords.

5. **Say this every time, whatever they picked:**
   > "One rule: never put your Claude Cowork folder in iCloud, OneDrive, Dropbox, or Google Drive to sync it. It creates duplicate files and broken notes."

6. **Phone habit.** Say:
   > "On your phone, new notes go in **inbox**. I'll sort them on [update day] like everything else."

7. Mark Phase 8 complete. Use the standard end line, offering Phase 9.
