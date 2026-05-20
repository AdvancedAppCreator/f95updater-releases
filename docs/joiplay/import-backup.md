---
title: Import .joiback backup
last_updated: 2026-05-20
---

# Import a JoiPlay backup

JoiPlay can export your installed games as a `.joiback` file (an encrypted
zip). Importing it into F95 Updater lets the app know about each JoiPlay game
without needing direct read access to the JoiPlay games folder.

## How to import

1. In JoiPlay: **Settings → Backup → Export backup**. Save the resulting
   `.joiback` somewhere accessible (Downloads is fine).
2. In F95 Updater: **Menu → Install → Import JoiPlay backup (.joiback)…**.
3. Pick the file. You'll see a snackbar: `Imported N games; matching to catalog…`.

## What gets imported

For every game in the backup, the app records:

- Title, version (from JoiPlay's properties), folder name, engine type
  (Ren'Py / RPG-MV / RPG-MZ / Tyrano / Twine / Kirikiri2 / etc.), exec file.
- Game ID (used as the internal package name `joiplay:<id>`).
- Last-played date.

The catalog match runs over just the imported games (or all apps on
first-run) and a snackbar reports the result.

## After import

JoiPlay games appear in the list with a different background tint to
distinguish them from Android apps. They show:

- Engine type (in the expanded details).
- Cover thumbnail and F95 mapping if matched.
- **▶** to launch via the JoiPlay app.
- **🗑** to delete the game folder — see [Delete a JoiPlay game](delete-game.md).

## Re-importing later

You can re-import a newer `.joiback` at any time. The new game list replaces
the cached one. Any [auto-backups](../backup/auto-backup.md) you've taken
keep a copy of the previous JoiPlay snapshot so you can roll back.

## See also

- [JoiPlay settings](settings.md) — grant All-files access if you want to delete game folders from inside our app.
- [Install game in JoiPlay](install-game.md) — add a new game by file/archive.
