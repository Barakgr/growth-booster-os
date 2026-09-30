# Phase 7 — Routines (5 minutes)

## Goal
Two scheduled tasks: a weekly update that sorts the inbox into the wiki, and a monthly health check that reports what's stale. The owner creates them; Claude walks them through it.

## Reads first
- `_sb/state.md`

## Steps

1. **Reality check, said once:**
   > "Scheduled tasks only run while the Claude app is open and your computer is awake. If it's asleep at that time, the task runs the next time it can, or waits for next week."

2. **Weekly update.** Ask:
   > "Which day and time should I sort your notes each week? Friday at 4:00 PM works for most people."

   Record `update_day`. Walk the owner through creating a scheduled task, one step at a time, waiting for **done**. Button names shift between versions; if the owner doesn't see one, ask them to describe the screen and adapt.

   - Name: **Weekly vault update**
   - When: weekly, on the day and time they picked
   - Instructions (paste exactly):

   ```
   Run /sb-update. Use the vaults and paths in _sb/state.md. For each vault, read _hot.md and _index.md, then every note in inbox/ added since the last entry in _log.md. Fold what's new into the right wiki pages, create a new page only when a topic has 2 or more notes, update _index.md and _hot.md, and add one line to _log.md. Never change or delete the notes in inbox/. Nobody is here: do not ask questions. Save and stop.
   ```

   Tell them to click **Run now** once and approve what it asks, so the approval is saved with the task.

3. **Monthly health check.** Ask:
   > "Once a month I can check the vault for stale pages and notes that never got filed. I only report; I fix nothing until you say go. First Monday of the month at 9:00 AM? (Type **yes**, a different time, or **skip**.)"

   On yes or a time, record `health_day` and walk through a second scheduled task:

   - Name: **Monthly vault health check**
   - When: monthly, at the time they picked
   - Instructions (paste exactly):

   ```
   Run /sb-health. Use the vaults and paths in _sb/state.md. Report only: wiki pages not updated in 60 days, facts that contradict each other or the basics file, inbox notes older than 14 days that were never filed, and pages with no Sources line. Save the report to outputs/second-brain/YYYY-MM-DD-health-check.md and propose the one fix that matters most. Change nothing in the vault. Nobody is here: do not ask questions. Save and stop.
   ```

   On **skip**, set `health_day: manual` and say: "Fine. Say **vault health check** whenever you want one."

4. Mark Phase 7 complete. Set `setup_complete: true`. Close exactly as described in "When the core phases finish" in `SKILL.md`.
