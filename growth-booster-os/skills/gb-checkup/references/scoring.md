# Checkup scoring

This is the rule. `SKILL.md` summarizes it; when they disagree, this file wins. Phase 6 of setup uses the same rubric for the baseline score.

## The rubric

25 points each. Total 0–100.

**Know** (does Claude know the business)
- 0–8: no `about-me/business.md` or `voice.md`, or either still has `~~` placeholders
- 9–16: both exist; fewer than 3 real writing samples in voice.md
- 17–22: both complete, 3+ real samples, memory.md has 5+ entries
- 23–25: above, plus business.md updated in the last 60 days and memory.md appended within the last 7 days
Penalties: any `~~` placeholder anywhere caps Know at 8. memory.md not appended in 14 days: −3.

**Connect** (which tools Claude can actually reach)
- 0–8: no live tool connections (a connection counts only if a read actually returns data)
- 9–16: Gmail OR Calendar live
- 17–22: Gmail AND Calendar live
- 23–25: Gmail, Calendar, AND the CRM (or a `people/` folder with 5+ notes) live, with sends blocked and writes on ask-first
Penalty: any send or delete action set to "act without asking": −5.

**Use** (are the skills actually used)
- 0–8: setup done, no skill run since
- 9–16: `/gb-brief` or `/gb-write` used in the last 14 days (evidence: outputs/ files or memory.md)
- 17–22: three or more skills used in the last 14 days, including `/gb-followup`
- 23–25: above, plus at least one custom skill or people/ note the owner added themselves
Rule: a skill installed but never run counts as not installed.

**Repeat** (routines firing on their own)
- 0–8: no scheduled tasks
- 9–16: daily brief scheduled
- 17–22: daily brief firing reliably (3+ briefs in outputs/daily-brief/ in the last 7 days) plus weekly checkup scheduled
- 23–25: both firing reliably, plus one more routine the owner chose

## Bands

Bands: 0–30 Leaking, 31–55 Patched, 56–75 Working, 76–90 Tuned, 91–100 Running itself.

## The gap rule

Gap rule: the top gap is NOT automatically the lowest area. It's the area where one specific change produces the biggest business return. Always tie the gap to a business outcome ("new leads are sitting unanswered until you open your laptop", not "Connect is low").

## How to place a score inside a range

Each range has room. Use it.

- Bottom of the range: the bar is barely met.
- Middle: met cleanly.
- Top: met with something extra (a sixth sample, a brief that ran 7 for 7, a people/ folder the owner keeps up by hand).

Apply penalties after placing the score. A penalty can push a score below the bottom of its range; a cap cannot be exceeded by anything. Never go below 0 on an area.

## What counts as evidence

- A writing sample is real when it's something the owner actually sent, pasted in their words. A sample the owner wrote on the call to fill the slot counts. A sample Claude drafted does not.
- A skill was "used" when there's a dated file in `outputs/` or a dated memory entry naming it. The owner saying "I think I ran it" is not evidence.
- A brief "fired" when its file exists in `outputs/daily-brief/` with that day's date.
- A scheduled task is "scheduled" when it shows in the scheduled-task list, not when brief-preferences.md says it should exist.
- A connection is "live" when a read-only call returned real data during this checkup. Not last week. Now.

## Worked examples of "biggest leak"

Each one names the gap, the outcome the owner feels, and nothing about the score. Match this shape.

1. **Missed after-hours calls.** "Calls after 5 go to voicemail and nobody texts back until Karen opens up at 8. Anyone who called at 6 PM with a dead AC has already booked with someone else by then."

2. **Stale business file.** "Your business.md still lists three services, but memory.md says you added duct cleaning in October. Every draft I write leaves it out, so nobody hears about it unless you remember to say it."

3. **No CRM connection.** "Form fills land in the CRM and I can't see them, so the morning brief never shows them. You find out about new homeowners when you log in, which last week was Tuesday afternoon for a Saturday lead."

4. **Quotes never chased.** "You sent eleven estimates in the last two weeks and there's no follow-up draft for any of them. Silence on a quote usually isn't a no; it's a homeowner waiting for a nudge that isn't coming."

5. **Brief not firing.** "The daily brief is scheduled but only ran twice in the last seven days. On the five days it didn't, nothing surfaced the two overdue callbacks in your inbox."

6. **Reviews asked for by memory.** "Twelve jobs finished this month and one review came in. Your file says you ask 'when I remember'. The best moment to ask is the day the job is done, and that moment has passed twelve times."
