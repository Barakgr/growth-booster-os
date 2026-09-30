# Obsidian guide: the owner-facing steps

Walk the owner through these one step at a time. Wait for **done** after each. The owner clicks; Claude never installs, downloads, moves the vault, or changes app settings itself. Button names shift between app versions. If the owner doesn't see a button, ask them to describe the screen and adapt.

Obsidian is free, including for business use. No account is needed to use it on one computer.

## Install Obsidian

1. Go to **obsidian.md** and click **Download**. Pick Mac or Windows.
2. Open the downloaded file and install it like any other app. (Mac: drag Obsidian into Applications.)
3. Open Obsidian. You'll see a welcome screen. Leave it there for now.

## Open the vault

1. On Obsidian's welcome screen, click **Open folder as vault** (sometimes shown as **Open** next to "Open folder as vault").
2. Find the Claude Cowork folder, click the vault folder inside it (usually **SecondBrain**), and click **Open**.
3. If Obsidian asks whether to trust the author and enable plugins, click **Trust**. It's your own folder.

You'll see `inbox`, `wiki`, and `attachments` in the left sidebar. That's the vault.

## Wrong folder check

The vault must be the folder *inside* Claude Cowork. If Obsidian shows an empty vault, or made a new folder somewhere else (like Documents), click **Open another vault** at the bottom left, then **Open folder as vault**, and pick the right folder.

## Copy a folder path

- **Mac:** in Finder, right-click the folder, then hold the **Option** key. The menu item changes to **Copy "[folder]" as Pathname**. Click it. It looks like `/Users/yourname/Claude Cowork/SecondBrain`.
- **Windows:** in File Explorer, hold **Shift** and right-click the folder, then choose **Copy as path**. It looks like `C:\Users\yourname\Claude Cowork\SecondBrain`.

Paste it into the chat. If the path doesn't go through the Claude Cowork folder, the vault is outside the workspace.

## Settings to change

Open **Settings** (the gear at the bottom left), then **Files and links**:

- **Default location for new notes**: choose **In the folder specified below**, then type `inbox` (or `<area>/inbox` for a vault with folders added on top).
- **Default location for new attachments**: choose **In the folder specified below**, then type `attachments` (or `<area>/attachments`).
- **Use [[Wikilinks]]**: on.
- **Automatically update internal links**: on.

Leave everything else alone.

## Plugins

None of these is required. Offer them one at a time with the one-line reason. The owner can skip any.

To install a community plugin: **Settings → Community plugins → Turn on community plugins** (first time only), then **Browse**, search for the name, click **Install**, then **Enable**.

1. **Omnisearch.** Better search. It forgives typos and ranks the best match first, so "that note about the Hendersons' water heater" turns up even misspelled.
2. **Dataview.** Lets a page show live lists, like "every note that mentions a warranty". The owner never writes these; they ask Claude to add one to a page.
3. **Obsidian Web Clipper** (a browser extension, not an Obsidian plugin). Saves any web page into the vault with one click: a supplier's spec sheet, a competitor's price page. Install it from **obsidian.md/clipper**. In its settings, set the vault to the owner's vault and the folder to **inbox**.

If the owner asks for more: live with these for a few weeks first. Most people never need more.

## Optional: the Obsidian skill pack for Claude

Obsidian's CEO publishes a free set of Claude skills that teach Claude Obsidian's formats (links, callouts, properties, Bases, Canvas). Growth Booster Second Brain works fine without it. If the owner wants it: **Customize → Plugins → Add → Add marketplace → Add from a repository**, type **kepano/obsidian-skills**, click **Sync**, and turn on **obsidian**.

## Sync to a phone

Recommend exactly one. Prices change; for exact pricing send the owner to **obsidian.md/pricing** rather than quoting.

**Never** put the Claude Cowork folder in iCloud, OneDrive, Dropbox, or Google Drive to sync it. It causes duplicate files ("conflicted copy", "(1)") and broken notes.

### Obsidian Sync (easy; Mac, Windows, iPhone, Android)

A paid add-on from Obsidian, a few dollars a month for one vault.

1. Go to **obsidian.md/account**, create an account, and buy Sync.
2. On the main computer: Obsidian **Settings → Core plugins**, turn on **Sync**.
3. **Settings → Sync → Log in**, then **Create new vault** (the remote copy). Turn on **end-to-end encryption** and set an encryption password. Save that password in a password manager. If it's lost, it can't be recovered.
4. Connect this vault to the remote one and let it finish the first sync. Starting on the main computer makes this copy the master.
5. On the phone: install Obsidian from the App Store or Google Play, open it, create an empty vault with the same name, then **Settings → Core plugins → Sync** on, **Settings → Sync → Log in**, choose the remote vault, enter the encryption password.

### Syncthing (free; computers and Android)

Free and open source, a bit more setup. Both devices must be on at the same time for changes to move. No official iPhone app; for iPhone owners, recommend Obsidian Sync or no sync.

1. Install Syncthing on the main computer from **syncthing.net**. On Android, use the **Syncthing-Fork** app from Google Play or F-Droid (the original Android app was discontinued).
2. On each device, open Syncthing and find its **device ID** (Actions → Show ID on a computer).
3. On the main computer, **Add Remote Device** and paste the other device's ID. Accept on the other device.
4. On the main computer, **Add Folder**, choose the vault folder only (never the whole Claude Cowork folder), and share it with the other device. Accept on the other device and pick where it goes.
5. On the phone, open Obsidian and **Open folder as vault** on that synced folder.

### Git with a private repository (free; keeps every past version)

Only for owners who already use GitHub. Don't teach Git from scratch. Point them to the **Obsidian Git** community plugin and keep the repository private.

## Claude chat access

Lets regular Claude chats in the Claude desktop app on this computer read the vault. Doesn't reach the phone's Claude app.

1. Open the Claude desktop app, then **Settings → Extensions**.
2. Click **Browse extensions**, find **Filesystem**, and click **Install**.
3. When it asks which folders to allow, add the vault folder only (for example `…/Claude Cowork/SecondBrain`). Not the Claude Cowork folder, not the home folder.
4. Make sure the extension is turned on. Quit Claude fully and reopen it if the chat can't see it.

## Troubleshooting

| What the owner sees | What to do |
|---|---|
| Obsidian shows an empty vault | Wrong folder. Run the "Wrong folder check". |
| Claude says it can't find the vault | The folder isn't inside the workspace, or Cowork is pointed at a different folder. Check which folder is selected under the chat box, and the path in `_sb/state.md`. |
| A note shows "(1)" or "conflicted copy" | Something is syncing the workspace through a cloud folder. Stop that sync; use one method from "Sync to a phone". |
| Community plugins won't turn on | Settings → Community plugins → turn off **Restricted mode**. |
| The weekly update didn't run | Claude was closed or the computer was asleep, or nobody clicked **Run now** once. |
| Regular Claude chat can't read the notes | The Filesystem extension is off or allows a different folder. Re-check "Claude chat access". |
