---
title: Export & import backup
last_updated: 2026-05-18
---

# Export & import backup

A manual snapshot of everything the app knows about your library, as one JSON
file. Use it before reinstalling, switching phones, or experimenting.

## What's included

- All **mappings** (package → F95 URL, threadId, lastSeenVersion,
  acknowledgedVersion, notOnF95 flag).
- The **hidden** packages list.
- A copy of the **JoiPlay games.json** from your last `.joiback` import.
- A copy of the **JoiPlay metadata.json** (used as a version-conflict
  fallback).
- All **per-game version overrides** you set via the conflict dialog.

## Export

Menu → **Backup & config** → **Export backup**. Pick a destination (any
location SAF allows). Default name: `f95updater-backup.json`.

Keep this file somewhere durable — cloud storage, email to yourself,
whatever survives reinstalls.

## Import

Menu → **Backup & config** → **Import backup**. Pick the file. The app
**replaces** your current data with the contents of the backup and re-runs
the scan.

The import is also tolerant of the legacy "bare mappings" format and of
exports made by the PC-side bulk lookup tool.

## Not included

- **SAF grant for the JoiPlay games folder** — re-grant via
  [Set JoiPlay games folder](../joiplay/set-folder.md) after reinstall.
- **App config (`app_config.json`)** — see
  [App config drop-in](app-config.md).

## See also

- [Auto-backups](auto-backup.md) — automatic snapshots on every upgrade.
