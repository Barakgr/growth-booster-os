# Growth Booster OS

Sets up Claude Cowork for an owner-operated business in about 75 minutes, self-paced, following the Growth Booster OS Setup course. When it's done, Cowork knows the business, writes in the owner's voice, produces a daily brief, drafts lead follow-ups and review replies, and checks its own setup once a week.

Built by Barak Granot, Growth Booster — growthboostercrm.com.

## What's inside

| Command | Say this | What it does |
|---|---|---|
| `/gb-setup` | "start setup", "continue setup" | Six-phase setup. Stop after any phase and pick up later. |
| `/gb-brief` | "daily brief", "what's on today" | One-line priority, today's calendar, leads and follow-ups waiting, urgent inbox, quick wins. Under 300 words. |
| `/gb-write` | "write this in my voice", "reply to this review" | Drafts texts, emails, review replies, and posts that sound like the owner, not like a robot. |
| `/gb-followup` | "follow up with", "missed call from", "the quote went quiet" | Drafts a text and an email for a lead situation, plus when to send each. Never sends. |
| `/gb-checkup` | "check my setup", "checkup" | Scores the setup 0–100 (Know / Connect / Use / Repeat), names the biggest leak, proposes one fix. |

## The setup, phase by phase

1. **Handbook** (10 min) — how Claude should work with the owner. Pasted into Cowork's settings.
2. **Business** (20 min) — what the business does, who it serves, how leads arrive, what happens after, who's on the team.
3. **Voice** (15 min) — how the owner writes, with real samples. Includes a list of words Claude will never use.
4. **Connect** (15 min) — Gmail and Google Calendar, read-first. The Growth Booster CRM when the client is on it.
5. **Routines** (10 min) — daily brief and weekly checkup as scheduled tasks.
6. **Verify** (10 min) — a live test that matters to the owner, then a baseline score.

## What it creates in the client's workspace

```
claude.md
about-me/
  business.md
  voice.md
  connections.md
  brief-preferences.md
  memory.md
outputs/
projects/
people/          (optional — one note per customer; skills read it when it's there)
_review/         (anything the owner asks to delete goes here instead)
_gb/state.md
SecondBrain/     (optional — created by the Growth Booster Second Brain plugin)
```

## Ground rules baked into every skill

Reading is automatic. Drafting asks first. Sending is off — the owner sends. Deleting is off. Nothing gets invented: no made-up numbers, reviews, or customer facts. No guaranteed results in any draft.

## Install

In Claude Desktop, open **Customize → Plugins → Add → Add marketplace → Add from a repository**, paste the repository path (the part after github.com/), click **Sync**, and turn on **Growth Booster OS**. Then open a new Cowork task and type **start setup**. The Growth Booster OS Setup course walks through every step.

## Roadmap

Next add-on: a people intake skill that files incoming email and voice notes into `people/<name>.md` so follow-ups and briefs draw on the full history with each person.
