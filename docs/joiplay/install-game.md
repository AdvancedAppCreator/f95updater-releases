---
title: Install a game in JoiPlay
last_updated: 2026-05-19
---

# Install a game in JoiPlay

Two paths, depending on whether your game is already extracted or still in a
compressed archive.

## Path A: Already-extracted game folder

Use this when the game is already unpacked on your phone (for example you used
a file manager to unzip it yourself).

1. Menu → **JoiPlay** → **Install game in JoiPlay…**
2. On first use, a "heads up" dialog explains the flow. Tick **"Don't show this
   again"** if you don't want to see it next time.
3. Pick the game's launch file — `Game.exe` for RPG Maker, `index.html` for
   HTML / Tyrano, `script.rpy` for Ren'Py, etc.
4. JoiPlay opens its add-game dialog. Finish there.

## Path B: Still in a compressed archive

Use this when you have a `.zip`, `.rar`, or `.7z` file.

1. Menu → **JoiPlay** → **Extract & install…**
2. The same heads-up dialog appears the first time (shared with Path A).
3. Pick the archive file.
4. The app extracts it into the folder you've configured in **JoiPlay
   settings** (see below). A progress dialog shows bytes processed; Cancel
   removes the partial extraction.
5. If the archive is password-protected, the app prompts for the password and
   retries. Passwords are kept in memory only — never stored.
6. After extraction, a file browser opens. The most likely launch file is
   highlighted and pre-selected (e.g. `Game.exe`). Tap **Send to JoiPlay**, or
   pick a different file.

### What we won't do

- **JoiPlay's library doesn't sync back to us** — neither path adds the game to
  F95 Updater's list. You'll only see the new game in F95 Updater after you
  re-export your JoiPlay backup and import the new `.joiback`. This is a
  one-way information flow that's a JoiPlay limitation, not ours.
- **No automatic re-extraction.** Once a game is extracted, it stays where it
  is — re-running the flow on the same archive creates a fresh copy.
- **Safety caps:** archives are rejected if they would expand past **10 GB** or
  if any single file shows a >100× compression ratio (zip-bomb guard).

## JoiPlay settings

Menu → **JoiPlay** → **JoiPlay settings…** controls three things:

| Setting | What it does |
|---|---|
| **Source folder** | Where the file picker opens when you pick an archive. Leave unset to start at Android's default. |
| **Destination folder** | Where extracted games are saved. Each archive gets its own subfolder. Required for the **Extract & install** flow. |
| **Storage strategy** | **SAF** (recommended): writes go through the Storage Access Framework using the folders above. **Full storage** (faster): requires Android's "All files access" permission. **Ask each time**: prompts for a destination on each extraction. |

Both folder pickers grant the app a persistent SAF tree URI; you only need to
set them once per install.

## See also

- [Import .joiback backup](import-backup.md) — how the game eventually shows
  up in F95 Updater.
- [Delete a JoiPlay game](delete-game.md).
