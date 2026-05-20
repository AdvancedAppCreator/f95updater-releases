---
title: Changelog
last_updated: 2026-05-19
---

# Changelog

Major user-visible changes per version. Bugfixes and internal refactors are
intentionally summarized.

## v0.35.0

- **Extract & install** flow added: pick a `.zip` / `.rar` / `.7z` (with optional
  password) and the app extracts it locally, then opens a file browser so you
  pick the launch file to send to JoiPlay. Progress dialog with cancel,
  10 GB / 100× zip-bomb guards. See
  [Install a game in JoiPlay](joiplay/install-game.md).
- **JoiPlay settings** dialog: configure source folder, destination folder,
  and storage strategy (SAF / Full storage / Ask each time).
- "Don't show this again" option on the install-flow warning modal.

## v0.34.x

- v0.34.1 — Show home-screen (launcher) name in row title and expansion when
  it differs from the app's manifest label.
- v0.34.0 — Fix version-comparison: `0.4` is no longer treated as equivalent
  to `0.4.7b`. Replaced "F95 latest" with "Installed version" in the row
  expansion. Internal cleanup.

## v0.31.0

- **Stripe donations** added alongside Buy Me a Coffee. The ☕ icon and menu
  now open a chooser when both options are configured. See
  [Support the project](support.md).

## v0.30.0

- **Help link** in the menu and About dialog pointing at the online docs
  (this site).

## v0.29.0

- **Donate URL** baked into the default app config — fresh installs now show
  the ☕ icon. See [App config](backup/app-config.md).
- **Auto-backup safety net** added. Every app upgrade triggers a snapshot of
  your state; **Backup & config → Restore auto-backup…** lets you list and
  restore. See [Auto-backups](backup/auto-backup.md).

## v0.28 series

- v0.28.10 – Startup prune of JoiPlay backup entries whose folders no
  longer exist. See [Delete a JoiPlay game](joiplay/delete-game.md).
- v0.28.9 – Progress dialog while a JoiPlay folder is being deleted;
  deletion now persists across launches.
- v0.28.8 – JoiPlay delete walks the granted SAF tree relative to the
  game's `storagePath`, so games nested in sub-folders work.
- v0.28.7 – Menu **JoiPlay → Set JoiPlay games folder…** added. Submenus
  use visual nesting (left accent bar + tinted background, expand/collapse
  chevron).
- v0.28.5 – Open Folder targets Samsung **My Files** directly when present.
- v0.28.4 – Open Folder accepts paths in Samsung Secure Folder / non-zero
  user-ID emulated storage.
- v0.28.3 – Catalog search requires **all** query tokens to match (drops
  partial-token tier).
- v0.28.2 – Open Folder uses proper SAF tree URI for the fallback picker.
- v0.28.0 – **Multi-select**: long-press a row to enter selection mode,
  then bulk Hide / Unhide. See [Main screen](main-screen.md).

## v0.27 series

- v0.27.1 – Catalog search precomputes per-game lowercase / normalized /
  tokens, dropping per-keystroke cost to <10 ms. Catalog title shown
  under the local label when they differ.
- v0.27.0 – Edit dialog gains a **Search catalog** box with live results
  and a **Not on F95** button. See
  [Manual search](mapping/manual-search.md) and
  [Not on F95](mapping/not-on-f95.md).

## v0.26 series

- v0.26.3 – Catalog search results sorted alphabetically.
- v0.26.2 – First-run refresh detached from `LaunchedEffect` (no more
  self-cancellation mid-scan).
- v0.26.1 – First-run waits for the catalog if it's still downloading.

## How to read this changelog

Each change ideally links to its docs page. Bug fixes that don't add or
remove user-visible behavior are kept short.
