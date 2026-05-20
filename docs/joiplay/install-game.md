---
title: Install a game in JoiPlay
last_updated: 2026-05-20
---

# Install a game in JoiPlay

Menu → **Install ›** → **Install game in JoiPlay…**

The app picker accepts both *launch files* and *archives* — pick whichever you have:

| What you pick | What happens |
|---|---|
| `.exe`, `.sh`, `.py`, `.html`, `.swf`, `.jgp` | Sent straight to JoiPlay's add-game dialog. |
| `.zip`, `.rar`, `.7z` | Extracted into your **Destination folder** first; then a file browser appears so you can pick the game's launch file inside. |

## First-time heads up

The first time you use the install flow, a warning explains that JoiPlay will take over to actually register the game. Tick **"Don't show this again"** to skip the dialog next time (you can re-enable it from [JoiPlay settings](settings.md)).

## During extraction

- Progress shows both byte count and percentage, with a heartbeat that updates at least every 200 ms so the UI never appears frozen.
- Password-protected archives prompt you for the password and retry. Passwords are kept in memory only — never stored.
- A confirmation dialog appears before extraction, showing source path and destination. If the app has write access to the source archive, you'll see an optional **Delete the archive after a successful extraction** checkbox.
- RAR5 is supported on arm64 devices (most modern phones); RAR4 works everywhere.
- Safety caps: archives are rejected if they would expand past **10 GB** or if any single entry shows a >100× compression ratio (zip-bomb guard).

## After extraction

A file browser opens showing the extracted folder. The most likely launch file is highlighted (e.g. `Game.exe`, `script.rpy`, `index.html`). Tap **Send to JoiPlay**, or pick a different file.

JoiPlay then opens its own add-game flow on top — finish there. The app passes JoiPlay the **raw filesystem path** of the file so JoiPlay can scan sibling files in the game folder.

## What we won't do

- **JoiPlay's library doesn't sync back to us.** The game won't appear in F95 Updater's list until you re-export your JoiPlay backup and import the new `.joiback` file.
- **No automatic re-extraction.** Re-running the flow on the same archive produces a fresh copy in your destination folder.

## See also

- [Install APK](install-apk.md) — the matching flow for plain Android `.apk` files.
- [JoiPlay settings](settings.md) — configure source and destination folders.
- [Import .joiback backup](import-backup.md) — how the game eventually shows up in F95 Updater.
- [Delete a JoiPlay game](delete-game.md)
