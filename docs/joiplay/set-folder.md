---
title: Set JoiPlay games folder
last_updated: 2026-05-18
---

# Set the JoiPlay games folder

This grants F95 Updater Storage Access Framework (SAF) permission to read and
modify your JoiPlay games directory. It's required to **delete** a JoiPlay
game's folder, and improves folder-existence checks for the [startup prune
pass](../faq.md#joiplay-row-keeps-coming-back-after-i-deleted-it).

## When you need it

- Before you can [delete a JoiPlay game folder](delete-game.md).
- After uninstalling and reinstalling the app (SAF permissions don't survive
  uninstall).
- If you moved your games to a different folder on your phone.

## How to grant it

Menu → **JoiPlay** → **Set JoiPlay games folder…**.

In Android's folder picker:

1. Navigate to the **root folder that contains all your JoiPlay games**
   (usually `Internal storage › Games` or `Internal storage › Joiplay ›
   games`).
2. Tap **Use this folder** at the bottom.
3. Confirm the read+write permission dialog.

<!-- screenshot: joiplay-set-folder.png -->

The app stores the granted tree URI permanently (via
`takePersistableUriPermission`) so it survives restarts. You only need to
re-grant when you uninstall the app, clear its data, or revoke the grant in
Android settings.

## Picking the right folder

The grant covers the **selected folder and everything inside it**. So:

- If all your games are under `Games/`, grant `Games/`.
- If half are under `Games/` and half under `Joiplay/games/`, grant a
  **higher level folder** that contains both (e.g. `Internal storage`
  itself, then navigate down — Android may restrict picking root directly,
  in which case grant the closest shared parent).

If you grant only `Games/` but some game lives under `Joiplay/games/`, our
delete and existence checks for those won't work — you'll see "Folder not
found" or "Re-grant" snackbars when trying to delete them.
