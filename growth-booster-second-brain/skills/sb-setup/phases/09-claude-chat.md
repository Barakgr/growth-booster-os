# Phase 9 — Read the vault from regular Claude chats (optional, 5 minutes)

## Goal
Cowork already reads the vault. This optional phase lets the owner's regular Claude chats in the Claude desktop app read it too, so they can ask "what does my second brain say about…" without opening Cowork.

## Reads first
- `_sb/state.md` (vault paths)
- `reference/obsidian-guide.md`, section "Claude chat access"

## Steps

1. Ask:
   > "Want your regular Claude chats on this computer to be able to read your notes too? Cowork already can; this is only for the chat side. (**yes** / **no**)"

   **No →** mark the phase `skipped` ("not wanted") and finish.

2. Say what it does and doesn't do, in two lines:
   > "This lets Claude chats on this computer read your vault folder. It won't work on your phone's Claude app, because your notes live on this computer."

3. Walk through "Claude chat access" in the reference file one step at a time, waiting for **done**. Give access to the vault folder only, never the whole Claude Cowork folder or the home folder.

4. **Test it.** Ask the owner to open a new regular chat (not Cowork) and type:
   > **Read _hot.md in my [vault folder name] folder and tell me the first fact.**

   Fill in the real folder name (usually SecondBrain) before showing it.

   Pass: the first fact comes back. Fail: ask what it said, and re-check the folder they allowed.

5. Remind them of the rule for chats: "In regular chats, ask Claude to read your notes. Keep filing and updating in Cowork, so everything stays in one place."

6. Mark Phase 9 complete. Close with: "That's everything, including the extras. Say **open my vault** any time to see what's new."
