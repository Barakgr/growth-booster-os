---
name: gb-checkup
description: Scores the owner's Growth Booster OS setup from 0 to 100 across Know, Connect, Use, and Repeat, names the one leak costing the most business, and proposes one fix for the week. Runs by hand or as a weekly scheduled task. Trigger when the owner says "check my setup", "checkup", "how am I doing", "what should I improve", "weekly checkup", "continue checkup", or types /gb-checkup.
---

# gb-checkup — score the setup, fix one thing

A setup that isn't checked drifts: files go stale, a connection quietly breaks, the brief stops firing and nobody notices for a month. This skill looks at everything once a week, scores it honestly, and fixes one thing. One. Not a list.

## Read before scoring

Note dates as you go; the score depends on them.

- `about-me/business.md`, `voice.md`, `connections.md`, `brief-preferences.md`, `memory.md` — every file in `about-me/`. Count `~~` placeholders. Count real samples in voice.md. Note "Last updated" in business.md and the date of the newest memory entry.
- `about-me/memory-log.md` if it exists — the long view. Skim for patterns.
- `_gb/state.md` — setup progress, `baseline_score`, operator flag.
- `_gb/checkup-log.md` if it exists — last score and date.
- `outputs/` — list file names and dates only. Count briefs in `outputs/daily-brief/` from the last 7 days; count files in `outputs/followups/` and `outputs/writing/` from the last 14 days.
- `people/` — count the notes if the folder exists.
- The list of scheduled tasks — is a daily brief scheduled? A weekly checkup? Anything else?

Then test each tool connection with **one read-only call**: Gmail (list a few recent threads), Google Calendar (list today's events), the Growth Booster CRM (search one contact), Drive if connections.md lists it. A connection counts as live only if data comes back; "connected" in connections.md proves nothing. Also note whether sends or deletes are set to "act without asking".

Change nothing during the reads.

## Score

Score per `references/scoring.md`. That file is the rule; this is the summary.

| Area | What it measures | 0–8 | 9–16 | 17–22 | 23–25 |
|---|---|---|---|---|---|
| Know | Does Claude know the business | files missing or `~~` left | both exist, under 3 samples | complete, 3+ samples, 5+ memory entries | plus business.md fresh (60 d) and memory appended (7 d) |
| Connect | What Claude can actually reach | nothing live | Gmail or Calendar | Gmail and Calendar | plus CRM or 5+ people/ notes, sends blocked, writes ask-first |
| Use | Are the skills used | none since setup | brief or write in 14 d | 3+ skills in 14 d incl. followup | plus a custom skill or people/ note the owner added |
| Repeat | Routines firing alone | no scheduled tasks | brief scheduled | brief firing (3+ in 7 d) plus checkup scheduled | plus one more routine the owner chose |

Penalties: any `~~` placeholder caps Know at 8. memory.md silent 14 days: −3. Send or delete set to act-without-asking: −5 on Connect. A skill never run counts as not installed.

Bands: 0–30 Leaking, 31–55 Patched, 56–75 Working, 76–90 Tuned, 91–100 Running itself.

A low number the owner trusts beats a high number they don't.

## Pick the biggest leak

Not the lowest area. The area where one change brings back the most business. Ask: where is a customer walking out right now because of this gap? Tie it to an outcome the owner feels:

- Good: "Leads that call after 5 go to voicemail and nobody texts them back, so they book with whoever answers first."
- Bad: "Connect is low."

Match the six worked examples in `references/scoring.md`.

## Output

Use this format exactly. No guesses.

```
## Growth Booster checkup — YYYY-MM-DD

**Score: X/100 — [band]** (last time: Y on DATE, ±Z)

| Area | Score | What I saw |
|---|---|---|
| Know | N/25 | ... |
| Connect | N/25 | ... |
| Use | N/25 | ... |
| Repeat | N/25 | ... |

**Biggest leak:** [one specific thing, tied to a business outcome]

**One fix for this week:** [what], because [why]. Takes about [N minutes].
```

First run: "(first checkup — this is the baseline)". If `_gb/state.md` has a `baseline_score`, use it for "last time" when there's no checkup log yet.

Cite specifics in "What I saw": "your business.md hasn't changed since the setup call on 9/30, but memory.md says you added duct cleaning in October", not "business.md may be out of date". Use the owner's customer word.

Then, in interactive mode only:
> Type **fix it** and I'll do it now, or **wait**.

## Fix it

One fix per week. If `_gb/checkup-log.md` shows a fix done in the last 7 days, say so and hold this one for next week.

On **fix it**:
1. Back up first. Copy every file you're about to change to `_gb/backups/YYYY-MM-DD/` with the same name. If the fix is a connection or a scheduled task, write a one-line note of the before-state there instead.
2. Make the change. Three kinds:
   - **Edit a file** (add a missing service, paste a fourth sample, fill a placeholder): make the edit, show the changed lines.
   - **Walk through a connection**: one step at a time, four-year-old rule. "Open Settings, then Connectors. Tell me when you're there." Test with one read when done.
   - **Set up a routine**: create the scheduled task, show the schedule in plain words.
3. Show what changed.
4. Give one verification step the owner can do in under a minute:
   > To check it worked: open a fresh task and ask "What services do we offer?" Duct cleaning should be in the answer.
5. Gate:
   > Type **approve** or **undo**.

On **undo**: restore every file from `_gb/backups/YYYY-MM-DD/`, or remove the scheduled task, or say how to disconnect the tool by hand. Confirm in one line.

On **wait**: log the proposal as "proposed, not done" and stop.

Never change the plugin's own files. Never delete anything; if something has to go, move it to `_review/`. Never send.

## Log

After every run, interactive or not:

1. Append to `about-me/memory.md`:

```
### YYYY-MM-DD — Checkup: X/100 ([band])
- What we did: scored the setup; biggest leak: [leak]
- Files touched: [list, or "none"]
- Decisions the owner made: [fix approved / waited / undone / unattended]
- Open loops: [the fix if not done]
- Next time: [what to re-check]
```

If memory.md is past 30 entries, move the oldest to `about-me/memory-log.md` silently.

2. Append one line to `_gb/checkup-log.md` (create it if missing, with a header line):

```
YYYY-MM-DD | X/100 | [leak, short] | [proposed / done / undone / waited]
```

## Unattended mode

When this runs as a scheduled task, nobody is there to type.

1. Read and score exactly as above.
2. Write the full checkup output, plus the proposed fix and its steps, to `_gb/checkup-pending.md` (overwrite the previous one).
3. Log to memory.md and checkup-log.md with the decision "unattended — proposal saved".
4. Stop. Ask nothing. Change nothing.

When the owner later says **continue checkup**: read `_gb/checkup-pending.md`, show it, and pick up at "Type **fix it** and I'll do it now, or **wait**." Don't re-score unless the pending file is more than 7 days old.

Can't tell if anyone is present? Assume unattended.

## Safety

- Reads, lists, and connection tests: no permission needed.
- Edits, new scheduled tasks, new files: only after **fix it**, with a backup first.
- Sends: blocked, always.
- Deletes: never. `_review/` instead.
- Never invent a score input. If you couldn't read something, say so and score it as missing.

## Sounds like

> Score: 58/100 — Working (last time: 44 on 9/30, +14)
>
> Biggest leak: three homeowners filled out the website form last week and the first reply went out the next afternoon. That's a full day for whoever answered first to win the job.
>
> One fix for this week: connect the Growth Booster CRM so the daily brief shows new form fills every morning at 7. Takes about 10 minutes.
>
> Type **fix it** and I'll do it now, or **wait**.

Short. Specific. One thing.
