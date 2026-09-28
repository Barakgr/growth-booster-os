# Obsidian setup: the owner-facing steps

Walk the owner through these one step at a time. Wait for **done** after each. The owner clicks; Claude never installs, downloads, or changes app settings itself. Button names can shift between Obsidian versions. If the owner doesn't see a button, ask them to describe the screen and adapt.

Obsidian is free, including for business use. No account is needed.

## Install and open the vault

1. Go to **obsidian.md** and click **Download**. Pick Mac or Windows.
2. Open the downloaded file and install it like any other app.
3. Open Obsidian. On the welcome screen, click **Open folder as vault** (sometimes shown as **Open** next to "Open folder as vault").
4. Find your Claude Cowork folder, click **SecondBrain** inside it, and click **Open**.
5. If Obsidian asks whether to trust the author and enable plugins, click **Trust**. It's your own folder.

You'll see `inbox`, `wiki`, and `attachments` in the left sidebar. That's the vault.

**Wrong folder check:** the vault must be the `SecondBrain` folder *inside* Claude Cowork. If Obsidian made a new folder somewhere else (like Documents), close it and repeat step 4.

## Copy a folder path

- **Mac:** in Finder, right-click the folder, then hold the **Option** key. The menu item changes to **Copy "[folder]" as Pathname**. Click it. It looks like `/Users/yourname/Claude Cowork/SecondBrain`.
- **Windows:** in File Explorer, hold **Shift** and right-click the folder, then choose **Copy as path**. It looks like `C:\Users\yourname\Claude Cowork\SecondBrain`.

Paste it into the chat. If it doesn't end with `Claude Cowork/...`, the vault is outside the workspace.

## Settings to change

Open **Settings** (the gear at the bottom left), then **Files and links**:

- **Default location for new notes**: choose **In the folder specified below**, then type `inbox`.
- **Default location for new attachments**: choose **In the folder specified below**, then type `attachments`.
- **Use [[Wikilinks]]**: on.
- **Automatically update internal links**: on.

That's it. Leave everything else alone.

## Plugins

None of these is required. Offer them one at a time with the one-line reason. The owner can skip any.

To install a community plugin: **Settings → Community plugins → Turn on community plugins** (first time only), then **Browse**, search for the name, click **Install**, then **Enable**.

1. **Omnisearch.** Better search. It forgives typos and ranks the best match first, so "that note about the Hendersons' water heater" turns up even if you misspell it.
2. **Dataview.** Lets a page show live lists, like "every note that mentions a warranty". You never have to write these yourself; ask Claude to add one to a page.
3. **Obsidian Web Clipper** (a browser extension, not an Obsidian plugin). Saves any web page into your vault with one click. Install it from **obsidian.md/clipper** for Chrome, Safari, Edge, or Firefox. In its settings, set the vault to **SecondBrain** and the folder to **inbox**.

If the owner asks for more: tell them to live with these for a few weeks first. Most people never need more.

## Optional: the Obsidian skill pack for Claude

Obsidian's CEO publishes a free set of Claude skills that teach Claude Obsidian's formats (links, callouts, properties, Bases, Canvas). Growth Booster OS works fine without it. If the owner wants it, they add it the same way they added Growth Booster OS: **Customize → Plugins → Add → Add marketplace → Add from a repository**, type **kepano/obsidian-skills**, click **Sync**, and turn on **obsidian**.

## Sync to a phone (optional)

Ask two questions, one at a time:

1. "Do you want your notes on your phone or a second computer too?" If no, skip sync entirely.
2. "Would you rather pay a few dollars a month for the easy way, or do a bit more setup to keep it free?"

Then recommend one:

- **Obsidian Sync** (easy, works on phones). The Standard plan is about $4 a month billed yearly, or $5 month to month, for one vault. Turn on encryption and save the encryption password in a password manager. If it's lost, it can't be recovered. Turn it on from the main computer first, so that copy is the master.
- **Syncthing** (free, more setup, computers and Android). Good for someone who likes to tinker.
- **Git with a private repository** (free, keeps every past version). Only for owners who already use GitHub.
- **Never** put the Claude Cowork folder in iCloud, OneDrive, Dropbox, or Google Drive to "sync" it. It causes duplicate files and broken notes.

Prices change. If the owner asks for exact pricing, send them to obsidian.md/pricing instead of quoting.

## Troubleshooting

| What the owner sees | What to do |
|---|---|
| Obsidian shows an empty vault | They opened the wrong folder. Close the vault (**Open another vault** at the bottom left) and pick SecondBrain inside Claude Cowork. |
| Claude says it can't find SecondBrain | The folder isn't inside the workspace, or Cowork is pointed at a different folder. Check which folder is selected under the chat box. |
| A note shows "(1)" or "conflicted copy" | Something is syncing the workspace through a cloud folder. Stop that sync; use Obsidian Sync instead. |
| Community plugins won't turn on | Settings → Community plugins → turn off **Restricted mode**. |
| The weekly update didn't run | Claude was closed or the computer was asleep on Friday, or nobody clicked **Run now** once. |
