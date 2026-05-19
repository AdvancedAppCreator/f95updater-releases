---
title: Delete a JoiPlay game
last_updated: 2026-05-18
---

# Delete a JoiPlay game

Removes the game's folder from disk and hides the row from the app. Use this
to clean up games you no longer want.

## Prerequisites

- You must have [granted the JoiPlay games folder](set-folder.md) at least
  once. If not, the first delete prompts you to do so.
- The granted folder must contain the game's location (see "Picking the
  right folder" in the page above).

## How to delete

1. Tap the **🗑** icon on the JoiPlay row.
2. Confirm in the **Delete JoiPlay game?** dialog.
3. A spinner dialog appears while the folder is being removed (large games
   can take several seconds).
4. Snackbar: `Deleted <game title>`.

<!-- screenshot: joiplay-delete-confirm.png -->

## Persistence

After a successful delete, the game's ID is added to a "deleted games" set
inside the app. Even though the imported `.joiback` snapshot still lists the
game, our app filters it out so it doesn't reappear on next launch.

## Startup prune of missing folders

On every app launch, the app walks all imported JoiPlay games and checks if
their folder still exists on disk. If a folder is definitely gone (we have
read access via SAF or `File.exists()` returned false on a reachable path),
the game is auto-marked deleted — the same as if you'd tapped 🗑.

This catches:

- Games you deleted via a file manager outside our app.
- Games removed in JoiPlay's own UI.
- Games left over from older `.joiback` imports.

Games we can't reach (e.g. in a different storage area without SAF grant)
are left alone — we don't false-prune.

## Troubleshooting

- **"Delete failed — re-grant JoiPlay games folder in menu"** — the granted
  tree URI doesn't actually contain this game's path. Tap **Set JoiPlay
  games folder…** and pick a higher-level folder that includes both your
  granted area and the game's actual location.
- **"Folder not found under root"** — same root cause. The error message
  also names the granted root and the game's storage path so you can spot
  the mismatch.
