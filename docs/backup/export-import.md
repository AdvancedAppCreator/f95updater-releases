---
title: Export & import backup
last_updated: 2026-05-25
---

# Export & import backup

A manual snapshot of everything the app knows about your library, as one JSON
file. Use it before reinstalling, switching phones, or experimenting.

## What's included

- All **mappings** (package → F95 URL, threadId, lastSeenVersion,
  acknowledgedVersion, notOnF95 flag, personal status/rating/notes).
- The **hidden** packages list.
- A copy of the **JoiPlay games.json** from your last `.joiback` import.
- A copy of the **JoiPlay metadata.json** (used as a version-conflict fallback).
- All **per-game version overrides** you set via the conflict dialog.

## Export

Menu → **Backup & config** → **Export backup**. Pick a destination (any
location SAF allows). Default name: `f95updater-backup.json`.

Keep this file somewhere durable — cloud storage, email to yourself,
whatever survives reinstalls.

## Import

Menu → **Backup & config** → **Import backup**. The first time, the app explains
why it needs scoped access to the folder containing your backup, opens Android's
folder picker, then shows the in-app file picker for the JSON file. The app
**replaces** your current data with the contents of the backup and re-runs the
scan.

The chosen backup folder is remembered across restarts and shared with JoiPlay
`.joiback` import as long as Android still reports the persisted folder grant.

The import is also tolerant of the legacy "bare mappings" format and of
exports made by the PC-side bulk lookup tool.

## Not included

- **All-files access permission** — re-grant via **Menu → Grant all files
  access** after reinstall if you need install/delete/unused-folder features.
- **Scoped backup folder access** — Android owns this grant; if it is revoked,
  the app will ask you to choose the backup folder again.

## See also

- [Auto-backups](auto-backup.md) — automatic snapshots on every upgrade.
